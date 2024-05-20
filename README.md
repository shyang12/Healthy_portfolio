# Healthy
## ▶ 안드로이드 스튜디오 헬스장 기구 예약 및 자세교정 앱 만들기 (Java)
 
 - 안드로이드 스튜디오에서 Java를 기반으로 기구 예약 및 자세교정 서비스를 구현하는 프로젝트
 - 기구 정보(Youtube 영상)등 헬스 초보자도 쉽게 이용 가능

`AWS EC2` `MySQL` `Youtube API` `Teachable Machine` `Linux` `Sublime Text 3` `Figma`

### ▶ ! AWS 암호화키 때문에 따로 만든 포트폴리오 (본 코드는 Private으로 돌려놨습니다) 요금 과금 발생 방지 !

![ㅇㄹㅇㄹ](https://github.com/shyang12/Healthy_portfolio/assets/85710913/25848d04-8d43-4b8d-a54f-2ad69b21f9cc)


## 1. Co-Development Environment   
### 1. 1 Environments `Java 96.1%  PHP 2.2%  HTML 1.7%`
- Windows 10
- Figma
- Android Studio / Java
- MySQL
- AWS EC2
- Linux `Ubuntu`
- SubLime Text 3 / PHP
- Teachable Machine / HTML `Json 파일`
- GitHub

### 1. 2 System Diagram & App Drawing

![구성도](https://github.com/shyang12/Healthy_portfolio/assets/85710913/bc9a41f8-c782-4860-b747-a01bae3a94a2)


### 1. 3 Teachable Machine Process of use

![ㄴㅇㄹㄴㅇㄹ](https://github.com/shyang12/Healthy_portfolio/assets/85710913/11051066-3f9e-4148-8229-fcc57c6a8588)


### 1. 4 Driving
- Android

### 1. 5 Implement
- AWS EC2 서버를 활용하여 `nginx`를 통해 리눅스 서버`Ubuntu`를 구축하고 `MySQL` `PHP`를 리눅스 서버에 설치하여 통합한 서버 구축
- UI를 꾸미기 위해 버튼 모양, edit text 모양 등 직접 디자인하여 색의 조합을 맞추고, 그림자 효과를 사용하여 애플리케이션에 더욱 입체감을 부여 -> `Figma 디자인 협업 툴 사용`
- 처음 접속 시 로그인하려면 회원가입을 해야 하며 회원가입 정보는 데이터베이스에 저장

  ▶ 저장된 정보와 일치 시 로그인을 할 수 있고 아이디는 `SQL 질의 구문`을 사용한 중복확인 버튼을 통해 중복 불가
- 회원 정보는 회원가입 화면에서 정보를 기재하면 데이터베이스의 사용자의 정보 저장
- 홈 화면에는 사용자의 이름, 처음 예약된 기구의 예약 시간, 혼잡도, 예약된 기구, 사진 등의 정보가 출력
- 기구 예약 화면에서는 운동 기구별로 시간 설정을 하여 예약을 할 수 있으며 예약된 시간이 일정표에 표시

  ▶ 사용자는 자신이 원하는 색을 지정하여 더욱 쉽게 자신의 예약 정보를 확인
- 기구 정보 화면에는 처음 접하거나 명칭을 잘 모르는 사람을 위해 기구별 정보와 사용 방법, 영상을 통해 설명 -> `Youtube API`

  ▶ 만약 잘못된 자세 ex) 구부정한 자세, 앞으로 쏠린 자세 등)로 스쿼트를 하게 되면 잘못되었다는 경고 소리와 화면에 경고 표시가 표시되며
     정상적인 동작을 수행했을 경우 카운트가 하나씩 증가

  ▶ `Teachable Machine`에서 `JSON` 형식으로 변환한 학습된 코드를 HTML 부분으로 수정하여 `Squat` `Stand` `Bent` 부분의 가중치를 `0.9 ~ 1.0`
     사이로 설정하여 조금 유하게 카운트가 될 수 있도록 설계하였고 `Sound툴`을 이용하여 녹음된 “잘못된 자세입니다.”를 Bent의 가중치가
     1.0이 되면 경고음이 울리도록 설정

  ▶ Squat 자세에서 Stand 자세로 바로 바뀌게 되면 Squat Count가 1씩 증가하도록 설계
- 사용자 정보 화면에서는 회원가입시의 정보가 들어있고 정보를 수정하고 탈퇴할 수 있으며 처음 화면인 로그인 화면으로 전환 가능

## 2. Project Architecture   
```bash
├── main
│   ├── Assist.java
│   ├── AssistAdapter.java
│   ├── DayView.java
│   ├── DeleteRequest.java
│   ├── DeleteReserve.java
│   ├── DirectionalRect.java
│   ├── EmailUpdateRequest.java
│   ├── Event.java
│   ├── Gym_inform.java
│   ├── Instrument_inform.java
│   ├── KindAdapter.java
│   ├── Loading.java
│   ├── Login.java
│   ├── LoginRequest.java
│   ├── My.java
│   ├── PwUpdateRequest.java
│   ├── Reserve.java
│   ├── ReserveInstrument.java
│   ├── Running.java
│   ├── RunningAdapter.java
│   ├── Signup.java
│   ├── SignupRequest.java
│   ├── SingerItem.java
│   ├── SingerViewer.java
│   ├── StretchAdapter.java
│   ├── Stretching.java
│   ├── TimeTableDialog.java
│   ├── TimeTableDialogRequest.java
│   ├── ValidateRequest.java
│   ├── Weight.java
│   ├── WeightAdapter.java
│   └── main.java
├── UI
│   ├── activity_assist.xml
│   ├── activity_loading.xml
│   ├── activity_login.xml
│   ├── activity_main.xml
│   ├── activity_reserveinstrument.xml
│   ├── activity_running.xml
│   ├── activity_signup.xml
│   ├── activity_stretching.xml
│   ├── activity_timetable.xml
│   ├── activity_weight.xml
│   ├── dialog_assist.xml
│   ├── dialog_kind.xml
│   ├── dialog_reserved.xml
│   ├── dialog_running.xml
│   ├── dialog_stretching.xml
│   ├── dialog_weight.xml
│   ├── fragment_gym_inform.xml
│   ├── fragment_home.xml
│   ├── fragment_instrument_inform.xml
│   ├── fragment_my.xml
│   ├── fragment_reserve.xml
│   ├── hour_label.xml
│   └── row.xml
```

## 3. SubLime Text 3 & Teachable Machine HTML (JSON)
```bash
├── healthy_server
│   ├── DeleteReserve.php
│   ├── DeleteUser.php
│   ├── LoadJsontoDB.php
│   ├── LoadReserve.php
│   ├── Logtest.php
│   ├── Resievent.php
│   ├── Resitest.php
│   ├── UpdateEmail.php
│   ├── Updatepw.php
│   ├── UserValidate.php
│   ├── bent.wav
│   ├── dbcon.php
│   ├── index.html
│   ├── phpinfo.php
│   └── sftp-config.json
├── my_model
│   ├── metadata.json
│   ├── model.json
│   └── weights.bin
```

## 4. MySQL   
### 4.1 MySQL Database
```bash
├── users
│    ├── name
│    ├── id
│    ├── pw
│    ├── year
│    ├── month
│    ├── day
│    └── email
├── revervations
│    ├── name
│    ├── st_name
│    ├── hour
│    ├── minute
│    ├── duration
│    └── color
```

## 5. Result

![결과](https://github.com/shyang12/Healthy_portfolio/assets/85710913/19d9bc24-66be-4e5e-866a-48dd6d5610d5)

- 자세교정 영상

https://github.com/shyang12/Healthy_portfolio/assets/85710913/f82ce9af-89b4-4e74-ab75-5ebe8cc76e81

  
