# 📊 E-commerce Sales Analytics: Влияние скидок на выручку

> Краткое описание аналитического проекта по оценке эффективности скидочной политики в e-commerce на основе датасета из 5000 заказов.

![Python](https://img.shields.io/badge/Python-3.14.6-blue)
![Pandas](https://img.shields.io/badge/Pandas-3.1.0-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)
![Orders](https://img.shields.io/badge/Orders-5000-blueviolet)

---

## 🎯 Цель проекта

Количественно оценить влияние размера скидки (`discount`) на выручку (`revenue`) и количество товаров в заказе (`quantity`). Проверить гипотезу о наличии **оптимальной скидки**, максимизирующей выручку (нелинейный квадратичный эффект).

**Ключевой бизнес-вопрос:** *Существует ли такой процент скидки, при котором выручка на заказ достигает максимума?*

---

## 📦 Данные

| Параметр | Значение |
| :--- | :--- |
| **Источник** | [Kaggle: E-commerce Sales Dataset](https://www.kaggle.com/datasets/abbas829/ecommerce-sales-dataset) |
| **Объём** | 5000 строк × 12 столбцов (исходно), 14 столбцов (после обогащения) |
| **Единица анализа (Grain)** | Уникальный заказ (`order_id`) |
| **Период** | 2022-01-01 — 2035-09-09 (4999 дней) |
| **Клиенты** | 989 уникальных `customer_id` |
| **Категории товаров** | 4: Beauty, Clothing, Electronics, Home |
| **Регионы** | 4: North, South, East, West |
| **Способы оплаты** | 3: Card, COD, Wallet |

**Бизнес-формула (подтверждена для 100% записей):**
$$revenue = quantity \times unit\_price \times (1 - discount)$$

---

## 🗂 Структура проекта
# ecommerce_sales_analytics/

- 📄 `README.md` — описание проекта (этот файл).
- 📊 `ecommerce_sales_analytics_5000.csv` — исходный датасет (5000 заказов).
- 📓 `ecommerce_sales.ipynb` — Notebook со всеми 7 этапами анализа.
- 📊 `ecommerce_sales_clean.csv` — очищенный и обогащённый датасет (14 столбцов).
- 📊 `segment_models_summary.csv` — сводная таблица результатов сегментных моделей.
- 📋 `qa_delivery_report.json` — отчёт о качестве данных и воспроизводимости.
- 📘 `metadata_ecommerce.md` — метаданные датасета.
- 📗 `pipeline_ecommerce.md` — описание аналитического пайплайна.
- 📕 `data_systems_intelligence_architect_preprompt.md` — ролевая инструкция аналитика.

## 📁 plots/ — визуализации (PNG + PDF)

### 📈 Этап 4: Разведочный анализ (EDA)
- 📈 `01_distributions_quantity_revenue.png/pdf` — распределения quantity и revenue.
- 📈 `02_boxplots_quantity_revenue.png/pdf` — box‑plot’ы по категориям.
- 📈 `03_spearman_correlation_heatmap.png/pdf` — тепловая карта корреляций Спирмена.
- 📈 `04_scatter_discount_vs_revenue.png/pdf` — scatter‑plot: скидка vs выручка.

### 📉 Этап 5: Моделирование
- 📉 `05_poly_regression_revenue.png/pdf` — полиномиальная регрессия revenue.
- 📉 `05_poly_regression_quantity.png/pdf` — полиномиальная регрессия quantity.
- 📉 `05_poly_regression_segments.png/pdf` — сегментный анализ по категориям.

### 📊 Этап 6: Финальная визуализация
- 📊 `06_01_revenue_vs_discount_poly.png/pdf` — финальный тренд выручки.
- 📊 `06_02_quantity_vs_discount_poly.png/pdf` — финальный тренд количества.
- 📊 `06_03_bar_revenue_by_bin_category.png/pdf` — выручка по корзинам и категориям.
- 📊 `06_04_bar_quantity_by_bin_category.png/pdf` — количество по корзинам и категориям.
