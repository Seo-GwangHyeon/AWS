Mongo DB
============
- Mongo DB 는 자바스크림트 문법을 사용하는 DB
- 또다른 특징은 스키마가 없다. (스키마란 데이터의 구조, SQL의 테이블과 유사)

AWS에 Mongo DB를 연결해서, Node.js와 Express를 이용해서 간단한 블로그 또는 게시판을 만들어 볼 것이다.

홈페이지 들어가면, cloud를 메인에 표시해놨는데, server를 설치해야한다.  

몽고DB를 node.js와 연결해보록하자
http://mongodb.github.io/node-mongodb-native/3.4/quick-start/quick-start/


Mongo DB의 기본 문법 정리

자바스크립트에서의 객체와 유사하게 DB를 관리하는 것으로 보인다.  

    db  
    
-> 현재 보고 있는 db명을 출력한다.

    use examples
    
-> examples 라는 db를 본다.

    db.inventory.insertMany([
      { item: "journal", qty: 25, status: "A", size: { h: 14, w: 21, uom: "cm" }, tags: [ "blank", "red" ] },
      { item: "notebook", qty: 50, status: "A", size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank" ] },
      { item: "paper", qty: 10, status: "D", size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank", "plain" ] },
      { item: "planner", qty: 0, status: "D", size: { h: 22.85, w: 30, uom: "cm" }, tags: [ "blank", "red" ] },
      { item: "postcard", qty: 45, status: "A", size: { h: 10, w: 15.25, uom: "cm" }, tags: [ "blue" ] }
    ]);
    
-> 데이터를 insert 한다.

    
    db.inventory.find({})
    
-> 모든 데이터를 select한다.

    db.inventory.find({}).pretty()
    
-> indent를 넣어서 beatify한 데이터를 보여준다.

    db.inventory.find( { status: "D" } );
    
-> 해당 조건의 데이터를 조회한다. status가 "D"인 모든 데이터
    
    db.inventory.find( {}, { _id: 0, item: 1, status: 1 } );    
    
-> 속성별로 데이터의 출력여부를 선택한다. 앞부분은 조건 뒷부분은 출력여부(0은 출력 X, 1은 출력 O)







