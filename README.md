# SparkMachineLearning — Machine Learning com Apache Spark (PySpark + MLlib)

Coleção prática e abrangente de **notebooks Jupyter** para aprender **Machine Learning com Apache Spark**, usando **PySpark** e as APIs de **Spark ML / MLlib** (DataFrames). O repositório inclui notebooks e datasets para executar os exemplos ponta a ponta.

---

## O que você vai encontrar aqui

- Importação e leitura de dados (CSV, JSON, ORC, Parquet, LIBSVM)
- Engenharia de atributos (VectorAssembler, encoders, imputação, escalas, discretização)
- Modelos:
  - **Regressão** (Linear/Generalized)
  - **Classificação** (Logistic, Naive Bayes, MLP, Random Forest)
  - **Clusterização** (KMeans, Bisecting KMeans)
  - **Associação** (FPGrowth)
- **Pipelines** e **tuning** (CrossValidation / TrainValidationSplit)

---

## Estrutura do repositório

- **Notebooks**: `*.ipynb` (ex.: `1.Dataimport.ipynb`, `21.LinearRegression.ipynb`, `30.Pipelines.ipynb`, etc.)
- **Datasets**: arquivos como `Carros.csv`, `Churn.csv`, `iris.csv`, `iris_libsvm.txt`, `despachantes.*`, `Transacoes.txt`, etc.

---

## Como rodar (modo local)

### Pré-requisitos
- **Python 3.9+** (recomendado 3.10/3.11)
- **Java 8/11/17** (Spark precisa de JVM)
- (Opcional) Conda/Miniconda para isolar ambiente

### 1) Crie e ative um ambiente (opcional, recomendado)

**Conda**
```bash
conda create -n sparkml python=3.10 -y
conda activate sparkml
```

**venv**
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# Linux/Mac:
source .venv/bin/activate
```

### 2) Instale dependências

Para rodar os notebooks com Spark em modo local:
```bash
pip install jupyter pyspark
```

Se algum notebook usar `pandas`/`matplotlib`:
```bash
pip install pandas matplotlib
```

### 3) Inicie o Jupyter

```bash
jupyter notebook
```

Abra o notebook desejado e execute as células.

---

## Trilha sugerida (ordem recomendada)

### A) Início: leitura e formatos
1. `1.Dataimport.ipynb`
2. `2.Libsvm.ipynb`

### B) Feature Engineering / Pré-processamento
- `3.VectorAssembler.ipynb`
- `4.PCA.ipynb`
- `5.Binarization.ipynb`
- `6.StringIndexer.ipynb`
- `7.IndexToString.ipynb`
- `8.OneHotEncoder.ipynb`
- `9.Imputer.ipynb`
- `10.PolynomialExpansion.ipynb`
- `11.Normalizer.ipynb`
- `12.StandardScaler.ipynb`
- `13.RobustScaler.ipynb`
- `14.MinMaxScaler.ipynb`
- `15.MaxAbsScaler.ipynb`
- `16.QuantileDiscretizer.ipynb`
- `17.RFormula.ipynb`
- `18.VectorSlicer.ipynb`
- `19.ChiSqSelector.ipynb`
- `20.UnivariateFeatureSelector.ipynb`

### C) Modelos
- `21.LinearRegression.ipynb`
- `22.GeneralizedRegression.ipynb`
- `23.RandomForest.ipynb`
- `24.Logistic.ipynb`
- `25.Naive.ipynb`
- `26.MultilayerPerceptron.ipynb`
- `27.Kmeans.ipynb`
- `28.HierarchicalBisecting.ipynb`
- `29.FPGrowth.ipynb`

### D) Pipelines + Tuning
- `30.Pipelines.ipynb`
- `31.TunningCross.ipynb`
- `32.TunningTrain.ipynb`

---

## Troubleshooting rápido

- **Erro de Java/JVM**: confirme `java -version` e use Java 11/17 (recomendado).
- **Spark lento**: evite `show()` em datasets grandes; reduza logs quando necessário.
- **Memória**: ajuste a memória do driver em notebooks mais pesados, por exemplo:
  ```python
  SparkSession.builder.config("spark.driver.memory", "2g")
  ```

---

## Licença

Se você pretende uso amplo (portfólio/colaboração), recomendo adicionar uma licença (ex.: **MIT**).
Se preferir uso apenas educacional, explicite isso aqui.

---

## Autor

**Fernando Amaral** — Data/AI Engineer & Instructor
