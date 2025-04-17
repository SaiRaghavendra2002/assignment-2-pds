# 🚗 Used Car Data Analysis – PDS Assignment 2

This repository contains a complete end-to-end analysis and transformation of a used car dataset as part of **Assignment 2** for the course **Principles of Data Science (PDS)**.

The dataset involves key car attributes such as brand, location, mileage, engine specs, transmission type, and the price of the car (in lakhs).

---

## 📦 Files in This Repository

| 📄 File Name                  | 📘 Description                                                  |
|------------------------------|-----------------------------------------------------------------|
| `train.csv`                 | Original raw dataset                                            |
| `pds_assignment_2_16353860.ipynb` | Google Colab notebook with all steps and code         |
| `selected_result.csv`       | Output after selecting key columns                             |
| `filtered_result.csv`       | Filtered cars with mileage > 20                                 |
| `renamed_result.csv`        | Renamed `Price` → `Selling_Price`                              |
| `mutated_result.csv`        | Added derived column `Price_Per_Year`                          |
| `arranged_result.csv`       | Sorted dataset by `Selling_Price` (descending order)           |
| `processed_used_cars.csv`   | Final fully cleaned and transformed dataset                    |
| `README.md`                 | Documentation for the full assignment                          |

---

## 📌 Assignment Breakdown

### 🔹 Part (a) – Handling Missing Values
- ❌ Dropped `New_Price` (over 85% missing)
- 🛠 Imputed:
  - `Seats` → Mode
  - `Engine`, `Power`, `Mileage` → Median (after cleaning text)
- ✅ Confirmed zero missing values in major columns

### 🔹 Part (b) – Removing Units from Columns
- Removed units to retain only numeric values:
  - `" CC"` from `Engine`
  - `" bhp"` from `Power`
  - `" kmpl"` / `" km/kg"` from `Mileage`
- Converted all to `float` for numeric processing

### 🔹 Part (c) – One-Hot Encoding
- Applied `pd.get_dummies()` to:
  - `Fuel_Type` → Created `Fuel_Type_Petrol`, `Fuel_Type_Electric`
  - `Transmission` → Created `Transmission_Manual`
- Set `drop_first=True` to prevent multicollinearity

### 🔹 Part (d) – Feature Engineering
- 🆕 Created `Car_Age`:
  ```python
  Car_Age = Current Year - Year of Manufacture
  ```

### 🔹 Part (e) – Data Operations with Pandas

| Operation  | Description                                | Output File              |
|------------|--------------------------------------------|--------------------------|
| `select`   | Selected specific useful columns           | `selected_result.csv`    |
| `filter`   | Kept cars with mileage > 20                | `filtered_result.csv`    |
| `rename`   | Renamed `Price` to `Selling_Price`         | `renamed_result.csv`     |
| `mutate`   | Created `Price_Per_Year` column            | `mutated_result.csv`     |
| `arrange`  | Sorted by `Selling_Price` (descending)     | `arranged_result.csv`    |
| `groupby`  | Used in notebook to show avg price by city | (inside notebook only)   |

---

## 🧠 Tools & Technologies

- 🐍 **Python** with `pandas`
- ☁️ **Google Colab**
- 📊 **CSV** format for intermediate outputs
- 🔗 **GitHub** for version control and public submission

---

## 📬 Submission Notes

- All transformations were done in `pds_assignment_2_16353860.ipynb` using Google Colab.
- Results were saved using `to_csv()` and downloaded using `files.download()`.
- All files were uploaded to this GitHub repository for transparency and evaluation.

---

## 👨‍💻 Author

**Sai Raghavendra**  
M.S. Computer Science – University of Missouri Kansas City  
🔗 GitHub: [@SaiRaghavendra2002](https://github.com/SaiRaghavendra2002)

---

### ✅ Ready for Review  
Feel free to open the notebook or any `.csv` to inspect the output of each transformation step!
