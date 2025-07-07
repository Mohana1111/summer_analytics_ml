# 🅿️ Dynamic Urban Parking Price Prediction

A real-time pricing engine and visualization system for urban parking spaces based on occupancy, demand, queue length, traffic, and special events. The goal is to optimize parking prices dynamically and reroute vehicles when lots are overburdened.

---

## 📌 Overview

This project builds a **multi-model dynamic pricing system** for 14 urban parking spaces, sampled across 73 days at 18 time intervals per day. We use:

- Baseline price models using occupancy
- Demand-based dynamic pricing using multiple features
- Exponential models for smoother elasticity-based pricing
- Interactive Bokeh-based visualization of prices and competitor lots

---

## 🧰 Tech Stack

| Category           | Tools Used                         |
|--------------------|-------------------------------------|
| Language           | Python 3.x                          |
| Data Handling      | Pandas, NumPy                       |
| Visualization      | Bokeh, Panel                        |
| Geospatial Calc    | Geopy                               |

---


1. Workflow & Architecture
1.Data Preparation

Original dataset contains:

Latitude/Longitude of lots

Occupancy, QueueLength, Capacity

VehicleType, SpecialDay, TrafficConditionNearby

Timestamp (e.g., 04-10-2016, 07:59:00)

2. Steps:

Parse the time into datetime objects

Normalize features as needed (scaling, encoding categorical variables)

3. Model 1 – Baseline Linear Price Model


4. Model 2 – Linear Demand-Based Price Model
Formulas :
-Demand = α * (Occupancy / Capacity) + β * QueueLength − γ * Traffic + δ * IsSpecialDay + ε * VehicleTypeWeight
Price_t = BasePrice * (1 + λ * NormalizedDemand)

5. Model 3 – Exponential Elastic Price Model

Formula:
Price = BasePrice * exp(λ * NormalizedDemand)

6. Visualization with Bokeh

Interactive plots using Bokeh + Panel

Dropdown to select parking lot

Shows nearby competitors (within 0.5 km)

Uses Geopy for distance calculation

