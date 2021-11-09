# project1_web

project1_web.py 에서는 튜토리얼 코드를 바탕으로 parsing 함수와 train 함수를 수정하여 accusary_score와 f1_score의 값을 상승하는 것을 목표로 작성하였습니다.

먼저 parsing 함수에서는 

            if l[:6]=='Pragma':

                continue


            if l[:10]=='User-Agent':

                continue


            if l[:10]=='Connection':

                continue

while문 안에 다음과 같은 조건을 추가하여 단어 벡터의 수를 줄이도록 하였습니다.

그리고 train 함수에서는 기존 코드에서 사용한 랜덤포레스트 함수 대신에 다른 분류 알고리즘인 knn 알고리즘을 사용하였습니다. 

kn = KNeighborsClassifier(n_neighbors=2, n_jobs=-1)

​    kn.fit(train_vec,train_y)

​    return kn

이때, n_neighborsd의 수는 1~11까지 score를 확인하였을때 가장 높은 값을 가지는 2를 사용하였습니다.

코드를 실행하였을때의 결과값은 다음과 같습니다.

```shell
❯ python3 project1_web.py     
0.971612168537498
0.9654489654489654
```
