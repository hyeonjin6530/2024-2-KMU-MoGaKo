# [[BOJ]10773](https://www.acmicpc.net/problem/10773)

## 풀이
첫 번째 줄에 정수 K가 주어진다. (1 ≤ K ≤ 100,000)
이후 K개의 줄에 정수가 1개씩 주어진다. 정수는 0에서 1,000,000 사이의 값을 가지며, 정수가 "0" 일 경우에는 가장 최근에 쓴 수를 지우고, 아닐 경우 해당 수를 쓴다.
정수가 "0"일 경우에 지울 수 있는 수가 있음을 보장할 수 있다.

K 만큼 반복을 한다. num이 0이 아니면 l 리스트에 추가하고, num이 0이면 l 리스트의 마지막 요소를 제거한다.
이후 sum해서 결과 출력
## 전체 코드
```Python
l = []
for i in range(int(input())):
    num = int(input())
    l.append(num) if num != 0 else l.pop()
print(sum(l))
```

# [[BOJ]2750](https://www.acmicpc.net/problem/2750)

## 풀이

첫째 줄에 수의 개수 N(1 ≤ N ≤ 1,000)이 주어진다. 둘째 줄부터 N개의 줄에는 수가 주어진다. 이 수는 절댓값이 1,000보다 작거나 같은 정수이다. 수는 중복되지 않는다.

입력받고 정렬한 후에 출력한다.


## 전체 코드
```Python
n=int(input())
l=[]
for i in range(n):
    l.append(int(input()))
l.sort()
for i in l:
    print(i)
```
