* 한국 주식 가격, 미국주식 가격, 지수, 환율, 암호화폐 가격, 종목 리스팅 등 금융 데이터 수집 라이브러리
* github: [FinanceData/FinanceDataReader: Financial data reader](https://github.com/FinanceData/FinanceDataReader)
* FinanceDataReader 사용자 안내서: [FinanceData](https://financedata.github.io/posts/finance-data-reader-users-guide.html)
* https://pandas-datareader.readthedocs.io/en/latest/readers/index.html

## 설치
```bash
!pip install -U finance-datareader
```
## 라이브러리 불러오기
```python
# 데이터 분석을 위해 pandas 불러오기
import pandas as pd

# FinanceDataReader 를 fdr 별칭으로 불러옵니다.
# 라이브러리의 version을 확인하고 싶을 때는 .__version__ 으로 확인합니다. 
import FinanceDataReader as fdr

fdr.__version__
```

## 한국거래소 상장종목 전체 가져오기
* KRX : KRX 종목 전체
* KOSPI : KOSPI 종목
* KOSDAQ : KOSDAQ 종목
* KONEX : KONEX 종목
* NASDAQ : 나스닥 종목
* NYSE : 뉴욕증권거래소 종목
* SP500 : S&P500 종목

```python
# 나스닥 종목 가져오기
df = fdr.StockListing('NASDAQ')
```
## 기술분석
```python
# 행과 열의 크기를 봅니다.
df.shape
```
```python
# 전체 데이터프레임의 요약정보를 봅니다.
df.info()
```
```python
# head 로 미리보기
df.head()
# tail 로 미리보기
df.tail()
```
```python
# 기술통계 값을 요약합니다.
df.describe(datetime_is_numeric=False)
```
## 파일로 저장하고 불러오기
```python
# to_csv로 Dataframe을 데이터 저장용 파일인 CSV 파일로 바꿀 수 있습니다.
df.to_csv("NASDAQ.csv")
```
```python
# CSV로 저장된 파일을 다시 DataFrame으로 읽어서 확인해 봅니다.
pd.read_csv("NASDAQ.csv", index_col=0)
```
