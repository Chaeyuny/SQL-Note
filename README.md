# SQL-Note
업무하면서 알게 된 DB 지식 정리(Oracle) 


- 일하면서 바탕화면 메모지에 적어두고 활용했던 SQL 관련 지식
- 에러 발생 시 검색해서 해결했던 내용 포함
- 메모 내용 + 추가로 찾아보며 공부한 내용 정리


<h4>📌 힌트(hint) 사용 : 쿼리튜닝 </h4>
✔ 업무에서 가장 많이 활용되고 있었던 건 /*+parallel(4)*/, 때때로 /*+ordered use_nl(a b c)*/

 1)  /*+parallel(4)*/
    : 검색해서 나오는 건 정확히는 /*+ PARALLEL(table_name, degree)*/ 
      실제로 쓸때는 그냥 숫자만 기재해서 활용했다. select 바로 옆에 붙여서 실행하면 적용된다. 
         ex) select /*+parallel(4)*/ from table_name;
     
      쉽게 말해 병렬처리문인데, 숫자는 degree를 의미한다. 
      참고한 사이트 설명상으로는 '하나의 operation 수행에 대한 serever process 개수'라고 기재되어있고, degree에 영향을 주는 요인들도 다양하다. 
      나는 힌트 이름이 병렬처리이니 쉽게 말해 한사람이 할 작업을 넷이서 하게끔 속도를 높여주는 것이라고 이해했다. (쿼리문에 따라 속도가 무조건 높아지진 않는다) 
      그러므로 숫자를 너무 높이면 서버에 과부하를 줄 수 있으니 주의해야 한다. 
      
  
  2) /*+ordered use_nl(a b c)*/
    : 괄호 안의 a,b,c는 table alias이다. 힌트 이름에서 대충 짐작할 수 있듯이 조인 순서를



*참고사이트
      https://devuna.tistory.com/35
