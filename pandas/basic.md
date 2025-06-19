# 📄 pandas 메서드 정리

`pandas`의 자주 사용되는 기능 및 메서드를 기능별로 정리한 문서입니다.  
각 항목에는 예제와 함께 핵심 메서드를 정리했습니다.


## 목차
- [📘1 기본 객체 생성](#1-기본-객체-생성)
  - [✅ Series](#-series)
  - [✅ DataFrame](#-dataframe)
- [🔍2 데이터 확인 메서드](#2-데이터-확인-메서드)
- [🎯 선택과 필터링](#-선택과-필터링)
- [✍️ 정렬 & 결측치 처리](#-정렬--결측치-처리)
- [🔁 GroupBy / Aggregation](#-groupby--aggregation)
- [🔧 열/행 추가 및 삭제](#-열행-추가-및-삭제)
- [🔗 데이터 결합](#-데이터-결합)
- [🌀 피벗과 변형](#-피벗과-변형)
- [🧽 문자열 메서드](#-문자열-메서드)
- [🧪 날짜 다루기](#-날짜-다루기)
- [📂 파일 입출력](#-파일-입출력)
- [📚 참고 문서](#-참고-문서)



---

## 📘1 기본 객체 생성

### ✅ Series
```python
import pandas as pd

s = pd.Series([1, 2, 3], index=['a', 'b', 'c'])
```

### ✅ DataFrame
```python
data = {
    '이름': ['Alice', 'Bob'],
    '나이': [25, 30],
    '점수': [90, 85]
}
df = pd.DataFrame(data)
```

---

## 🔍2 데이터 확인 메서드

| 메서드 | 설명 |
|--------|------|
| `df.head()` | 상위 5개 행 출력 |
| `df.tail()` | 하위 5개 행 출력 |
| `df.shape` | 행과 열의 개수 튜플 반환 |
| `df.info()` | 컬럼별 타입 및 결측값 등 요약 정보 |
| `df.describe()` | 수치형 통계 요약 |
| `df.columns` | 컬럼명 확인 |
| `df.index` | 인덱스 확인 |

---

## 🎯 선택과 필터링

```python
df['이름']        # 단일 컬럼 선택
df[['이름', '점수']]  # 여러 컬럼 선택
df.iloc[0]        # 행 인덱스로 접근
df.loc[0]         # 레이블 기반 접근
df[df['점수'] > 85]  # 조건 필터링
```

---

## ✍️ 정렬 & 결측치 처리

```python
df.sort_values('나이', ascending=False)    # 나이 내림차순 정렬
df.isnull().sum()                          # 결측치 개수
df.fillna(0)                               # 결측값 0으로 채우기
```

---

## 🔁 GroupBy / Aggregation

```python
df.groupby('이름')['점수'].mean()          # 이름별 점수 평균
df.groupby('이름').agg(['mean', 'max'])   # 여러 통계 적용
```

---

## 🔧 열/행 추가 및 삭제

```python
df['합격여부'] = df['점수'] >= 85          # 새로운 컬럼 추가
df.drop('나이', axis=1, inplace=True)      # 열 삭제
df.drop(0, axis=0, inplace=True)           # 행 삭제
```

---

## 🔗 데이터 결합

```python
pd.concat([df1, df2], axis=0)              # 행 기준 결합
pd.merge(df1, df2, on='공통컬럼')           # SQL-style 병합
```

---

## 🌀 피벗과 변형

```python
df.pivot(index='이름', columns='과목', values='점수')   # wide-format 피벗
df.melt(id_vars='이름')                                # wide → long 변환
```

---

## 🧽 문자열 메서드

```python
df['이름'].str.upper()           # 대문자 변환
df['이름'].str.contains('A')     # 특정 문자 포함 여부
```

---

## 🧪 날짜 다루기

```python
df['날짜'] = pd.to_datetime(df['날짜'])
df['날짜'].dt.year
df['날짜'].dt.dayofweek
```

---

## 📂 파일 입출력

```python
df.to_csv('파일이름.csv', index=False)
pd.read_csv('파일이름.csv')
```

---

## 📚 참고 문서

- [pandas 공식 문서](https://pandas.pydata.org/docs/)
- [10 minutes to pandas](h