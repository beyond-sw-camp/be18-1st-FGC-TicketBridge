# be18-1st-FGC-TicketBridge
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
    
    1-1. [주제](#11-주제)
    
    1-2. [프로젝트 배경 및 필요성](#12-프로젝트-배경-및-필요성)
    
    1-3. [프로젝트 소개](#13-프로젝트-소개)
    
    1-4. [프로젝트 주요기능](#14-프로젝트-주요기능)
    
    1-5. [서비스 차별화 전략](#15-서비스-차별화-전략)
    
2. [WBS](#2-wbs)
3. [요구사항 명세서](#3-요구사항-명세서)
4. [유스케이스 다이어그램](#4-유스케이스-다이어그램)
5. [테이블 명세서](#5-테이블-명세서)
6. [ERD](#6-erd)
7. [DDL](#7-ddl)
8. [프로시저](#8-프로시저)
9. [회고](#9-회고)

---

## 1.1 주제

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

“티켓브릿지(TicketBridge)”는 YES24, 인터파크, 티켓링크 등 다양한 공연 티켓팅 사이트에 흩어진 공연 정보를 한곳에 모아 제공해 사용자는 공연 정보를 더 쉽게 탐색하고, 실제 관람 후기를 참고하거나 좌석별 시야 이미지를 확인해 보다 정확한 정보를 바탕으로 좌석을 선택할 수 있습니다.

사용자는 자신이 좋아하는 공연이나 아티스트를 북마크 해두면, 예매처와 관계없이 해당 공연이 등록되었을 때 자동으로 알림을 받아 예매 기회를 놓치지 않을 수 있습니다.

공연마다 다른 예매처의 가격 및 좌석 조건을 비교할 수 있어, 사용자에게 더 편리하고 만족도 높은 예매 환경을 제공할 것 입니다.

---

## 1.4 프로젝트 주요기능

- **회원 기능**
- **공연 일정 통합 조회**
    
    **YES24, 인터파크, 티켓링크 등 주요 티켓팅 사이트의 공연 정보를 수집하여 화면에서 통합 제공**
    
- **좌석 시야 정보 제공**
- **북마크 기능**
- **관람 후기 리뷰 기능**
- **알림 기능**
- **공연 추천 기능**

---

## **1.5 서비스 차별화 전략**
## 통합 플랫폼

- 여러 공연 예매 사이트(인터파크, YES24, 티켓링크 등)의 공연 정보를 하나의 플랫폼에 통합하여 사용자에게 제공하여 사용자 접근성 향상
- 사용자는 각 사이트를 일일이 방문할 필요 없이, 한 곳에서 공연 검색, 예매까지 가능
- 사이트별 잔여석, 좌석 배치를 실시간으로 연동하여 정보 제공

### **공연 좌석 정보 제공**

- 좌석별 시야 이미지, 후기, 별점 등 시각적이고 직관적인 정보 제공
- 좌석 선택 시 실제 공연장에서의 시야를 미리 확인할 수 있어 사용자의 좌석 선택의 폭 증가

### **예매 연습 기능**

- 실전과 동일한 예매 환경을 제공해 사전 연습 가능
---

## **2. WBS**
<a href="https://docs.google.com/spreadsheets/d/1_PlSBTiDaWMltI1_8KaKv3UF04rUYA0L5o9ec0qnmz0/edit?gid=1299906392#gid=1299906392" target="_blank">👉WBS 바로가기</a>

<img alt="image" src="https://github.com/user-attachments/assets/fa3db2ca-25d2-4827-a999-292e575676d7" width="50%"/>


---

## **3. 요구사항 명세서**
<a href="https://docs.google.com/spreadsheets/d/1_PlSBTiDaWMltI1_8KaKv3UF04rUYA0L5o9ec0qnmz0/edit?gid=0#gid=0" target="_blank">👉요구사항 명세서 바로가기</a>


<img alt="image" src="https://github.com/user-attachments/assets/284e235d-1d66-41b8-9bfb-3a076ac2d5ef" width="50%" />

---

## **4. 유스케이스 다이어그램**
<img src="https://github.com/user-attachments/assets/2139b138-ab01-457a-b6a9-c52f005062ae" width="50%"/>

---

## **5. 테이블 명세서**

<a href="https://docs.google.com/spreadsheets/d/1_PlSBTiDaWMltI1_8KaKv3UF04rUYA0L5o9ec0qnmz0/edit?gid=993473287#gid=993473287" target="_blank">👉테이블 명세서 바로가기</a>


<img alt="image" src="https://github.com/user-attachments/assets/d8346454-3ca9-4717-b71d-4be44dfac46b" width="50%" />

---

## **6. ERD**
![image](https://github.com/user-attachments/assets/8be26278-8602-4212-8d29-16537c999978)

---

## **7. DDL**
<details>
<summary>1. users 테이블</summary>

```sql
 CREATE TABLE `users` (
  `users_id` INT NOT NULL AUTO_INCREMENT,
  `email` VARCHAR(255) NOT NULL,
  `password` VARCHAR(255) NOT NULL,
  `nickname` VARCHAR(50) NOT NULL,
  `gender` ENUM('남성','여성') NOT NULL,
  `age` INT NOT NULL,
  `profile_image` VARCHAR(255) DEFAULT NULL,
  `create_at` DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`users_id`),
  UNIQUE KEY `email` (`email`),
  UNIQUE KEY `nickname` (`nickname`),
  CONSTRAINT `users_chk_1` CHECK ((`age` between 0 and 150))
);
```
</details>

<details>
<summary>2. performers 테이블</summary>
  
```sql
CREATE TABLE `performers` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(100) NOT NULL,
  `type` varchar(30) NOT NULL,
  `agency` varchar(100) DEFAULT NULL,
  `profile_img` varchar(255) DEFAULT NULL,
  `bio` TEXT DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `name` (`name`)
);
```
</details>

<details>
<summary>3. show_performers 테이블</summary>
  
```sql
CREATE TABLE `shows_performers` (
  `shows_id` INT NOT NULL,
  `performer_id` INT NOT NULL,
  `performer_role` varchar(50) NOT NULL,
  PRIMARY KEY (`shows_id`, `performer_id`,`performer_role`),
  KEY `shows_id` (`shows_id`),
  KEY `performer_id` (`performer_id`),
  CONSTRAINT `show_performers_ibfk_2` FOREIGN KEY (`shows_id`) REFERENCES `shows` (`shows_id`),
  CONSTRAINT `show_performers_ibfk_1` FOREIGN KEY (`performer_id`) REFERENCES `performers` (`id`)
);
```
</details>



<details>
<summary>4. genres 테이블</summary>
  
```sql
CREATE TABLE `genres` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `name` VARCHAR(50) NOT NULL,
  `description` VARCHAR(255) DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `name` (`name`)
);
```
</details>

<details>
<summary>5. user_interest_genres 테이블</summary>
  
```sql
CREATE TABLE `user_interest_genres` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `user_id` INT NOT NULL,
  `genres_id` INT NOT NULL,
  PRIMARY KEY (`id`),
  KEY `user_id` (`user_id`),
  KEY `genres_id` (`genres_id`),
  CONSTRAINT `user_interest_genres_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`users_id`),
  CONSTRAINT `user_interest_genres_ibfk_2` FOREIGN KEY (`genres_id`) REFERENCES `genres` (`id`)
);
```
</details>

<details>
<summary>6. user_interest_performers 테이블</summary>
  
```sql
CREATE TABLE `user_interest_performers` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `user_id` INT NOT NULL,
  `performers_id` INT NOT NULL,
  PRIMARY KEY (`id`),
  KEY `user_id` (`user_id`),
  KEY `performers_id` (`performers_id`),
  CONSTRAINT `user_interest_performers_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`users_id`),
  CONSTRAINT `user_interest_performers_ibfk_2` FOREIGN KEY (`performers_id`) REFERENCES `performers` (`id`)
);
```
</details>

<details>
<summary>7. venues 테이블</summary>
  
```sql
CREATE TABLE `venues` (
  `venues_id` INT NOT NULL AUTO_INCREMENT,
  `venues_name` VARCHAR(100) NOT NULL,
  `venues_location` VARCHAR(150) DEFAULT NULL,
  `seat_count` INT DEFAULT NULL,
  `business_hours` VARCHAR(50) DEFAULT NULL,
  PRIMARY KEY (`venues_id`),
  UNIQUE KEY `name` (`name`)
);
```
</details>

<details>
<summary>8. shows 테이블</summary>
  
```sql
CREATE TABLE `shows` (
  `shows_id` INT NOT NULL AUTO_INCREMENT,
  `title` VARCHAR(200) NOT NULL,
  `price` INT NOT NULL,
  `genres_id` INT NOT NULL,
  `venues_id` INT NOT NULL,
  `start_date` DATETIME NOT NULL,
  `end_date` DATETIME NOT NULL,
  `ticket_open_at` DATETIME NOT NULL,
  `ticket_close_at` DATETIME NOT NULL,
  `platform` VARCHAR(50) NOT NULL,
  `description` TEXT DEFAULT NULL,
  `url` VARCHAR(255) DEFAULT NULL,
  PRIMARY KEY (`shows_id`),
  KEY `genres_id` (`genres_id`),
  KEY `venue_id` (`venues_id`),
  CONSTRAINT `shows_ibfk_2` FOREIGN KEY (`genres_id`) REFERENCES `genres` (`id`),
  CONSTRAINT `shows_ibfk_3` FOREIGN KEY (`venues_id`) REFERENCES `venues` (`venues_id`)
);
```
</details>

<details>
<summary>9. seats 테이블</summary>
  
```sql
CREATE TABLE `seats` (
  `seat_id` INT NOT NULL AUTO_INCREMENT,
  `venues_id` INT NOT NULL,
  `section` VARCHAR(20) DEFAULT NULL,
  `seats_row` VARCHAR(10) DEFAULT NULL,
  `number` VARCHAR(10) DEFAULT NULL,
  `seat_img` VARCHAR(255) DEFAULT NULL,
  PRIMARY KEY (`seat_id`),
  KEY `venue_id` (`venues_id`),
  CONSTRAINT `seats_ibfk_1` FOREIGN KEY (`venues_id`) REFERENCES `venues` (`venues_id`)
);
```
</details>

<details>
<summary>10. reservations 테이블</summary>
  
```sql
CREATE TABLE `reservations` (
  `reserve_id` INT NOT NULL AUTO_INCREMENT,
  `user_id` INT NOT NULL,
  `shows_id` INT NOT NULL,
  `seat_id` INT DEFAULT NULL,
  `reservation_date` DATETIME NOT NULL,
  `platform` VARCHAR(50) NOT NULL,
  PRIMARY KEY (`reserve_id`),
  KEY `user_id` (`user_id`),
  KEY `show_id` (`shows_id`),
  KEY `seat_id` (`seat_id`),
  CONSTRAINT `reservations_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`users_id`),
  CONSTRAINT `reservations_ibfk_2` FOREIGN KEY (`shows_id`) REFERENCES `shows` (`shows_id`),
  CONSTRAINT `reservations_ibfk_3` FOREIGN KEY (`seat_id`) REFERENCES `seats` (`seat_id`)
);
```
</details>

<details>
<summary>11. bookmarks 테이블</summary>
  
```sql
CREATE TABLE `bookmark` (
  `bookmark_id` INT NOT NULL AUTO_INCREMENT,
  `user_id` INT NOT NULL,
  `shows_id` INT NOT NULL,
  `performers_id` INT NOT NULL,
  `created_at` DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`bookmark_id`),
  KEY `user_id` (`user_id`),
  KEY `shows_id` (`shows_id`),
  KEY `performers_id` (`performers_id`),
  CONSTRAINT `bookmarks_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`user_id`),
  CONSTRAINT `bookmarks_ibfk_2` FOREIGN KEY (`shows_id`) REFERENCES `shows` (`shows_id`),
  CONSTRAINT `bookmarks_ibfk_3` FOREIGN KEY (`performers_id`) REFERENCES `performers` (`id`)
);
```
</details>

<details>
<summary>12. reviews 테이블</summary>
  
```sql
CREATE TABLE `reviews` (
  `reviews_id` INT NOT NULL AUTO_INCREMENT,
  `user_id` INT NOT NULL,
  `reserve_id` INT NOT NULL,
  `rating` DECIMAL(2,1) NOT NULL,
  `comment` TEXT DEFAULT NULL,
  `review_like` INT DEFAULT NULL,
  `review_hate` INT DEFAULT NULL,
  `photo` VARCHAR(255) DEFAULT NULL,
  `created_at` DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`reviews_id`),
  KEY `user_id` (`user_id`),
  KEY `reserve_id` (`reserve_id`),
  CONSTRAINT `reviews_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`users_id`),
  CONSTRAINT `reviews_ibfk_2` FOREIGN KEY (`reserve_id`) REFERENCES `reservations` (`reserve_id`)
);
```
</details>

<details>
<summary>13. notification 테이블</summary>
  
```sql
CREATE TABLE `notification` (
  `notifi_id` INT NOT NULL AUTO_INCREMENT,
  `user_id` INT NOT NULL,
  `shows_id` INT NOT NULL,
  `noti_type` ENUM('RESERVATION_SOON', 'RESERVATION_DAY_BEFORE', 'BOOKMARK_SOON', 'BOOKMARK_NEWS') NOT NULL,
  `is_on` TINYINT(1) NOT NULL DEFAULT '1',
  `sent_at` DATETIME NOT NULL,
  PRIMARY KEY (`notifi_id`),
  KEY `user_id` (`user_id`),
  KEY `shows_id` (`shows_id`),
  CONSTRAINT `notifications_ibfk_1` FOREIGN KEY (`user_id`) REFERENCES `users` (`id`),
  CONSTRAINT `notifications_ibfk_2` FOREIGN KEY (`shows_id`) REFERENCES `shows` (`shows_id`)
);
```
</details>


---

## **8. 프로시저**

<details>
  <summary>1. 회원</summary>

  <details>
    <summary>1. 회원가입을 통해 user entity에 회원이 등록되어야 한다</summary>

  - 회원가입  
    - 기존 데이터  
      <br>
      <img width="979" alt="스크린샷 2025-07-08 오후 4 22 19" src="https://github.com/user-attachments/assets/b9b36007-18f9-4001-9fce-3dfd6d4447ae" />
      <br>

    - 회원 추가 프로시저 생성  
      
      <br>
      <img width="992" alt="스크린샷 2025-07-08 오후 4 27 56" src="https://github.com/user-attachments/assets/523a6570-53b6-4a92-9ab0-a981f32bdadd" />
      <br>

    - 프로시저 실행 결과
      <br>
      <img width="1018" alt="스크린샷 2025-07-08 오후 4 28 38" src="https://github.com/user-attachments/assets/5c3cc653-39af-42cf-aa13-6fd11419dcc0" />
      <br>

  </details>

  <details>
    <summary>2. 회원 정보를 수정한다 (닉네임, 비밀번호, 프로필사진)</summary>

   - 회원 정보 수정  
      - 기존 데이터  
        <br>
        <img width="1013" alt="스크린샷 2025-07-08 오후 4 39 40" src="https://github.com/user-attachments/assets/c217304d-056f-4faf-a173-7593a2b43601" />
        <br>
      - 프로시저  
        <br>
        <img width="999" alt="스크린샷 2025-07-08 오후 4 40 06" src="https://github.com/user-attachments/assets/00d7b197-70f6-4f47-848b-ad50cb3e40fb" />
        <br>
      - 실행 후 결과 값  
        <br>
        <img width="997" alt="스크린샷 2025-07-08 오후 4 40 21" src="https://github.com/user-attachments/assets/3c90ab99-ac8c-42e8-bdbe-43de0a5ccce7" />
        <br>
  </details>

  <details>
    <summary>3. 회원이 탈퇴하면 계정을 삭제한다</summary>

  - 회원 삭제  
      - 기존 데이터  
        <br>
        <img width="886" alt="스크린샷 2025-07-08 오후 4 36 52" src="https://github.com/user-attachments/assets/c38df3c9-57e9-4655-a4d9-f16d086581ab" />
        <br>
      - 프로시저  
        <br>
        <img width="901" alt="스크린샷 2025-07-08 오후 4 37 05" src="https://github.com/user-attachments/assets/da9e6bb4-127c-445a-93f6-ecfea8686d56" />
        <br>
      - 실행 결과  
        <br>
        <img width="952" alt="스크린샷 2025-07-08 오후 4 37 20" src="https://github.com/user-attachments/assets/f8c9eb97-60f2-4497-a20b-40f6fb285ae8" />
        <br>
  </details>

  <details>
    <summary>4. 회원의 이메일/비밀번호를 찾는다</summary>

   - 회원의 이메일 찾기  
      - 프로시저  
        <br>
        ![image](https://github.com/user-attachments/assets/7d9f8a90-6a0b-4de7-9a27-ed639b593d75)
        <br>
      - 결과  
        <br>
        ![image](https://github.com/user-attachments/assets/1ded459a-93b6-48ad-8f50-8df396cf7518)
        <br>
  - 회원의 비밀번호 찾기  
      - 프로시저  
        <br>
        ![image](https://github.com/user-attachments/assets/c838216e-4d47-47c8-8910-3dc7ff8c8699)
        <br>
      - 결과  
        <br>
        ![image](https://github.com/user-attachments/assets/83ff216a-ff02-48a9-9c68-a6838094531b)
        <br>
  </details>
</details>

<details>
  <summary>2. 공연</summary>

  <details>
    <summary>1. 공연 목록/검색 (필터 조건: 공연명, 일정, 장소 등)</summary>

  - 사용자에 요구사항에 맞는 공연 목록 조회  
      - 프로시저  
        <br>
        <img width="878" alt="스크린샷 2025-07-08 오후 4 40 50" src="https://github.com/user-attachments/assets/8c0a4508-8999-486d-b21b-260491d787c3" />
        <br>
      - 실행 결과  
        - 전체 공연 조회  
          <br>
          <img width="1007" alt="스크린샷 2025-07-08 오후 4 41 12" src="https://github.com/user-attachments/assets/80a4e21c-4fb0-4fd2-9459-9aa668f679c7" />
          <br>
        - 공연명 ‘뮤지컬’ 포함 공연 전체 조회  
          <br>
          <img width="1005" alt="스크린샷 2025-07-08 오후 4 41 34" src="https://github.com/user-attachments/assets/1afe3f57-ba12-426b-9b88-953539eea471" />
          <br>
        - 공연장명 ‘인천시립극장’인 공연만 조회
          <br>
          <img width="1013" alt="스크린샷 2025-07-08 오후 4 41 49" src="https://github.com/user-attachments/assets/02092d16-520c-44d9-b3d3-a6183fb1c9fb" />
          <br>
  </details>

  <details>
    <summary>2. 공연 상세 조회 (공연 PK, 공연명, 일정 등)</summary>

  - 프로시저  
      <br>
      <img width="1006" alt="스크린샷 2025-07-08 오후 4 42 18" src="https://github.com/user-attachments/assets/e23ef69f-25c5-478b-81a6-28680d7972d4" />
      <br>
    - 실행 결과  
      - "뮤직밤 클래식" 상세정보  
        <br>
        <img width="1012" alt="스크린샷 2025-07-08 오후 4 42 34" src="https://github.com/user-attachments/assets/b6041775-6a9a-4695-89b5-fd2590d5f4bc" />
        <br>
        
  </details>
</details>

<details>
  <summary>3. 예매</summary>

  <details>
    <summary>1. 공연 예매 등록 (회원, 공연, 좌석, 예매일 등)</summary>

  - 예매 등록 프로시저  
      <br>
      <img width="1014" alt="스크린샷 2025-07-08 오후 4 43 10" src="https://github.com/user-attachments/assets/1b53787b-c133-495b-af40-72bb25a5acea" />
      <br>

    - 실행 결과 ( 1번 회원의 티켓을 등록)  
      <br>
      <img width="974" alt="스크린샷 2025-07-08 오후 4 43 25" src="https://github.com/user-attachments/assets/61c93cdc-8723-43ec-9230-a8e188ced48f" />
      <br>
  </details>

  <details>
    <summary>2. 특정 사용자의 예매 내역 전체 조회</summary>

  - 프로시저  
      <br>
      <img width="1018" alt="스크린샷 2025-07-08 오후 4 43 50" src="https://github.com/user-attachments/assets/0be11ddf-c3a1-4da3-a10b-07b0961e8b2d" />
      <br>
  - 실행 결과( 1번 회원의 모든 예매 내역 조회)  
      <br>
      <img width="771" alt="스크린샷 2025-07-08 오후 4 44 02" src="https://github.com/user-attachments/assets/19e6157c-0704-4e3b-b80b-953810746308" />
      <br>
  </details>

  <details>
    <summary>3. 내가 등록한 예매 삭제하기</summary>

  - 프로시저  
      <br>
      <img width="979" alt="스크린샷 2025-07-08 오후 4 44 30" src="https://github.com/user-attachments/assets/7f0365b3-2028-4336-95a8-9d6c6df5a392" />
      <br>
- 실행 결과( 1번 회원의 모든 예매 삭제)  
      <br>
      <img width="1010" alt="스크린샷 2025-07-08 오후 4 44 55" src="https://github.com/user-attachments/assets/4df27e43-19a9-45bd-a1e4-197384d95875" />
      <br>
  </details>

  <details>
    <summary>4. 내가 등록한 예매 수정</summary>

  - 기존 데이터  
      <br>
      (이미지)
      <br>
  - 프로시저  
      <br>
      (이미지)
      <br>
  - 실행 결과  
      <br>
      (이미지)
      <br>
  - 중복 예매 시 실행 결과  
      <br>
      (이미지)
      <br>
  </details>
</details>

<details>
  <summary>4. 북마크</summary>

  <details>
    <summary>1. 공연 북마크 등록</summary>

  - 프로시저  
      <br>
      <img width="1011" alt="스크린샷 2025-07-08 오후 4 45 15" src="https://github.com/user-attachments/assets/87bdf17a-7955-491f-84f5-198f2c616f1d" />
      <br>
  - 실행 결과(1번 유저의 3번 공연 북마크 추가) 
      <br>
      <img width="927" alt="스크린샷 2025-07-08 오후 4 45 33" src="https://github.com/user-attachments/assets/b20d64cb-80a2-4920-aedc-7029900ae60c" />
      <br>

  </details>

  <details>
    <summary>2. 회원별 북마크 내역 전체 조회</summary>

  - 프로시저  
      <br>
      <img width="865" alt="스크린샷 2025-07-08 오후 4 45 56" src="https://github.com/user-attachments/assets/b8af7188-10a3-4ae4-9fc0-aeba3362a4fc" />
      <br>

  - 실행 결과(1번 회원이 등록한 모든 북마크 내역 조회 )
      <br>
      <img width="1024" alt="스크린샷 2025-07-08 오후 4 46 11" src="https://github.com/user-attachments/assets/7288fcf8-88d0-470b-b779-a2f43bb86527" />
      <br>
  </details>

  <details>
    <summary>3. 공연 북마크 해체</summary>

  - 프로시저  
      <br>
      <img width="1012" alt="스크린샷 2025-07-08 오후 4 46 25" src="https://github.com/user-attachments/assets/35e16876-d27b-46a9-bf84-8f72e42ed86a" />
      <br>
  - 실행 결과( 1번 회원의  3번 공연 북마크 삭제)
      <br>
      <img width="984" alt="스크린샷 2025-07-08 오후 4 46 43" src="https://github.com/user-attachments/assets/85e529cc-5665-488c-874c-756b08cdf7fc" />
      <br>
  </details>
</details>

<details>
  <summary>5. 리뷰</summary>

  <details>
    <summary>1. 공연 리뷰 등록 (별점, 한줄평, 사진 등)</summary>

  - 프로시저  
      <br>
      <img width="1019" alt="스크린샷 2025-07-08 오후 4 48 57" src="https://github.com/user-attachments/assets/09d8f9d6-8b6b-4fbf-846a-f09d99146c8e" />
      <br>
  - 실행 결과( 1번 회원의 리뷰 작성)  
      <br>
      <img width="914" alt="스크린샷 2025-07-08 오후 4 49 16" src="https://github.com/user-attachments/assets/74fa7b6c-053c-4a93-a795-1d3f08832f75" />
      <br>
  </details>

  <details>
    <summary>2. 내 리뷰 확인하기 (모든 리뷰 보기)</summary>

  - 프로시저  
      <br>
      <img width="702" alt="스크린샷 2025-07-08 오후 4 49 31" src="https://github.com/user-attachments/assets/d954d2d1-8b8a-4419-be0a-339f5750c052" />
      <br>
  - 실행 결과( 1번 회원의 리뷰 목록 확인하기)  
      <br>
      <img width="1015" alt="스크린샷 2025-07-08 오후 4 50 17" src="https://github.com/user-attachments/assets/bf4c21d1-1670-4502-b98e-b36c2b5a101d" />
      <br>
  </details>

  <details>
    <summary>3. 좋아요/싫어요 많은 순으로 정렬</summary>

  - 좋아요 순 정렬
      - 프로시저  
        <br>
        ![image](https://github.com/user-attachments/assets/04bafb34-72d1-467c-8f30-f625bf40c054)
        <br>
      - 결과  
        <br>
        ![image](https://github.com/user-attachments/assets/0785aee1-1df8-4212-8f43-4bf47021e547)
        <br>
  - 싫어요 순 정렬
      - 프로시저
        <br>
        ![image](https://github.com/user-attachments/assets/1a5c2d8c-8b5e-4b70-b7eb-5e5fdac06036)
        <br>
      - 결과  
        <br>
        ![image](https://github.com/user-attachments/assets/10404264-4629-412a-850a-8927f1bf046d)
        <br>
        </details>
  <details>
    <summary>4. 리뷰 삭제</summary>

  - 프로시저  
      <br>
      (이미지)
      <br>
  - 실행 결과  
      <br>
      (이미지)
      <br>
  </details>

  <details>
    <summary>5. 리뷰 좋아요/싫어요</summary>

  - 프로시저  
      <br>
      (이미지)
      <br>
  - 실행 결과  
      <br>
      (이미지)
      <br>
  </details>
</details>

<details>
  <summary>6. 관심사</summary>

  <details>
    <summary>1. 회원의 관심 장르 등록/수정</summary>

  - 변경 전  
      <br>
     ![image](https://github.com/user-attachments/assets/72f0ba0b-1ec4-4c50-8f4b-2708019946ff)
      <br>
  - 프로시저  
      <br>
      ![image](https://github.com/user-attachments/assets/3357a774-40cf-46b7-a473-2f4c7b587f19)
      <br>
  - 변경 후  
      <br>
      ![image](https://github.com/user-attachments/assets/3d586402-0743-459a-8dcd-b4e88e312844)
      <br>
  </details>

  <details>
    <summary>2. 회원의 관심 퍼포머 등록/수정</summary>

  - 변경 전  
      <br>
      ![image](https://github.com/user-attachments/assets/c269e890-0c70-451c-8f78-bf2224f9b724)
      <br>
  - 프로시저  
      <br>
      ![image](https://github.com/user-attachments/assets/3ca4dd29-7b1d-49ab-805f-0f0f3f3065e5)
      <br>
  - 변경 후  
      <br>
      ![image](https://github.com/user-attachments/assets/787fbb7c-70d8-474c-bf7c-41524613c244)
      <br>
  </details>
</details>

<details>
  <summary>7. 알림</summary>

  <details>
    <summary>1. 알림 등록</summary>

  - 변경 전  
      <br>
      ![image](https://github.com/user-attachments/assets/e447d959-f426-40b1-830b-662999844f40)
      <br>
  - 프로시저  
      <br>
      ![image](https://github.com/user-attachments/assets/663ab5d4-5927-4956-a6a6-f72aa01c5cae)
      <br>
  - 새 알림 등록  
      <br>
      ![image](https://github.com/user-attachments/assets/fdb5a037-86b7-4982-9c33-41a9439a6db6)
      <br>
  </details>

  <details>
    <summary>2. 알림 전체 조회</summary>

  - 프로시저  
      <br>
      (이미지)
      <br>
  - 기능  
      <br>
      (이미지)
      <br>
  </details>

  <details>
    <summary>3. 예매한 공연의 하루 전 날 알림 발송</summary>

  - 공연 시작 날짜  
      <br>
      ![image](https://github.com/user-attachments/assets/f0eeb504-93cf-495f-b434-0d116167d3a9)
      <br>
    - 프로시저  
      <br>
      ![image (1)](https://github.com/user-attachments/assets/1b838ea4-fe90-44c8-b532-1c9d3e477ee5)
      <br>
    - 결과  
      <br>
      ![image (2)](https://github.com/user-attachments/assets/dd3c987b-39be-4f86-b215-e8496a6f122b)
      <br>
  </details>


  <details>
    <summary>4. 예매 당일 공연 시작 전 알림 발송</summary>

  - 공연 시작 시간  
      <br>
      ![image (3)](https://github.com/user-attachments/assets/5743a569-8f1a-471f-bec3-d80ca4cbe84b)
      <br>
    - 프로시저  
      <br>
      ![image (4)](https://github.com/user-attachments/assets/c8324a32-a4d3-4a28-a7fe-ad27e30e5bdf)
      <br>
    - 결과  
      <br>
      ![image (5)](https://github.com/user-attachments/assets/367dd162-2854-4260-be9b-8995be1b45ab)
      <br>
  </details>

  <details>
    <summary>5. 북마크 공연 티켓팅 하루 전 알림 발송</summary>

  - 티켓팅 시작일  
      <br>
      ![image (6)](https://github.com/user-attachments/assets/6a681971-d900-4ef2-8cc9-809f4c53ac2f)
      <br>
    - 프로시저  
      <br>
      ![image (7)](https://github.com/user-attachments/assets/97971195-2831-47eb-8e9b-e8a9e96d0899)
      <br>
    - 결과  
      <br>
      ![image (8)](https://github.com/user-attachments/assets/8770af37-faa9-4cd9-93fd-ffa584ffe066)
      <br>
  </details>
</details>

<details>
  <summary>8. 추천</summary>

  <details>
    <summary>1. 좋아하는 장르의 공연 추천</summary>

  - 프로시저  
      <br>
      (이미지)
      <br>
  - 결과  
      <br>
      (이미지)
      <br>
  </details>

  <details>
    <summary>2. 좋아하는 퍼포머의 공연 정보 추천</summary>

  - 프로시저  
      <br>
      (이미지)
      <br>
  - 결과  
      <br>
      (이미지)
      <br>
  </details>
</details>



---
## **9. 회고**
