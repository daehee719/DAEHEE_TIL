### 

### 1.1 운영체제의 구조

![커널 (컴퓨팅) - 위키백과, 우리 모두의 백과사전](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8f/Kernel_Layout.svg/800px-Kernel_Layout.svg.png)

#### 운영체제의 핵심은 "커널"이다

###### 커널은 프로세스와 메모리, 저장장치를 관리한다.

<img src="file:///C:/Users/USER/AppData/Roaming/marktext/images/2022-09-15-22-42-18-image.png" title="" alt="" width="566">

###### 사용자는 운영체제에 직접 접근할 수 없고 인터페이스를 통해 접근할 수 있다.

###### 인터페이스는 GUI 와 CUI로 나뉘는데 이것은 텍스트냐 그림이냐의 차이만 있을 뿐, 커널에 접근하기 위한 목적은 같다.

![04 OS 서비스와 시스템콜 | CloudStudying](https://i.imgur.com/YINBipo.png)

> ###### 어플리케이션 같은 경우, 시스템 콜을 통해서 커널에 접근할 수 있다.
> 
> ###### 커널은 사용자로부터 자신을 보호하기 위한 "시스템 콜"이라는 인터페이스를 가지고 있다.
> 
> ###### 사용자나 어플리케이션이 하드디스크에 접근한다고 가정해보자.

![](C:\Users\USER\AppData\Roaming\marktext\images\2022-09-15-22-43-33-image.png)

> ###### 시스템 콜이 없이 어플리케이션이 하드디스크에 접근하게 되면 원래 하드디스크에 있었던 중요한 데이터들을 덮어씌워서 기존의 데이터들이 날아갈수도 있다.
> 
> ###### 시스템 콜 인터페이스를 사용하면 Write()라는 함수를 사용하게 되는데, 이 함수는 운영체제가 알아서 하드디스크의 빈 공간에 저장하게 된다.

<img src="https://img1.daumcdn.net/thumb/R800x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdvUcAT%2Fbtq2MPijaN1%2FucPcKdcatHFNN9RY6EGt8K%2Fimg.png" title="" alt="LInux Kernel] 문자 디바이스 드라이버 작성" width="675">

###### 하드웨어와 커널의 사이에도 인터페이스가 있는데, 바로 "드라이버"이다.

###### 운영체제는 많은 종류의 하드웨어를 전부 지원해야 하기 때문에 각각의 하드웨어에 맞는 프로그램을 커널이 미리 갖고 있기는 힘들다.

###### 그래서 하드웨어를 제작한 제작사에서 드라이버를 만들어 제공하는게 일반적이다.
