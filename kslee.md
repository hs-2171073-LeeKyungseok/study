
# 이경석 - 무인 라면가게 인기 조합 저장 및 추천

### Apache의 predictionIO 오픈소스를 활용한 토핑 조합 정보 수집 및 추천 서비스

![image](https://user-images.githubusercontent.com/115882994/201883356-5438698e-263c-4b18-aaa4-4dbaba99b65d.png)

1. 사용 라이선스:  Apache 2 license
2. 사용 오픈소스
   > Apache Hadoop
   > Apache Spark
   > Elastic Search
   > PredictionIO
   ->Apache PredictionIO는 개발자, 데이터 과학자 및 최종 사용자를 위한 오픈 소스 기계 학습 프레임워크입니다. 이벤트 수집, 알고리즘 배포, 평가, REST API를 통한 예측 결과 쿼리를 지원      합니다. Hadoop, HBase(및 기타 DB), Elasticsearch, Spark와 같은 확장 가능한 오픈 소스 서비스를 기반으로 함.
  
3. 변경 사항
LICENSE.txt
https://github.com/apache/predictionio/blob/d9628ca2f148b45a51bf4cea68699a72f25cb383/LICENSE.txt
- 라이선스 정책에 의해 Elastic search가 더이상 apache 라이선스를 따르지 않게 됨에 따라 Elastic Search 오픈소스를 AWS의 OpenSearch 오픈소스로 교체하여 코드를 수정하여 사용을 하게 되었습니다. 이를 통해 자료 분석을 통한 조합을 수집하고 분석하는 부분에서 발생하는 문제를 수정하였습니다.(https://aws.amazon.com/ko/what-is/opensearch/)
- # ElasticSearch -> OpenSearch: OpenSearch는 AWS에서 ElasticSearch를 기반으로 Apache에서 만든 오픈소스입니다. ES에서 파생되어 같은 기능을 수행할 수 있음

4. 기능 부분
  1) 사람들이 주문을 하면서 추가하는 토핑에 대한 정보 저장
  2) 조합들을 비교해서 가장 인기가 있는 토핑에 대한 정보를 수집하고 저장
  3) 사용자가 주문을 할려고 할 때 가장 많이 팔리는(인기있는) 토핑에 대한 정보를 어플로 보내는 기능 수행 
 => 프리딕션IO를 통해 사용자로부터 받는 주문 정보를 수집하고 해당 데이터를 분석하여 인기있는 토핑들의 조합을 찾아내거나 단순 토핑을 추천해주고 이후에 어플을 통해 로그인을 하고 사용자로부터 정보를 받게 되었을 때 사용자의 기호에 따라 사용자에게 맞는 토핑을 추천해주는 기능을 제공한다. 
사용한 오픈소스: https://github.com/apache/predictionio
 
5.관련자료
http://hacks.mozilla.or.kr/2014/04/introducing-predictionio/
https://www.crunchbase.com/organization/prediction-io

6. (추가적인 내용 - 메인 오픈소스와 관련X)
-> 검색엔진이나 수집이 부족한 경우 해당 오픈소스를 추가로 사용할 수 있음
피노 - 방대한 양의 데이터를 수집하고 분석 (Apache에서 제작한 오픈소스)
ex) 자신의 사이트에 방문한 사람들 기록 -> 토핑을 구매한 사람들의 수를 기록 데이터를 가져오고 이를 코드를 만들어 사용자에게 제공한다.
https://github.com/apache/pinot#what-is-apache-pinot
