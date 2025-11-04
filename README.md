# 🏙️ Vacant Houses in Seoul
서울시 자치구별 빈집 비율 분석 및 공간통계 프로젝트

## 📌 프로젝트 개요
이 프로젝트는 서울시 25개 자치구를 대상으로 **거주용·비거주용 빈집 비율**을 분석하고,  
도시의 사회·경제적 요인과 공간적 특성을 함께 고려하여 **빈집 발생의 구조적 원인**을 탐색하는 데 목적이 있습니다.

> 📊 데이터 전처리부터 통계 검정, 회귀 분석, 머신러닝, 공간통계까지 일련의 분석 과정을 Colab 환경에서 수행했습니다.

---

## 🧾 분석 내용 요약

| 구분 | 분석 내용 |
|------|------------|
| **데이터 수집 및 전처리** | 서울열린데이터광장, 통계청 자료 등을 기반으로 자치구별 CSV 데이터(빈집, 인구, 주택, 문화공간 등) 병합 및 파생변수 생성 |
| **통계 분석** | 정규성 검정, Levene 등분산 검정, Kruskal–Wallis 검정으로 권역 간 차이 분석 |
| **회귀 분석** | 베타회귀 (Beta Regression, Logit Link)로 거주용·비거주용 빈집비율 결정 요인 도출 |
| **머신러닝 분석** | RandomForest, XGBoost + SHAP 분석으로 변수 중요도 시각화 |
| **요인분석 / PCA** | 13개 독립변수를 3개 주요 요인(경제활동·인프라 / 사회·문화 / 주거환경·고령화)으로 축약 |
| **공간 분석 (LISA, Moran’s I)** | 자치구별 요인 점수를 바탕으로 공간자기상관(Local Moran’s I) 및 클러스터 지도 시각화 |

---

## 📂 주요 코드 파일

| 파일명 | 설명 |
|---------|------|
| `capstone1.ipynb` | Colab에서 실행한 메인 분석 코드 (데이터 병합 → 통계분석 → 베타회귀 → SHAP → LISA) |
| `거주용_빈집비율_베타회귀결과.csv` | 거주용 빈집 비율 회귀 결과 |
| `비거주용_빈집비율_베타회귀결과.csv` | 비거주용 빈집 비율 회귀 결과 |
| `corr_heatmap.png`, `*_bar.png` | 상관관계 및 SHAP 중요도 시각화 이미지 |
| `*_LISA_map.png`, `*_LISA_result.geojson` | 공간자기상관 분석 결과 시각화 및 GeoJSON 파일 |

---

## 🧠 주요 변수

| 변수명 | 설명 |
|--------|------|
| `노후주택비율` | 30년 이상 노후주택 비율 |
| `고령인구비율` | 65세 이상 인구 비율 |
| `인구밀도` | 자치구별 인구 밀도 |
| `순이동률` | 순이동 인구 비율 |
| `경제활동인구` | 경제활동 참여 인구수 |
| `교육만족도`, `문화공간` | 생활환경 관련 요인 |
| `노인복지시설수`, `1인가구수` | 복지 및 인구 구조 관련 변수 |

---

## 🧩 주요 분석 기법

- **Beta Regression (Logit link)** : 비율형 종속변수(빈집비율)에 적합한 회귀 모형  
- **Kruskal–Wallis Test** : 권역 간 차이 비모수 검정  
- **VIF (Variance Inflation Factor)** : 다중공선성 확인  
- **SHAP Analysis** : 변수 중요도 및 방향성 시각화  
- **Factor Analysis / PCA** : 변수 간 상관구조 축약  
- **Spatial Analysis (LISA / Moran’s I)** : 공간적 자기상관과 지역적 패턴 탐색  

---

## 🗺️ 주요 시각화 예시
- 상관관계 히트맵  
- SHAP 변수 중요도 바 플롯  
- 요인별 LISA 클러스터 지도  
- PCA Biplot  

---

## 💾 실행 환경
- Python 3.10 (Google Colab)
- 주요 패키지  
  `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, `statsmodels`,  
  `pybetareg`, `xgboost`, `shap`, `geopandas`, `esda`, `libpysal`, `splot`, `factor_analyzer`

---

## 🧑‍💻 연구 의의
- **정책적 시사점**  
  - 노후주택·고령화·경제활동 저하가 빈집 증가와 밀접하게 관련됨  
  - 공간적으로는 ‘High-High’ 군집이 특정 생활권에 집중 → **생활 SOC 보강, 맞춤형 도시재생 정책**의 필요성 제시  

---

## 🏁 향후 계획
- 시계열 데이터(2020~2025년)를 활용한 **공간패널모형(Spatial Panel Model)** 확장  
- 자치구 내 세부 행정동 단위로 세분화한 **빈집 위험지수 지도화**

---

## 👩‍💻 Author
**김문주 (Moonjoo Kim)**  
Dankook University · Department of Information Statistics  
📧 rla912906@dankook.ac.kr  
📍 Seoul, Republic of Korea
