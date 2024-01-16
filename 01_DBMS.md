### Datatype:문자형/숫자형/날짜형
- DATE
- DATETIME
- TIME
- YEAR
- ...

### Database/Table
- Database는 데이터를 저장하는 저장소.
- 여러 Database를 만드는 이유는 접근 권한을 쉽게 나누기 위함.

#### CREATE TABLE
> CREATE TABLE customers(     </br>
    customer_number INT,      </br>
    customer_name VARCHAR(50),    </br>
    phone VARCHAR(50),     </br>
);

#### INSERT
> INSERT INTO 테이블이름 </br>
    (컬럼명1, 컬럼명2, 컬럼명3) </br>
VALUES </br>
    (DATA1, DATA2, DATA3) </br>
;
#### DELETE/TRUNCATE
- 둘 다 테이블을 지우는 쿼리.
- DELETE: 데이터삭제
- TRUNCATE: 테이블 초기화
- DELETE FROM '테이블이름'where~
- DELETE구문에서 where문을 생략하면 모든 데이터 삭제


#### UPDATE
- 이미 존재하는 TABLE의 내용을 수정
> UPDATE 테이블이름 </br>
SET 컬럼명1=DATA1, 컬럼명2=DATA2 </br>
WHERE 조건~~; 


#### ALTER TABLE 이름 변경
> ALTER TABLE '테이블명' RENAME '새이름' </br>
> ALTER TABLE customers RENAME newcustomers;


#### ALTER TABLE 컬럼 추가
> ALTER TABLE '테이블명' ADD '새이름' 데이터타입 </br>
> ALTER TABLE newcustomers ADD 지역 VARCHAR(50);


#### ALTER TABLE 컬럼 데이터 타입 변경
> ALTER TABLE '테이블명' MODIFY '컬럼명' 데이터타입; </br>
> ALTER TABLE newcustomers MODIFY 지역 INT;


#### ALTER TABLE 컬럼 이름 변경
> ALTER TABLE '테이블명' CHANGE '기존컬럼명' '새컬럼명' 데이터타입; </br>
> ALTER TABLE newcustomers CHANGE 지역 REGION VARCHAR(10);

#### ALTER TABLE 컬럼 삭제
> ALTER TABLE '테이블명' DROP '컬럼명';
> ALTER TABLE newcustomers DROP REGION;


### 데이터를 테이블에 넣는 방법
##### CSV가져오기
- 로컬 데이터 불러올 수 있게 설정값.
- SHOW GLOBAL VARIABLES LIKE 'LOCAL_INFILE';
- SET GLOBAL LOCAL_INFILE=TRUE;

### 데이터 불러오기

#### SELECT FROM
> SELECT * FROM 테이블명; (여기서 *는 모든 컬럼) </br>
> SELECT * FROM `newcustomers`; </br>
> SELECT customer_name, phone FROM `newcustomers`;


#### ALIAS(별칭)
> SELECT 컬럼명 AS 별칭 FROM 테이블명;
