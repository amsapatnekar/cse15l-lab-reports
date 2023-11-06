# Lab Report 3

## Part 1

**Failure inducing input**
~~~~
  @Test
  public void testAverageWithouttLowest() {
    double[] input1 = {3.0,2.0,1.0,1.0};
    double solution = 2.5;
    assertEquals(solution, ArrayExamples.averageWithoutLowest(input1),0.0001);
  }
~~~~

**Non-failure inducing input**

~~~~
@Test
  public void testAverageWithouttLowest2() {
    double[] input1 = {3.0,2.0,1.0};
    assertEquals(2.5,ArrayExamples.averageWithoutLowest(input1), 0.0001);
  }
~~~~

**Symptom**

![image](testSymptom.png) 

**The bug**

*Before*

~~~~
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
~~~~

*After*

~~~~
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    int countLowest = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
      if(num == lowest) {countLowest+=1; }
    }
    return sum / (arr.length - countLowest);
  }
~~~~

The problem with the original code is that it needed to account for what can happen if there are more than 1 of the lowest number. By initializing a variable **countLowest**, to keep track of how many instances of the lowest double are contained in the argument, we are able to keep track of how many instances there are, and then subtract that from our average calculation.   
