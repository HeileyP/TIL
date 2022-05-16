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
