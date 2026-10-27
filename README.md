# Analýza a shlukování olympijských sportovců

Projekt do předmětu VYL0034. Jupyter notebook, který zkoumá fyzické parametry olympijských sportovců (věk, výška, váha, pohlaví) a pomocí shlukové analýzy v nich hledá skupiny s podobnou tělesnou stavbou.

## Co projekt obsahuje

1. **Načtení dat** – `dataset_olympics.csv` (~270 000 záznamů)
2. **EDA** – histogramy, scatter plot výška × váha, korelační matice
3. **Čištění dat** – imputace chybějících hodnot mediánem podle sportu a pohlaví
4. **Feature engineering** – `BMI`, `Medal_Won`, `Is_Summer`
5. **Preprocessing** – `LabelEncoder` pro pohlaví, `StandardScaler` pro numerické rysy
6. **Shlukování**
   - K-Means (počet shluků určen metodou lokte, k = 4)
   - DBSCAN (detekce outlierů)
7. **Interpretace shluků** – popis typických skupin sportovců

## Použité technologie

Python 3, pandas, numpy, seaborn, matplotlib, scikit-learn

## Spuštění

```bash
pip install pandas numpy seaborn matplotlib scikit-learn jupyter
jupyter notebook VYL0034_projekt_01.ipynb
```

Soubor `dataset_olympics.csv` musí být ve stejné složce jako notebook.

## Hlavní zjištění

- Výška a váha silně korelují (~0,8), věk téměř vůbec.
- Tělesná konstituce sportovců se výrazně liší podle pohlaví a typu sportu.
- K-Means rozdělil sportovce do 4 skupin podle výšky, váhy, BMI a pohlaví.
- DBSCAN vytvořil jeden hlavní shluk a označil extrémní jedince jako šum (`-1`).

## Autor

Tomáš – VŠB-TUO
