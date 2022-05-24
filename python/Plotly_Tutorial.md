# Plotly
Plotly는 오픈소스 plotting Python 라이브러리입니다.
인터페이스가 Python이고 R일 뿐이지 JavaScript로 만들어졌습니다.
광범위한 통계, 재무, 지리, 과학 및 3차원을 다루고 있으며,
40개 이상의 다양한 차트를 만들고 동적인 시각화를 구성할 수 있습니다.
특히 JavaScript기반으로 만들어져 `한글폰트` 설정을 하지 않아도 됩니다.

* Jupyter notebook에서 display 가능
* standalone HTML files로 저장 가능
* Dash를 사용한 Python 기반 웹 어플리케이션의 일부로 제공

# plotly 환경설정
## Anaconda 가상환경에서 plotly 설치하기
```bash
conda install plotly
```
## Jupyter notebook에서 plotly 최신버전을 설치하기
```python
# plotly 최신버전을 사용해 주세요.
!pip install plotly --upgrade
```
```python
# plotly 라이브러리 불러오기
import plotly
# 버전확인
plotly.__version__
```

## plotyly의 모듈 불러오기
* Graph Objects: low-level interface to figures, traces and layout
* plotly.express: high-level interface for data visualization
```python
# plotly.express 모듈 불러오기
import plotly.express as px
```

# plotly 시계열 예제 따라하기 
[Time Series and Date Axes | Python | Plotly](https://plotly.com/python/time-series/)
```python
# plotly에 내장된 data.stocks 데이터를 불러옵니다.
df = px.data.stocks()
```
## 일별 수익률 그래프
일별 수익률 선 그래프로 그리기
*  plotly.line()
*  plotly에서의 plotting할 때 기본적으로 x,y를 지정해준다고 기억합니다.
```python
fig = px.line(df, x='date', y="GOOG", title="구글주가)
```
일별 수익률 막대 그래프로 그리기
*  plotly.bar()
```python
px.bar(df_1)
```
![newplot](https://user-images.githubusercontent.com/91872648/169939632-14569606-7535-435b-8ea5-f16d4b27cca2.png)
구글 일별 수익률 막대 그래프로 그리기
*  plotly.bar()
```python
df = px.data.stocks(indexed=True)-1
fig = px.bar(df, x=df.index, y="GOOG")
fig.show()
```
![newplot (2)](https://user-images.githubusercontent.com/91872648/169940057-f1b1cdfc-e5e1-4679-88d1-596d41ef1d85.png)

## facet_col 서브플롯
* 왜 columns의 name을 지정하나요?  
plotly 개발자가 컬럼의 이름을 지정하자고 약속하고 그 안에 개발자의 철학이 녹아져있는 것이다.
```python
# df_1.columns 의 name을 "company"로 지정하기
df_1.columns.name = "company"
```

px.area로 수익률 분포 그리기
* facet_col을 통해 서브플롯을 그릴 수 있습니다.
* facet_clo_wrap 한 줄에 몇 개의 그래프를 보여줄 것인가를 지정합니다.
```python
px.area(df_1, facet_col="company", facet_col_wrap=2)
```

* df_1로는 왜 hover 설정이 안되는건가요?
안 되는건 아니고 date 가 index 로 되어 있어서 컬럼으로 접근할 수 없습니다.

### 데이터 분석에 관한 지나가는 이야기
---
#### 스타벅스 매장위치 데이터와 인도 인구 조사 데이터를 이용하여 튜토리얼
https://coderzcolumn.com/tutorials/data-science/how-to-create-sunburst-chart-in-python-plotly
#### FACT FULLNESS 팩트풀니스를 아시나요?
우리가 세상을 오해하는 10가지 이유와 세상이 생각보다 괜찮은 이유
https://www.ted.com/talks/steven_pinker_is_the_world_getting_better_or_worse_a_look_at_the_numbers?language=ko 


