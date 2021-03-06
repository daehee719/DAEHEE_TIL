> inflearn - 이재규 선생님의 '**C++로 배우는 자료구조와 알고리즘** ' ([링크](https://url.kr/l3b1pr)) 참고
# 2022-02-23

## 1. 경험적 분석/수학적 분석

### 1-1
* 분석은 알고리즘을 정확히 **선택** 하기 위한 방법
* 시간 소요량 vs 공간 소요량
* 경험적 분석(Empirical Analysis)
  * 실제 코드를 작성 후, 실행하여 시간을 측정
  * 데이터 수를 다르게 하여 함수관계 유추
* 수학적 분석(Mathematical Analysis)
  * 알고리즘 자체를 가지고 수학적인 분석을 함.

## 2. 최악의 경우/최선의 경우

### 2-1 
* 최악의 경우 (Worst Case)
  * 가장 많은 시간과 자원을 필요로 하는 경우
* 최선의 경우 (Best Case)
  * 가장 적은 시간과 자원만이 소요되는 경우
* 평균적 경우(Average Case)
  * 개념이 모호함.
  * 자료의 균일 분포? 가장 많은 빈도의 경우?
### 2-2. 알고리즘 분석 예
```
void algorithm(int a[], int n)
{
  int i,j;
  for(i = 0; i < n; i++)
  {
    //이 for문을 실행하는 동안 c1의 시간이 걸림
    for(j = 0; j < i; j++)
    {
      //이 for문을 실행하는 동안 c2의 시간이 걸림
    }
  }
}
```
> 이걸 좀 많이 복잡하게 쓰면
```
T(N)
= c1 //첫번째 for문의 i가 0일 경우
+ (c1 + c2)//첫번째 for문의 i가 1일 경우
+ (c1 + c2 * 2)//첫번째 for문의 i가 2일 경우
+ (c1 + c2 * 3)//첫번째 for문의 i가 3일 경우
.
.
.
+ (c1 + c2 * (N - 1))//첫번째 for문의 i가 n(최대)일 경우
```
> 난 이 과정에서 시그마라는 개념을 익히게 되었다.
> 그리고 1부터 N - 1까지의 합이
> (N - 1) * (N)/2)라는 것도 깨달았다.
## 3. 알고리즘의 유형
![시간 복잡도](https://user-images.githubusercontent.com/81199906/155334103-ca375306-7275-4f0f-a936-ba9c34513bf4.png)
|1(상수)|log N|N|N log N|NxN|NxNxN|
|:------:|:---:|:---:|:---:|:----:|:----:|
|입력 자료 수와 관계 없이|Divide & Conquer 방법 사용 시|Scan 방법 사용 시|Divide & Conquer & Merge 방법 사용 시|이중루프|삼중루프
|일정한 실행시간이다.|이진 검색|선형 검색 등...|병합 정렬 등...|삽입정렬, 선택 정렬 등..|-|
|해쉬 검색 알고리즘 등..|이진 트리 검색 등...|-|-|-|-|



> ### 해시 검색이란
> ![해시 테이블](https://user-images.githubusercontent.com/81199906/155337992-84f003f1-22c2-49f1-82af-22aa6c3d1ce3.png)
> #### 간략한 설명으로는 (Key, Value)로 데이터를 저장하는 자료구조 중 하나이다.
> #### 해시 테이블이 빠른 검색 속도를 제공하는 이유는 내부적으로 배열(버킷)을 이용해서 데이터를 저장하기 때문이다.
> #### 해시 테이블은 각각의 Key값에 해시 함수를 적용해 고유한 index를 생성하고, 이 index를 활용해 값을 저장하거나 검색한다.
> #### 여기서 실제 값이 저장되는 장소를 **버킷** 또는 **슬롯**이라고 한다.
> #### 입력 자료수와 관계없이 일정한 실행시간을 유지하기 때문에 O(1) (상수) 이다.


> ### Divide & Conquer(분할 정복)이란?
> #### divide 와 conquer의 의미는 단어의 뜻대로 '나눠서 정복한다.'이다.
> #### 이것을 풀어서 설명하면 '해결하기 쉬운 단위로 나눠서 해결한 후 다시 합친다.'이다.
> #### 1. 일반적인 해결방법
> ![Divide And Conquer(분할 정복) 안한 해결방법](https://user-images.githubusercontent.com/81199906/155340693-b741f955-7812-45c7-8cb9-a53b1c9187f9.png)
> #### 연산을 총 7번 했기때문에 7의 시간이 걸린다.
> #### 2. Divide & Conquer을 적용한 해결방법
> ![Divide And Conquer(분할 정복) 해결 방법](https://user-images.githubusercontent.com/81199906/155340718-f9a9e030-81ac-474a-b092-cdd9800c0dfd.png)
> #### 여기에서 분할 정복의 강점을 알수 있다.
> #### 한 문제를 여러 문제로 나누어 한번에 해결하면 여러 문제들이 동시에(같은 시간 안에) 해결이 된다.
> #### 위와 같은 경우에 3번째 줄(3+2,7+8,5+8,10+4)가 같은 시간에 해결이 되고,
> #### 그 다음줄 (5+15,13+14)이 같은 시간에 해결이 되었고,
> #### 마지막으로 마지막줄(20+27)이 해결 되었으므로, 
> #### D부분을 나누는데 시간이 4보다 작다면, 분할 정복의 해결 방법이 더 효율적이란 것을 알 수 있다.
> #### ([Divid And Conquer](https://sinseonc.tistory.com/10)) 출처


> ### BT(이진 트리), BST(이진 탐색 트리)란?
> #### 이진 트리
> ![Binary Tree](https://user-images.githubusercontent.com/81199906/155343929-13121c5d-3ce2-4f43-813f-78039140a3e5.png)
> #### 1. 트리 중에서 가장 많이 쓰이는 트리가 이진트리이다. 
> #### 2. 모든 노드가 2개의 서브 트리를 가지고 있는 트리를 이진 트리(binary tree) 라고 한다. 
> #### 3. 서브트리는 공집합일 수 있다. 
> #### 4. 따라서 이진트리의 노드에는 최대 2개까지의 자식 노드가 존재할 수 있고 모든 노드의 차수가 2 이하가 된다.
> #### 이진 탐색 트리
> ![Binary Search Tree](https://user-images.githubusercontent.com/81199906/155343945-a5f744bf-e878-4e6f-b6af-3580847a84eb.png)
> #### 1. 어떤 노드 N을 기준으로 왼쪽 서브 트리 노드의 모든 키 값은 노드 N의 키 값보다 작아야 한다.
> #### 2. 오른쪽 서브트리 노드의 키 값은 노드 N의 키 값보다 커야한다.
> #### 3. 같은 키 값을 갖는 노드는 없다.(중복이 불가하다.)
## 4. 알고리즘 성능 표기법
### 4.1 알고리즘 성능 표기법(Big-Oh)
* 알고리즘의 성능을 객관적으로 표현하는 방법
* O 표기법 (Big-Oh Notation)
 * 실행기간 함수
 * 상한선을 기준으로 나타냄
 > 수학적인 정의를 이해 못했다..
