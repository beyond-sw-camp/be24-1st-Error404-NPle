# 🛒 NPle
![로고](docs/NPle_Logo.png)
> **"함께 사면 더 싸다!"**
> 실시간 공동구매 딜과 그룹 매칭을 지원하는 이커머스 플랫폼입니다.

---

## 👥 1. 팀원 소개 (Team Members)

| 이름 | GitHub |
| :---: | :---: |
| **강신우** | [@id](https://github.com/id) |
| **이후경** | [@id](https://github.com/id) |
| **박범수** | [@id](https://github.com/id) |
| **이재혁** | [@id](https://github.com/id) |

---

## 📖 2. 프로젝트 개요 (Project Overview)

- 프로젝트 개요: 기존 이커머스의 직관적인 UX에 '공동구매' 방식을 결합하여, 특정 목표 인원이 모이면 자동으로 할인된 가격에 구매할 수 있는 플랫폼입니다.
- 기대 효과: 소비자는 복잡한 절차 없이 가격 혜택을 누리고, 판매자는 대량 판매를 통한 재고 소진과 안정적인 수익 구조를 확보하는 상생 모델을 지향합니다.
- 핵심 프로세스: 사용자는 별도의 리스크 없이 구매 예약을 진행하며, 목표 인원 달성 시에만 자동 결제가 이루어지고 미달 시에는 자동으로 취소되는 시스템입니다.

[프로젝트 기획안](https://github.com/beyond-sw-camp/be24-1st-Error404-NPle/blob/3b6ce68d9fc43252af19eeb40fd36a8b3319f5b1/docs/Error404_%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%20%EA%B8%B0%ED%9A%8D%EC%95%88.pdf)

---

## 📋 3. 요구사항 명세 (Requirements Specification)

[요구사항 명세](https://github.com/beyond-sw-camp/be24-1st-Error404-NPle/blob/3b6ce68d9fc43252af19eeb40fd36a8b3319f5b1/docs/NPle_%EC%9A%94%EA%B5%AC%EC%82%AC%ED%95%AD%20%EC%A0%95%EC%9D%98%EC%84%9C_1.0.pdf)

---

## 📐 4. ERD (Entity Relationship Diagram)

데이터베이스의 논리적/물리적 설계도입니다.
*(클릭하면 확대해서 볼 수 있습니다)*

![EDR](docs/NPle_ERD.png)

---

## 🏗️ 5. 시스템 아키텍처 (System Architecture)

서버 인프라 및 기술 구성도입니다.

![시스템 아키텍처](docs/NPle_Architecture.png)

* **Database:** MariaDB (Master-Slave 구조)
* **Infra:** Linux (Ubuntu 22.04 LTS) 
<details> <summary><strong>📌 아키텍처 설계 설명 보기</strong></summary> <br>

이커머스 서비스의 특성상 조회 트래픽이 압도적으로 많기 때문에, 이를 슬레이브 서버로 분산 처리하여 마스터 서버의 부하를 줄이고 전체적인 응답 속도를 향상시키는 구조입니다. HAProxy를 통해 트래픽을 유연하게 분산함으로써 특정 서버에 장애가 발생하더라도 서비스 중단 없이 안정적인 운영이 가능하도록 해당 구조를 채택했습니다.

특히 공동구매가 특정 시간에 오픈될 경우, 짧은 시간 동안 다수의 사용자가 동시에 접속하여 상품 상세 정보와 옵션을 조회하는 대량의 SELECT 요청이 발생합니다. 이러한 트래픽 급증 상황에서도 슬레이브 서버를 수평적으로 확장하는 것만으로 유연하게 대응할 수 있다는 장점이 있습니다.

</details>

---

## 💡 6. 부하테스트 전후 차이 
<details>
  <summary>1번 상품 리스트 조회 </summary>
  <div markdown="1" style="margin-left: 20px;">

<img src="" alt="before" align="center" />
<br/>
<img src="" alt="after" align="center" 

  </div>
</details>

<details>
  <summary>2번 특정 상품 조회 </summary>
  <div markdown="1" style="margin-left: 20px;">

<img src="./img/2_sql_before.png" alt="before" align="center" />
<br/>
<img src="./img/2_sql_after.png" alt="after" align="center" 

  </div>
</details>









