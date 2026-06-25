# Ecom_delivery_optimisation
Ecom_delivery_optimisation_Geocoding,route optimisation,TSP
# 🚚 Smart Route Planning & Warehouse Optimization System

An advanced, interactive delivery optimization system designed to streamline e-commerce logistics. This system validates geospatial data, clusters delivery regions, maps warehouse-to-customer constraints, and generates optimized delivery routes to minimize costs and transit time.

---

## 🌟 Features

* **Robust Coordinate Validation:** Automatically detects, flags, and separates invalid, missing, or out-of-range latitude and longitude values to ensure clean data processing.
* **Intelligent Region Clustering:** Group warehouses and orders dynamically using K-Means clustering to identify high-density delivery zones.
* **Proximity-Based Routing:** Automatically pairs customer orders with the closest available fulfillment center.
* **Interactive Visualizations:** Generates rich, dynamic maps using `Folium` with distinct color-coded pins for warehouses, order drop-offs, and cluster centers.
* **Comprehensive Data Exports:** Export final optimized delivery plans, multi-stop route sequencing, summary metrics, and data error logs directly into structured Excel formats.

---

## 📊 Data Input Format

The system processes three core data sheets (CSV or Excel formats). To ensure optimal performance, your files should include the following structural headers:

### 1. Warehouse Data
| Header | Description |
| :--- | :--- |
| `FC Code` | Unique identifier for the Fulfillment Center (e.g., SVGA, SDEA) |
| `state` | Operating region/state |
| `Fulfillment Center Address`| Full physical address of the facility |
| `latitude` | Decimal latitude coordinate |
| `longitude` | Decimal longitude coordinate |

### 2. Stock Data
* Must contain a `PRODUCT CODE` column.
* Subsequent column headers must match the unique `FC Code` identifiers from your Warehouse dataset to denote available stock quantities per item.

### 3. Orders Data
| Header | Description |
| :--- | :--- |
| `Number` | Unique Order/Customer ID |
| `Address` / `City` / `State` / `Postal Code` | Customer destination details |
| `PRODUCT CODE` | Ordered item identifier |
| `ORDER_QTY` | Total units ordered |
| `Latitude` | Decimal latitude coordinate |
| `Longitude` | Decimal longitude coordinate |

---

## 🛠️ Tech Stack & Dependencies

The project relies on the following core Python libraries:

```bash
pip install pandas numpy folium requests googlemaps geopy scikit-learn plotly openpyxl ipywidgets
