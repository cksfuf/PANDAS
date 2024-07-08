## numpy
- ndarray 생성
- 자료형
- 연산
- 인덱싱, 슬라이싱
- bool 값으로 선택
- 팬시 인덱싱
- 전치행렬
- 난수생성
- 데이터 시각화

### numpy 문과 행렬이해하자.

### query
- .head(): 파일 첫 5개 데이터 확인
- .tial(): 파일 마지막 5개 데이터 확인
- .info(): 컬럼명, Null값, 데이터 타입 등 확인
- .value_counts(): 컬럼의 세로줄 데이터 개수를 셈
- .info(): 컬럼이름, 널값, 데이터 타입 확인
- .sort(): 내림차순
	- .sort_index(ascending=False): 인덱스 기준으로 오름차순 정렬
	- .sort_values('age'): 나이를 기준으로 내림차순 정렬
	- .sort_values(['fare', 'age']): fare 과 age를 기준으로 정렬
- .loc[]: 특정 위치 찾아줌.
	- .loc[3, 'class']: 3번째 인덱스의 '클래스' 변수 값
	- .loc[2:5, ['age', 'fare']]: 2~5번 인덱스의 age와 fare 값을 보여줌.

- .loc의 활용
	- df = sns.load_dataset('titanic'): 타이타닉 자료
	- 자료에서 who 값이 man 인 데이터 age에 100값 할당
	```python
	c1 = df['who'] == 'man'
	df.loc[c1, 'age'] = 100
	```

	- 조건 2개 만들기
	- 자료에서 fare 값이 30이 넘고, who 가 man인 전체 값
	```python
	c1 = df['who'] == 'man'
	c2 = df['fare'] > 30
	df.loc[c1 & c2]
	```
- .where(): 특정 조건 찾기
	- df['fare'].where(df['fare'] < 30, 1).tail()
	- > df데이터 의 fare 열 중 30 이하인 값을 True로, False 인 값은 1로 변환.