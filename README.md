# 230610
이산수학 코드과제 4 동치 관계 판단 코드

# 동치 관계 확인 코드
관계 R이 set으로 주어졌을 때 관계 R이 동치 관계인지 판단하는 코드이다.

반사적 관계, 대칭적 관계, 추이적 관계가 모두 성립하는지를 확인하여  동치 관계를 판단할 수 있다.

# 설치, 실행
주어진 관계 R은 다음과 같다. 

R = {(1, 1), (1, 3), (2, 2), (3, 3),(3, 1), (3, 4), (4, 4), (4, 3)}

R이 동치 관계인 경우 True, 동치 관계가 아닌 경우 False가 나온다.

.py 파일을 다운받은 뒤 .py 파일을 colab에 업로드 후 다음 코드를 실행시킨다.
```python
! python3 202210725_이은서_코드과제4.py
```

# 코드 설명 
```python
def check_transitive(R):
    for (a, b) in R:
        for (c, d) in R:
            if b == c and (a, d) not in R:
                return False
    return True
```

- 추이적 : "aRb이고 bRc이면 aRc가 성립한다. 성립하지 않을시 False"

```python
def check_symmetric(R):
    for (a, b) in R:
        if (b, a) not in R:
            return False
    return True
```
- 대칭적 : "aRb가 성립하면 bRa도 성립한다. 성립하지 않을시 False "
```python
def check_reflexive(R):
    for a in set(x[0] for x in R):
        if (a, a) not in R:
            return False
    return True
```
- 반사적 :  "All x ∈ X, if (x,x)∈ R 성립하지 않을시 False "  

# 팀원
202210725 이은서
202210688 안혁진
