# Simple-Data-Analytics-Service


![image](https://github.com/KimJinung/Simple-Data-Analytics-Service/assets/111354195/2fa25579-b4ff-4ffe-aa93-fb5c40b70da5)

1. 트랜잭션 데이터는 RDS read replica를 사용한다. mySQL의 replica기능은 binlog를 기반으로 동작한다.
2. 로그 데이터는 firehose를 가지고 로우 데이터를 먼저 떨군다.
3. raw 버킷에 데이터 떨어지면 람다 트리거 태워서 전처리 및 파케이로 포맷 변경한다.
4. 글루 크롤러, 카탈로그 이용해서 지속적으로 테이블 스키마를 추적할 수 있게 한다.
5. 글루 etl로 트랜잭션 데이터와 로그 데이터를 말아서 redshift에 밀어 넣는다.
6. Bi, Query engine 솔루션을 통해 데이터 활용 할 수 있도록 제공
