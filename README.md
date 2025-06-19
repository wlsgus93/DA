# 📊 Python 데이터 분석 예제 모음

`pandas`, `scikit-learn`, `statsmodels`의 자주 쓰는 메서드와 실습 예제를 정리한 저장소입니다.  
각 라이브러리별로 주요 기능들을 `.ipynb` 또는 `.py` 파일로 정리하고, 관련 설명은 `.md`로 제공합니다.

---

## 📁 폴더 구조

```
data-analysis-cheatsheet/
├── pandas/
│   ├── series_basics.ipynb
│   ├── groupby_examples.ipynb
│   └── pandas_cheatsheet.md
├── sklearn/
│   ├── preprocessing.ipynb
│   └── model_selection.ipynb
├── statsmodels/
│   └── ols_regression.ipynb
├── datasets/
│   └── sample_data.csv
├── requirements.txt
└── README.md
```

---

## 📚 목차 (Contents)

### 🐼 pandas

- [기본 예제](./pandas/basic.ipynb)
- [📄 pandas 메서드 정리](./pandas/pandas_cheatsheet.md)

### 🤖 scikit-learn

- [데이터 전처리 (StandardScaler, LabelEncoder)](./sklearn/preprocessing.ipynb)
- [모델 선택 및 검증 (train_test_split, GridSearchCV)](./sklearn/model_selection.ipynb)

### 📈 statsmodels

- [OLS 회귀분석 예제](./statsmodels/ols_regression.ipynb)

---

## 🧠 목표 (Goals)

- 자주 사용하는 데이터 분석 메서드 체계화
- 실습 위주로 정리한 `.ipynb` 노트북 예제
- GitHub 기반으로 TIL 및 포트폴리오화

---

## 🛠 설치 방법 (Setup)

```bash
git clone https://github.com/wlsgus93/data-analysis-cheatsheet.git
cd data-analysis-cheatsheet
python -m venv venv
source venv/bin/activate  # 또는 .\venv\Scripts\activate (Windows)
pip install -r requirements.txt
```

Jupyter 실행:
```bash
jupyter notebook
```

---

## 📦 requirements.txt 예시

```txt
pandas
scikit-learn
statsmodels
matplotlib
jupyter
```

---

## 📬 연락

질문이나 제안은 GitHub Issue 또는 [이메일](mailto:your.email@example.com)로 부탁드립니다.
