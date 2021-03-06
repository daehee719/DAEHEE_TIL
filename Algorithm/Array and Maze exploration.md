> inflearn - 이재규 선생님의 '**C++로 배우는 자료구조와 알고리즘** ' ([링크](https://url.kr/l3b1pr)) 참고
# 날짜 - 2022-03-01
## 1. 배열의 정의와 사용법
### 1-1. C++의 배열 정의
* 배열
  * 연속된 메모리 공간을 차지하는 같은 타입의 데이터집합
  * 정적인 데이터타입으로 그 크기가 미리 정해져 있음
  * 배열의 인덱스 사용은 사용자의 책임
    * 인덱스는 0 ~ 크기 - 1 까지
    * 배열 자체에 크기 정보는 없다.
  * 데이터형 배열명[배열의 크기];
  ```
  int array[10]; // array[0] ~ array[9]
  int array2[5] = {1, 2, 3, 4, 5}; // 정의와 동시에 초기화
  ```
### 1-2. 배열과 포인터의 관계
* 배열의 이름은
 * 배열이 저장된 메모리의 선두를 가르키는 상수(constant) 포인터이다.
 * sizeof(array) == 20, sizeof(parray) == 4
 * 인덱스 연산자([])는
  * array[n]은 *(array + n) 과 같은 의미
 ```
 int array[5] = {1, 2, 3, 4, 5};
 
 array = array + 1; //error! 배열이름은 상수포인터로 변경 불가.
 int v1 = array[3];
 int v2 = *(array + 3); // array[3]과 같다.
 
 int *parray = array;
 parray = parray + 1;
 v1 = parray[3];
 v2 = *(parray + 3);
 ```
### 1-3. 함수에서 1차원 배열 사용
* C++의 배열은 크기정보가 없다.
  * 배열의 끝에 특정값을 넣는 방법
   * C++의 스트링 : 끝에 NULL값
 * 배열의 크기를 따로 지정하는 방법
 ```
 int average(int a[], int n) // 혹은 int average(int *a, int n)
{
	int sum = 0;
	for (int i = 0; i < n; i++)
	{
		sum += a[i];
	}
	return (sum / n);
}


int main()
{
	int array[5] = { 1, 2, 3, 4, 5 };
	int average = average(array, 5);
}
 ```
  
## 2. 다차원배열에 대한 이해
### 2-1. 다차원배열의 구조
* 다차원 배열의 정의
 * 인덱스 연산자를 차원 수 만큼 쓴다.
* array[3][3]에서
 * array[0],array[1],array[2]는 각각 세개짜리 정수배열을 가리킴.
 * sizeof(array[0]) == 12, sizeof(array[0][0]) == 4
 ```
 int main()
{
	int array[3][3] =
	{
		{1,2,3},  
		{4,5,6},
		{7,8,9}
	};
}
 ```
### 2-2. 다차원배열의 사용법
```
int average(int m[][3])
{
	int i, j;
	int sum = 0;
	for ( i = 0; i < 3; i++)
	{
		for ( j = 0; j < 3; j++)
		{
			sum += m[i][j];
		}
	}
	return sum / (3 * 3);
}


int main()
{
	int array[3][3] = {
		{1,2,3},
		{4,5,6},
		{7,8,9}
	};
	int averageRes = average(array);
	cout << averageRes << endl;
}
```


## 3. 미로탐색
### 3-1. 미로 탐색 알고리즘 : 우선법
* 우선법(Right Hand On Wall)
 * 갈림길을 만났을때 우선적으로 오른쪽으로 간다.
 * 오른손을 벽에 대고 가기
### 3-2. 최단경로 찾기
> 이 부분은 도대체 무슨 소리인지 이해가 잘 안간다.
