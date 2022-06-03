# 리눅스 명령어(top, ps, jobs, kill)와 vim에디터에서 매크로 사용법


## 리눅스 명령어(top, ps ,jobs, kill)
**1) tops**
* top은 실시간으로 CPU 사용률을 체크해준다.

```c
$ tops
```
![top](https://user-images.githubusercontent.com/98298940/171864295-e8338724-7ae3-4c9d-8499-9b4d0ed4ccc0.png)

* **주요 옵션**

|옵션|설명|
|:---:|:---:|
|-a|메모리 사용에 따라 정렬|
|-b|배치 모드에서 시작|
|-h|도움말|
|-n|반복의 최대수를 지정|

---

**2) ps**
* 리눅스 OS관리 시 프로세스를 확인하는 경우가 있는데 이때 ps명령어는 현재 실행중인 프로세스 목록을 보여준다.
* 주로 파이프와 grep명령어와 함께 사용하여 특정 프로세스를 확인하는데 많이 사용된다.

```c
$ ps
```

 ![ps](https://user-images.githubusercontent.com/98298940/171865892-024fbd7f-bafa-42da-9ad8-1084c2d1d2d2.png)
 
 * **주요 옵션**
 
 |옵션|설명|
 |:---:|:---:|
 |-e|모든 프로스세를 출력해준다|
 |-f|풀 포맷으로 보여준다.(UID,PID 등)|
 |-l|긴 포맷으로 보여준다|
 |-p|특정 PID의 프로세스를 보여준다|
 |-u|특정 사용자의 프로세스를 보여준다|
 
 ```c
 $ ps -e
 ```
 
 ![ps -e](https://user-images.githubusercontent.com/98298940/171866937-cbb05a70-66fc-4cd9-8226-df8752c2dc13.png)
 
 ---
 
 **3) jobs**
 * jobs 명령어는 작업의 상태를 표시하는 명령어이다.
 * 현재 쉘 세션에서 실행시킨 백그라운드의 작업 목록이 출력된다.
 * 각 작업에는 번호가 붙어 있어 kill명령어 뒤에 '%번호' 등으로 사용할 수 있다.
 
 ```c
  $ jobs [옵션][작업번호]
  ```


 ![job](https://user-images.githubusercontent.com/98298940/171868298-aa30a5d0-3fa5-4765-b7ee-55488013f330.png)

 * **jobs로 출력되는 백그라운드 작업의 상태값은 다음과 같다.**

|상태|설명|
|:---:|:---:|
|Running|작업이 계속 진행중임|
|Done|작업이 완료되어 0을 반횐|
|Done(code)|작업이 종료되었으며 0이 아닌 코드를 반환|
|Stopped|작업이 일시 중단|


* **주요 옵션**


|옵션|설명|
|:---:|:---:|
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그릅 중에 대표 프로스세 ID를 출력|
|-p|각 프로세스 ID에 대해 한 행씩 출력|

---

**4) kill**
* 리눅스에서 작업을 할 때 응용프로그램이나 프로세스가 멈추는 것을 볼 수 있다.
* 이 때의 해결책은 그 프로세스를 종료하는 것이다.
* kill 명령어는 대게 프로세스를 죽일 때 사용한다.

```c
$ kill [options][pid]
```

* **주요 옵션**

|옵션|설명|
|:---:|:---:|
|-l|시그널의 종류 출력|
|-s signal|시그널의 이름을 지정|


```c
$ kill -l
```

![kill](https://user-images.githubusercontent.com/98298940/171872431-c70b8166-0db0-4d34-9c6c-c3ec56432c76.png)

---

## vim에디터에서 매크로 사용법

**1) 매크로란?**
* 같은 동작을 반복하게 해주는 것이다.


**2) 매크로 시작 방법**

* q[name]을 한다.
```c
$ q[name]
```
![기록중](https://user-images.githubusercontent.com/98298940/171875587-e0dfdd57-07c1-4865-aa1a-4ad0c44ca1af.png)

* 그러면 recording @a 라면서 a라는 이름의 매크로가 기록중이라는 것을 알 수 있다.


**3) 동작 입력**

![동작](https://user-images.githubusercontent.com/98298940/171876160-d7f738b2-b8d9-4bb4-acb4-94236981689f.png)

* 여기서는 매크로 동작 입력에 입력모드를 실행시킨후 hello world를 입력했다


**4) 매크로 종료**

* 다시 q를 입력하면 매크로 기록이 종료가 된다.

![종료](https://user-images.githubusercontent.com/98298940/171876663-e4d3cfa6-a1bd-44d9-990b-9ea2c4a9211a.png)

* 매크로 종료가 되면 recording @a가 사라진다.

**5) 매크로 실행**

```c
$ @[name]
```

![매크로 실행](https://user-images.githubusercontent.com/98298940/171877319-8dd36b1e-9ced-42e5-b136-336a134961d1.png)

* 세번째 줄에서 매크로를 실행하니 hello world가 입력된다.




