# Melon Playlist Continuation Apple Music Team
**개요 )** Word2Vec + LMF Models 를 결합해 추천 모델 구성.
메인코드는 Word2Vec을 사용하고, 추천 100곡을 다 채우지 못하면 LMF 모델을 사용해서 남은 곡을 채운다. 결과는 다음과 같다.
<img width="853" alt="스크린샷 2020-07-27 오전 11 14 46" src="https://user-images.githubusercontent.com/56217762/88497251-c4dfdb00-cffa-11ea-974e-a97c47b3b286.png">


> " 혹시 이런 음악/태그는 플레이리스트에 깜빡하고 들어가지 않은 건 아닐까? "

플레이리스트에 이미 들어간 곡과 태그를 바탕으로 들어갈 만한, 그러니까 플레이리스트에 들어가야 하는 데 미처 누락 됐을 법한 음악이나 태그를 예측한다는 개념으로 음악과 태그를 예측 방법을 선정했다. 



## How 2 use
(정선이 한테 물어보기 )
- Logistic Matrix Factorization model for songs



## MODELS 
**1. Word2Vec**
참고링크 : https://arena.kakao.com/forum/topics/232
카카오 아레나 포럼에 업로드 된 코드를 바탕으로 최종코드를 작성했다.


**2. LMF and BPR Models** 
BPR 참고 링크 :  https://arxiv.org/pdf/1205.2618.pdf
                            https://soobarkbar.tistory.com/147
LMF 참고 링크 : https://greeksharifa.github.io/machine_learning/2020/06/02/LMF/

**결과**
Baysian Personalized Rank(BPR) 방법보다 Logical Matrix Factorization (LMF)이 미세하게 결과가 더 좋고,
파라미터는 regulation =0.1, factors =50 일때 가장 실적이 뛰어났다. 

**[ LMF reg=0.1, factors=50 채점결과 ]**
곡nDCG | 태그nDCG 
0.085576 | 0.106127


## 개발과정스토리
- 태그 NLP 분석결과 : simple_tags branch 참고 
- Autoencoder 분석 시도 : sparse matrix branch 참고 


