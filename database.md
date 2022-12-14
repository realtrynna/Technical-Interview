# 데이터베이스
<br>

### 데이터베이스
일정한 규칙을 통해 구조화되어 저장되는 데이터의 모음집이다. <br>
DBMS는 데이터베이스를 제어하고 관리하는 시스템을 의미하며 데이터들은 DBMS마다 정의된 언어를 통해 조작할 수 있다. <br>

<br>

### 데이터베이스 특징
1. 실시간 접근성 <br>
비정형적인 질의에 실시간 처리에 의한 응답이 가능해야 한다.

<br>

2. 지속적인 변화 <br>
데이터베이스의 상태는 동적이다. <br>
새로운 데이터의 삽입 삭제 갱신으로 최신 데이터를 유지해야 한다.

<br>

3. 동시 공용 <br>
데이터베이스는 서로 다른 목적을 가진 응용자들이 사용한다. <br>
다수의 사용자가 동시에 동일한 내용의 데이터를 이용할 수 있어야 한다. <br>

<br>

4. 내용에 의한 참조 <br>
데이터 참조 시 레코드의 주소나 위치가 아닌 사용자가 정의하는 데이터의 내용으로 찾아져야 한다. 

<br>

### 데이터베이스 무결성 
데이터의 정확성 일관성 유효성이 유지되는 상태를 의미한다. <br>

1. 개체 무결성 <br>
기본 키는 중복되지 않으며 NULL 값일 수 없다. <br>

<br>

2. 참조 무결성 <br>
외래 키는 기본 키에 종속돼야 하며 NULL 값일 수 없다.

<br>

3. 도메인 무결성 <br>
특정 속성에 대해 고유값을 가지도록 조건이 주어진 경우 해당 속성값은 모두 고유해야 한다. <br>

<br>

### 관계형 비관계형
1. 관계형 데이터베이스 <br>
스키마를 가지며 행과 열로 이루어진 데이터베이스이다. <br>
장점으로 구조화된 데이터를 관리하므로 데이터의 정합성을 보장할 수 있다. <br>
단점으로 시스템이 커질수록 쿼리가 복잡해지고 성능 저하가 발생할 수 있다. <br>

<br>

2. 비관계형 데이터베이스 <br>
스키마가 없으며 데이터는 Key-Value 형태로 저장된다. <br>
장점으로 스키마가 없어 조회 삽입 성능이 좋다. <br>
단점으로 데이터의 구조를 보장하지 않아 데이터 구조 결정에 어려움이 있다. <br>

<br>

### 옵티마이저
쿼리 실행 계획을 생성하는 내부 엔진이다. <br>

* 쿼리 실행 단계 
1. 파스 트리 생성 <br>
내부 엔진이 이해할 수 있는 수준으로 쿼리문을 파싱 하여 파스 트리를 생성한다. <br>

<br>

2. 파스 트리 참조 <br>
생성된 파스 트리를 참조해 실행 계획을 수립한다. <br>

<br>

3. 스토리지 엔진 <br>
수립된 실행 계획에 따라 레코드를 읽어 작업을 수행한다. <br>

<br>

* 쿼리 실행 규칙
1. 규칙 기반 최적화 <br>
테이블의 레코드 수나 선택도 등을 고려하지 않고 옵티마이저 내부에 내장된 우선순위에 따라 실행 계획을 수립한다. 데이터의 분포도는 매우 다양하므로 현재는 많은 관계형 데이터베이스에서 사용하지 않는다. <br>

<br>

2. 비용 기반 최적화 <br>
쿼리문 처리를 위해 여러 방법 생성해 각 작업의 비용의 정도와 대상 테이블의 통계 정보를 이용해 각 실행 계획의 비용을 산출한다. 생성된 정보 중 가장 비용이 적은 계획으로 실행한다. <br>

<br>

### 이상 현상
올바르지 않은 테이블 설계로 인해 발생하는 논리적 오류를 의미한다. <br>

1. 삽입 이상 <br>
데이터 삽입 시 속성에 해당하는 값이 없어 NULL 값이 삽입되는 현상. <br>

<br>

2. 갱신 이상 <br>
중복된 데이터 중 일부만 수정되어 데이터 모순이 일어나는 현상. <br>

<br>

3. 삭제 이상 <br>
하나의 데이터 삭제 시 의도하지 않은 데이터까지 삭제되는 현상. <br>

<br>

### 질의 구조 언어
1. DDL <br>
데이터베이스의 구조를 정의한다. (Create, Drop, Alter, Truncate) <br>

<br>

2. DML <br>
데이터베이스 내부의 데이터를 조작한다. (Select, Insert, Update, Delete) <br>

<br>

3. DCL <br>
데이터베이스의 관리와 무결성을 유지한다. (Grant, Revoke) <br>

<br>

### 정규화
릴레이션을 여러 개로 분리하는 과정을 의미한다. <br>
불필요한 데이터를 제거하고 이상 현상을 해결하기 위해 실행한다. <br>

* 정규형 원칙 <br>
하나의 릴레이션은 하나의 의미만 가져야 한다. <br>
각각의 릴레이션은 독립적인 표현이 가능해야 한다. <br>

* 릴레이션의 분해로 릴레이션 간의 연산이 증가해 성능 저하가 발생할 수 있다. <br>

<br>

1. 제1 정규형 <br>
테이블의 컬럼이 원자 값을 갖도록 테이블을 분해한다. <br>

2. 제2 정규형 <br>
제1 정규형을 만족하고 테이블에 대해 완전 함수 종속을 만족하도록 테이블을 분해한다. <br>

* 완전 함수 종속 <br>
기본 키의 부분 집합이 결정자가 되어선 안된다는 걸 의미한다. <br>

<br>

3. 제3 정규형 <br>
제2 정규형을 만족하고 테이블에 대해 이행적 종속을 없애도록 테이블을 분해한다. <br>

<br>

### 비정규화
하나 이상의 테이블에 데이터를 중복으로 배치하는 과정을 의미한다. <br>

> 읽기 작업의 성능이 저하되었을 경우 사용한다. <br>
> 과도한 비정규화는 데이터베이스의 무결성이 조각날 수 있다. <br>

<br>

### SQL Injection
악의적인 쿼리 문을 삽입해 데이터베이스를 비정상적으로 조작하는 코드 인젝션 기법이다. 
<br>

* 방지 <br>
> 사용자의 입력값이 쿼리 문의 동적으로 영향을 주는 경우 개발자가 의도한 값인지 검사해야 한다. 
<br>
> 저장 프로시저를 활용해 쿼리의 형식을 지정하여 지정한 형식이 아닐 경우 쿼리 문이 실행되지 않도록 설정한다. 
<br>

<br>

### 인덱스
테이블의 검색과 정렬 작업의 속도를 향상시킬 수 있는 자료구조다. <br>

* 장점 <br>
테이블 조회 성능이 향상된다. <br>
전반적인 시스템의 부하를 줄일 수 있다. <br>

<br>

* 단점 <br>
인덱스를 관리하기 위해 약 10%에 데이터베이스 저장 공간이 필요하다. <br>
인덱스의 사용이 올바르지 않을 경우 성능 저하가 발생한다. <br>

<br>

* 인덱스 사용 <br>
1. 데이터가 많은 테이블 <br>
2. Insert Update Delete 작업이 발생하지 않는 컬럼 <br>
3. JOIN WHERE ORDER BY에 자주 사용되는 컬럼 <br>
4. 카디널리티가 높은 경우 <br>

### 락
1. 공유 락 <br>
읽기 작업 시 사용되는 락이다. <br>
여러 사용자가 동시에 데이터를 읽어도 일관성에 영향을 주지 않아 동시에 접근이 가능하다. <br> 공유 락이 설정돼있는 동안 베타 락은 사용할 수 없다. <br>

<br>

2. 베타 락 <br>
데이터 변경 시 사용되는 락이다. <br>
베타 락이 해제될 시점까지 다른 트랜잭션은 접근할 수 없다. <br>
베타 락은 트랜잭션 완료 시까지 유지된다. <br>

<br>

### 조인
테이블을 결합하는 연산 작업이다. <br>

1. 이너 조인 <br>
테이블 간 공통 컬럼을 이용해 컬럼 값이 같은 레코드를 출력한다. <br>
조건이 만족하는 레코드가 존재하는 경우에만 레코드가 반환된다. <br>

<br>

2. 아우터 조인 <br>
기준 테이블에 레코드가 모두 출력되며 조건에 맞는 레코드가 없을 경우 NULL 값을 출력한다. <br>

<br>

### 조인 원리
1. 중첩 루프 조인 (Nested Loop Join) <br>
반복 문과 같은 원리로 조건에 맞는 조인을 하는 방법이다. <br>
랜덤 접근에 대한 비용이 증가하므로 대용량의 테이블에서는 사용하지 않는다. <br>

<br>

2. 정렬 병합 조인 (Sort Merge Join)
각각의 테이블을 조인할 필드를 기준으로 정렬하고 정렬이 끝난 후에 조인을 하는 방법이다. <br> 대용량의 테이블 또는 적절한 인덱스가 없을 경우 사용한다. <br>

<br>

3. 해시 조인 (Hash Join) <br>
조인될 두 테이블 중 하나를 해시 테이블로 설정해 조인될 테이블의 조인 키 값을 해시 알고리즘으로 비교하여 매치되는 결과값을 얻는 조인이다. <br>

<br>

### Truncate Drop Delete
1. Truncate <br>
테이블 생성 초기 단계로 돌아간다. <br>
데이터와 인덱스가 삭제되며 Rollback이 불가능하다. <br>

<br>

2. Drop <br>
테이블이 삭제되며 Rollback이 불가능하다. <br>

<br>

3. Delete <br>
원하는 데이터를 삭제하고 Rollback이 가능하다. <br>

<br>

### GROUP BY
특정 컬럼을 기준으로 연산한 결과를 집계 키로 정의하여 그룹핑한다. <br>

<br>

### WHERE HAVING
1. WHERE <br>
그룹화 또는 집계가 발생되기 전 필터링한다. <br>

<br>

2. HAVING <br>
그룹화 또는 집계가 발생된 후 필터링한다. <br>

> 집계 함수는 HAVING 절과 같이 사용할 수 있지만 WHERE 절과는 사용할 수 없다. <br>

<br>

### ON WHERE
ON이 WHERE 절보다 먼저 실행되며 ON은 JOIN 되기 전 필터링을 하며 WHERE는 JOIN 되고 난 후 필터링한다. <br>

* 쿼리 실행 순서 
1. SELECT <br>
2. FROM <br>
3. WHERE <br>
4. GROUP BY <br>
5. ORDER BY <br>

<br>

### 트랜잭션
하나의 논리적 기능을 수행하기 위한 작업의 단위를 의미한다. <br>

* 트랜잭션 특징
1. 원자성 <br>
작업이 모두 반영되거나 반영되지 않아야 한다. <br>

2. 일관성 <br>
트랜잭션이 완료되면 데이터베이스는 언제나 일관성 있는 상태를 유지해야 한다. <br>

3. 독립성 <br>
둘 이상의 트랜잭션이 동시에 실행될 경우 서로는 서로의 작업에 끼어들 수 없다. <br>

4. 지속성 <br>
트랜잭션이 완료의 결과는 데이터베이스에 영구적으로 저장되어야 한다. <br>

<br>

### 트랜잭션 격리 수준
트랜잭션의 고립 정도를 의미하며 일관성과 동시성 제어 문제를 해결하기 위해 사용한다. <br>

1. UN_COMMITTED READ <br>
트랜잭션의 COMMIT이 완료되지 않은 상태에서 다른 트랜잭션이 접근하는 격리 수준 <br>

> Dirty Read, Non Repeatable Read, Phantom Read 문제 발생 <br>

2. COMMITTED READ <br>
트랜잭션 COMMIT이 완료된 경우에만 다른 트랜잭션이 접근하는 격리 수준 <br>

> Non Repeatable Read, Phantom Read 문제 발생 <br>

3. REPEATABLE READ <br>
트랜잭션 시작 전 COMMIT된 내용에 대해서만 접근하는 격리 수준 <br>

> Phantom Read 문제 발생 <br>

4. SERIALIZABLE <br>
트랜잭션이 순차적으로 실행되는 격리 수준 <br>

<br>

### 트랜잭션 격리 수준에 따른 문제점
1. Dirty Read (더티 리드) <br>
트랜잭션 COMMIT이 완료되지 않았음에도 다른 트랜잭션이 접근 가능한 경우 <br>

> A의 나이가 29에서 30으로 변경된 내용이 COMMIT 되기 전 B가 조회했을 경우 30으로 나오는 경우를 의미 <br>

<br>

2. Non Repeatable Read (반복 가능하지 않은 조회) <br>
트랜잭션 내에서 같은 쿼리가 두 번 이상 실행될 경우 그 결과가 다른 문제 <br>

<br>

3. Phantom Read (팬텀 리드) <br>
트랜잭션 내에서 동일한 레코드를 두 번 읽었을 경우 그 결과가 다른 문제 <br>

> Non Repeatable Read와 다른 점은 Non Repeatable Read는 레코드 값이 달라질 수 있지만 Phantom Read는 새로운 레코드가 선택될 수도 있다. <br>

<br>

### ORM
객체와 데이터베이스의 릴레이션을 매핑해주는 도구다. <br>
데이터베이스의 접근을 프로그래밍 언어 관점에서 바라볼 수 있다. <br>

* 장점
1. 데이터베이스가 변경되었을 경우 변경된 문법을 ORM이 커버 <br>
2. ORM은 독립적으로 작성되어 재사용 가능 <br>
3. 로우 쿼리의 절차적이고 순차적인 접근이 아닌 객체 지향 접근을 통해 생산성 증가 <br>

<br>

* 단점 <br>
프로젝트 규모가 커질 경우 난이도가 급격하게 올라감 <br>
설계가 제대로 되지 않은 경우 성능 저하와 일관성이 무너질 수 있음 <br>







