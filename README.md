# Healthy
## ▶ 안드로이드 스튜디오 헬스장 기구 예약 및 자세교정 앱 만들기 (Java)
 
 - 안드로이드 스튜디오에서 Java를 기반으로 기구 예약 및 자세교정 서비스를 구현하는 프로젝트
 - 기구 정보(Youtube 영상)등 헬스 초보자도 쉽게 이용 가능

`kpostal (우편주소 API)` `Firebase` `Firestore Database` `SHA-256`

### ▶ ! AWS 암호화키 때문에 따로 만든 포트폴리오 (본 코드는 Private으로 돌려놨습니다) 요금 과금 발생 방지 !

## 1. Co-Development Environment   
### 1. 1 Environments `Java 96.1%  PHP 2.2%  HTML 1.7%`
- Windows 10
- Android Studio / Java
- MySQL
- AWS EC2
- Linux `Ubuntu`
- SubLime Text 3 / PHP
- Teachable Machine / HTML `Json 파일`
- GitHub

### 1. 2 Driving
- Android

### 1. 3 Implement
- 상품 리스트를 ScrollView를 통해 상품 사진, 상품명, 가격등 정보 제공 -> `나의 주문목록, 장바구니 확인 버튼 위에 추가`
- 제품의 상세 페이지를 통해 제품의 상세 내용 제공
- 장바구니 기능을 통해 상품 개수 추가 or 감소, 삭제등 구매하기 전 장바구니 기능
- 우편번호(주소) API를 사용하여 사용자에게 택배 보낼 주소 저장 기능
- 주문목록에서 주문날짜, 주분정보, 주문취소, 배송조회등의 기능
- 주문완료 페이지를 통해 최종 결제

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

## 3. MySQL   
### 3.1 Firestore Database
```bash
├── orders
│    ├── buyerEmail
│    ├── buyerName
│    ├── buyerPhone
│    ├── deliveryStatus
│    ├── orderDate
│    ├── orderNo
│    ├── paymentMethod
│    ├── paymentStatus
│    ├── productNo
│    ├── quantity
│    ├── receiverAddress1
│    ├── receiverAddress2
│    ├── receiverName
│    ├── receiverPhone
│    ├── receiverZip
│    ├── totalPrice
│    ├── unitPrice
│    └── userPwd
├── products
│    ├── price
│    ├── productImageUrl
│    ├── productName
│    └── productNo
```

## 4. Result

![결과](https://github.com/shyang12/Healthy_portfolio/assets/85710913/19d9bc24-66be-4e5e-866a-48dd6d5610d5)
