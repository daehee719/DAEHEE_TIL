###자바스크립트는 어떻게 실행이 되나?
![image](https://user-images.githubusercontent.com/81199906/202843868-ae13ac53-1a39-41f7-acd4-211f5c729574.png)
자바스크립트는 동적으로 어떠한 기능을 해주는 언어이다.
앞서, 자바스크립트는 웹페이지에 내장되어 일을 한다고 했다.
사실 웹에 있는 엔진을 통해 자바스크립트가 동적으로 컴파일 되고, 실행이 되는 것이다.

![image](https://user-images.githubusercontent.com/81199906/202843966-e202ecac-996c-460f-b035-e168b84f72e1.png)
크롬의 V8엔진을 보면 코드가 다양한 과정을 거쳐 실행이 된다.
3번의 과정이 있다.
1. Parse Code : 코드를 분석해서 읽는다.
2.  Compile to Machine Code : 분석하여 읽은 것을 더욱 빠른 기계어로 바꾼다.
3. Run Code : 바꾼 기계어를 실행한다.
