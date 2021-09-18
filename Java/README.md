- Java
  - [JDBC](#JDBC)


# JDBC
자바에서 DB 프로그래밍을 하기 위해 사용되는 API  

JDBC API가 없던 때는 DB 종류마다 각각의 SQL문을 사용 
메서드나 전역변수 등을 통합하는 문법으로 통일시킨 것이 JDBC  

### 구조 
자바(웹) 애플리케이션 -> JDBC API -> JDBC 드라이버 -> DB  
1. 드라이브 로딩  
`Class.forName(DRIVER);  `
2. DB 연결 (커넥션 얻기)  
`Connection conn = DriverManager.getConnection(URLS, USER, PWD);  `
3. 쿼리 준비  
`PreparedStatement psmt = conn.prepareStatement(SQL);  `
4. 쿼리 실행 (CRUD)  
`ResultSet rs = psmt.executeQuery();  `  
`int count = psmt.executeUpdate();  `
5. 쿼리 결과 가져오기  
`
while(rs.next()){  
  int a = rs.getInt(1);  
  String b = rs.getString(2);  
}`  
6. 닫기  
`rs.close();  `  
`psmt.close();  `  
`conn.close();  `

*** 

# DBMS
다수의 사용자가 DB 내의 데이터에 접근할 수 있도로 지원하는 소프트웨어 도구이며 데이터 관리시스템
