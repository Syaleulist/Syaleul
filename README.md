# 🍕 배달앱 음식 주문 시나리오 – 시퀀스 다이어그램 & 샘플 코드

## 💡 주제 개요

이 프로젝트는 **배달앱을 통해 음식 주문**하는 과정을 모델링한 과제입니다.  
일상 속 소프트웨어 사용 사례로, 사용자가 앱에서 음식을 고르고 결제한 뒤 배달 상태를 확인하는 일련의 흐름을  
**시퀀스 다이어그램과 샘플 코드**로 구현하였습니다.

---

## 🗂️ 시퀀스 다이어그램

Mermaid 문법을 활용하여 작성된 시퀀스 다이어그램입니다.  
Mermaid.live 또는 GitHub 지원 뷰어에서 시각화할 수 있습니다.

```mermaid
sequenceDiagram
    participant User
    participant App
    participant Server
    participant PaymentGateway
    participant DeliveryService

    User->>App: 음식 선택
    App->>Server: 주문 요청 전송
    Server-->>App: 주문 확인 응답
    App->>User: 주문 확인 알림
    User->>App: 결제 요청
    App->>PaymentGateway: 결제 정보 전송
    PaymentGateway-->>App: 결제 성공 응답
    App->>Server: 결제 완료 알림
    Server->>DeliveryService: 배달 요청
    DeliveryService-->>Server: 배달 접수 완료
    Server-->>App: 배달 상태 정보 전송
    App->>User: 배달 상태 안내
