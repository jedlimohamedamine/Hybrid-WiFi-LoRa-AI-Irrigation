Project README

## Overview
Our project monitors soil and environmental conditions in three Tunisian regions (Bizerte, Tunis, Kasserine) using ESP32-based sensors and a TensorFlow LSTM model for predictive analysis. This repository contains synthetic datasets generated to simulate sensor readings for soil moisture, temperature, humidity, evapotranspiration, and gas concentrations, used for testing and training the LSTM model.

## Dataset Description
Three CSV files contain synthetic sensor data for:
- **Bizerte**: January 6, 2025, 10:48:00 to February 28, 2025, 23:50:00 (~7,696 records)
- **Tunis**: April 2, 2025, 09:07:00 to April 30, 2025, 23:50:00 (~4,086 records)
- **Kasserine**: May 2, 2025, 14:17:00 to June 30, 2025, 23:50:00 (~8,581 records)

Each dataset has data points every 10 minutes, with a total of ~20,363 timestamps across all files.

### Data Schema
Each CSV follows this schema:
- **timestamp**: String, format "YYYY-MM-DD HH:MM:SS" (e.g., "2025-01-06 10:48:00")
- **site**: String, one of "Bizerte", "Tunis", "Kasserine"
- **moisture**: Float, soil moisture in % (e.g., 45.2), ±2% accuracy from capacitive probes
- **T**: Float, temperature in °C (e.g., 25.6)
- **RH**: Float, relative humidity in % (e.g., 60.3)
- **ET0**: Float, reference evapotranspiration in mm/day (e.g., 4.5), calculated via Penman-Monteith
- **H2_ppm**: Float, hydrogen concentration in ppm (MQ-8 sensor)
- **CO_ppm**: Float, carbon monoxide in ppm (MQ-9 sensor)
- **CH4_ppm**: Float, methane in ppm (MQ-9 sensor)
- **NH3_ppm**: Float, ammonia in ppm (MQ-135 sensor)
- **NOx_ppm**: Float, nitrogen oxides in ppm (MQ-135 sensor)
- **benzene_ppm**: Float, benzene in ppm (MQ-135 sensor)

### Regional Parameters
- **Bizerte (loamy soil, winter)**: Moisture ~65%, T ~9.5–11°C, RH ~85%, ET0 ~1.5–2.0 mm/day
- **Tunis (sandy soil, spring)**: Moisture ~50%, T ~15.5°C, RH ~67%, ET0 ~3.7 mm/day
- **Kasserine (arid soil, late spring/summer)**: Moisture ~30%, T ~23–25°C, RH ~47%, ET0 ~4.8–5.2 mm/day
- **Gas Sensors**: H2_ppm ~4.0, CO_ppm/CH4_ppm ~5.0, NH3_ppm ~2.0, NOx_ppm ~1.5, benzene_ppm ~0.8, with temperature adjustments and noise

## File Structure
- `bizerte_data.csv`: Bizerte dataset
- `tunis_data.csv`: Tunis dataset
- `kasserine_data.csv`: Kasserine dataset
- `README.txt`: This file