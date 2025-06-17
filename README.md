# BTP-Passenger-Predection
# 🚆 Passenger Flow Forecasting & Train Optimization

## 📌 Project Overview

This project presents a comprehensive system to analyze, forecast, and optimize train operations at a busy urban railway station. The primary goal is to simulate the passenger inflow and determine the ideal number and timing of train dispatches, minimizing wait times and maximizing efficiency.

It consists of two major parts:
1. **Time Series Forecasting** using STL decomposition to predict hourly passenger volume.
2. **Discrete Event Simulation** to determine train scheduling, considering capacity constraints and real-world limitations.

---

## 🎯 Objectives

- Forecast hourly passenger traffic throughout the year.
- Model seasonality, trends, and noise in passenger data using STL decomposition.
- Simulate train operations based on predicted data to optimize train dispatches.
- Ensure no passenger waits more than 10 minutes and no train exceeds a 650-passenger limit.

---

## 🧠 Problem Description

Train stations in metropolitan areas experience massive fluctuations in footfall due to working hours, weekends, holidays, and special events. Poor forecasting can lead to either congestion or underutilization. This project seeks to:

- Understand passenger movement patterns.
- Forecast daily and hourly passenger numbers.
- Use a simulation to decide the **minimum number of trains required** per day under operational constraints.

---

## 🧪 Methodology

### 1. 📊 STL Decomposition (Time Series Analysis)
- **Technique Used**: STL (Seasonal-Trend decomposition using Loess).
- **Purpose**: Break down the passenger time series data into **trend**, **seasonality**, and **residuals**.
- **Result**: Smoother and more accurate forecasts that are interpretable.

### 2. 📈 Passenger Count Forecasting
- Trained on cleaned, decomposed data.
- Generates passenger count forecasts on an hourly basis for any given day of the year.
- Includes treatment for holidays, weekends, and rush-hour adjustments.

### 3. 🚄 Discrete Event Simulation
- **Key Parameters**:
  - Train capacity: **650 passengers**
  - Max wait time: **10 minutes**
- **Logic**:
  - For every predicted hour, passengers are batched.
  - Trains are dispatched if the batch exceeds 650 or 10 minutes have passed since the last train.
  - Additional trains are dispatched dynamically in peak hours.

### 4. 📅 Temporal Segmentation
- Days are categorized into:
  - **Weekdays**
  - **Weekends**
  - **Public Holidays**
- Separate seasonal profiles are maintained for each category to improve prediction accuracy.

---

## ✅ Key Features

- Time series visualization and STL decomposition plots.
- Passenger prediction by hour.
- Train requirement calculation per hour/day.
- Smart batching and train dispatch strategy.
- Simulation metrics: number of trains per day, average wait time, utilization.

---

## 📈 Sample Insights (you can visualize)

- Average number of trains dispatched per weekday vs weekend.
- Passenger volume peaks during morning (8–10 AM) and evening (5–7 PM) rush hours.
- Fewer trains required during weekends but variability increases.
