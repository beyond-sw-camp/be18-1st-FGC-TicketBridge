# be18-1st-3team
## 팀원 소개
<table>
  <tr align="center">
    <td>김대의</td>
    <td>김재상</td>
    <td>이진구</td>
    <td>임성민</td>
    <td>조원석</td>
    <td>전하윤</td>
  </tr>
  <tr align="center">
    <td><a target="_blank" href="https://github.com/kimeodml"><img src="https://avatars.githubusercontent.com/u/88065770?v=4" width="100px"><br>@kimeodml</a></td>
    <td><a target="_blank" href="https://github.com/jaesangE"><img src="https://avatars.githubusercontent.com/u/106606736?v=4" width="100px"><br>@jaesangE</a> </td>
    <td><a target="_blank" href="https://github.com/LeeJingu01"><img src="https://avatars.githubusercontent.com/u/174857452?v=4" width="100px"><br>@LeeJingu01</a> </td>
    <td><a target="_blank" href="https://github.com/baechuking"><img src="https://avatars.githubusercontent.com/u/215663014?v=4" width="100px"><br>@baechuking</a>  </td>
    <td><a target="_blank" href="https://github.com/jws020501"><img src="https://avatars.githubusercontent.com/u/59154288?v=4" width="100px"><br>@jws020501</a>  </td>
    <td><a target="_blank" href="https://github.com/Losientonana"><img src="https://avatars.githubusercontent.com/u/118197691?v=4" width="100px"><br> @Losientonana</a></td>
  </tr>
</table>

---

## 목차

1. 개요
    
    1-1. 주제
    
    1-2. 프로젝트 배경 및 필요성
    
    1-3. 프로젝트 소개
    
    1-4. 프로젝트 주요기능
    
    1-5. 서비스 차별화 전략
    
2. 유스케이스 다이어그램
3. 요구사항 명세서
4. ERD
5. 테이블 명세서
6. 💻SQL개발

---

## 1.1 주제

- 티켓팅 사이트의 통합을 통해 사용자에게 편리한 공연 예매 환경 제공
- 사용자에게 편리한 공연 예매 환경을 제공하기 위한 통합 공연 티켓팅 플랫폼
- 좌석 시야부터 공연 정보 예매 정보까지, 공연 예매를 도와주는 통합 공연 티켓팅 플랫폼

---

## 1.2 프로젝트 배경 및 필요성

- **사이트별로 다른 정보**

    <img src="https://github.com/user-attachments/assets/f05ef0e9-ffdb-4f97-82aa-0f8a8934f019" width="50%" />

    <img src="https://github.com/user-attachments/assets/e0983873-d6db-40bb-bcf0-658d826ca86c" width="50%" />


    YES24에서는 예매 가능한 공연이 인터파크(NOL) 에서는 검색이 되지 않거나 YES24와 인터파크 둘 다에 대해 동일한 공연이 존재하지만, 잔여좌석 수를 확인 할 수 없는 경우가 존재하고 사이트마다 공연에 적용되는 카드 할인, 프로모션, 수수료 등이 
    예매 사이트에 따라 달라서 직접 사이트를 방문해야 하며 이 과정에서 사용자는 불필요한 시간과 노력을 요구받게 됩니다. 

- **좌석 피해 사례**

    <img src="https://github.com/user-attachments/assets/15634131-c71b-4274-8b42-74c4d5957388" width="50%" />


    대부분의 예매 플랫폼은 좌석 번호와 등급만 제공하며, 해당 좌석에서 무대가 얼마나 잘 보이는지에 대한 정보는 제공되지 않습니다.
    이로 인해 일부 관객은 기둥이나 벽에 가려 공연이 제대로 보이지 않는 ‘시야 제한석’을 예매하게 되고, 예매 전에는 알 수 없었던 불편함으로 공연 만족도가 크게 떨어지게 됩니다.

- **공연 시장 확대**

    <img src="https://github.com/user-attachments/assets/7a4e9dd0-5757-498c-a5bc-3c62a943088c" width="50%" />


    출처 : [KOPIS] 공연예술 통합전산망 2024년 총결산 공연시장 티켓판매 현황 분석 보고서

    코로나19 이후 억눌렸던 문화, 여가 활동에 대한 수요가 폭발하며, 국내 공연 시장도 빠르게 회복세를 보입니다. KOPIS(공연예술통합전산망)의 자료에 따르면, 2024년 기준 국내 공연 시장은 지속적으로 증가세를 기록했습니다.

    이처럼 공연시장이 확대됨에도 불구하고 여전히 사용자는 공연 정보 접근성이 부족하다고 생각하여 프로젝트를 기획하게 되었습니다.

---

## 1.3 프로젝트 소개

“티켓브릿지(TicketBridge)” [ 가제 ]는 YES24, 인터파크, 티켓링크 등 다양한 공연 티켓팅 사이트에 흩어진 공연 정보를 한곳에 모아 제공해 사용자는 공연 정보를 더 쉽게 탐색하고, 실제 관람 후기를 참고하거나 좌석별 시야 이미지를 확인해 보다 정확한 정보를 바탕으로 좌석을 선택할 수 있습니다.

사용자는 자신이 좋아하는 공연이나 아티스트를 북마크 해두면, 예매처와 관계없이 해당 공연이 등록되었을 때 자동으로 알림을 받아 예매 기회를 놓치지 않을 수 있습니다.

공연마다 다른 예매처의 가격 및 좌석 조건을 비교할 수 있어, 사용자에게 더 편리하고 만족도 높은 예매 환경을 제공할 것 입니다

---

## 1.4 프로젝트 주요기능

- **회원 기능**
- **공연 일정 통합 조회**
    
    **YES24, 인터파크, 티켓링크 등 주요 티켓팅 사이트의 공연 정보를 수집하여 화면에서 통합 제공**
    
- **좌석 시야 정보 제공**
    
    
- **북마크 기능**
- **관람 후기 리뷰 기능**
- **북마크 및 예매 정보 기입 시 알림 기능**
- **공연 추천 기능**

---

## **1.5 서비스 차별화 전략**

---

## **2. 유스케이스 다이어그램**
<img src="https://github.com/user-attachments/assets/2139b138-ab01-457a-b6a9-c52f005062ae" width="50%" />


---

## **3. 요구사항 명세서**
[요구사항 명세서](https://docs.google.com/spreadsheets/d/1_PlSBTiDaWMltI1_8KaKv3UF04rUYA0L5o9ec0qnmz0/edit?usp=sharing)
---

## **4. ERD**
![image](https://github.com/user-attachments/assets/37f0781a-3831-4348-b94a-473d8a125637)

---

## **5. 테이블 명세서**
[테이블 명세서]()

