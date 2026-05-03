# ESP32 Health Monitor v8.1 — Web Dashboard (HTML Interface)

## Overview

This project includes a web-based biomedical monitoring dashboard designed to visualize real-time physiological data from an ESP32-based system. It is implemented using HTML, CSS, and JavaScript and operates as a browser-based interface for multi-sensor health monitoring.

The system functions as a hardware-to-browser bridge, enabling real-time signal visualization, debugging, and data logging without requiring a dedicated mobile application.

---

## System Purpose

The interface is developed to:

* Display real-time biomedical signals from ESP32
* Support multiple communication protocols (WiFi, BLE, USB Serial)
* Provide clinical-style waveform visualization
* Enable recording and export of physiological datasets
* Assist firmware testing and system validation

---

## Supported Biomedical Signals

### ECG (Electrocardiogram)

* Lead I configuration
* 250 Hz sampling rate
* Real-time waveform visualization
* Heart rate estimation via QRS detection
* RR interval and HRV analysis

### SpO₂ (Oxygen Saturation)

* MAX30100 sensor support
* Real-time saturation percentage display
* Signal quality estimation
* Trend visualization over time

### Pulse Rate (PPG)

* Derived from optical sensor data
* Real-time BPM calculation
* Stability tracking across readings

### Temperature

* DS18B20 sensor integration
* Multi-level clinical classification
* Session-based min/max tracking

---

## Communication Architecture

### 1. WiFi (WebSocket)

* ESP32 Access Point mode
* WebSocket streaming on port 81
* JSON-based real-time data transfer
* Auto-reconnection and recovery handling

### 2. Bluetooth Low Energy (BLE)

* Web Bluetooth API integration
* GATT-based multi-characteristic streaming
* Separate channels for ECG, SpO₂, pulse, and temperature

### 3. USB Serial

* Web Serial API support
* 115200 baud rate communication
* JSON newline-delimited data stream

---

## User Interface Design

* Dark biomedical-themed UI optimized for long monitoring sessions
* Modular dashboard layout
* Signal-specific color coding system
* Responsive design for different screen sizes
* Real-time status indicators and state machine visualization

---

## Visualization Components

### ECG Visualization

* Canvas-based real-time rendering
* Grid-based medical waveform layout
* Lead-off detection overlay
* Glow-enhanced signal trace

### Trend Analysis

* Heart rate trend (last 60 beats)
* SpO₂ trend (1-second interval)
* Pulse rate trend visualization
* Temperature trend (5-second interval)

### RR Interval Analysis

* Beat-to-beat variability visualization
* HRV estimation using RMSSD method
* Dynamic bar representation

---

## Signal Processing Logic

* Heart rate classification (tachycardia, bradycardia, normal)
* SpO₂ threshold evaluation
* Temperature-based clinical classification
* Lead connection status monitoring

---

## Data Recording System

### Features

* Real-time session recording
* Selective signal logging (ECG, beats, SpO₂, temperature)
* Timestamped dataset storage

### Export

* CSV export functionality
* Browser-based download system
* Structured dataset for analysis

---

## Performance Optimization

* Circular buffer for ECG data handling
* Efficient canvas rendering with device scaling
* Minimal DOM updates for real-time metrics
* Animation frame-based rendering loop
* Optimized array management for trend data

---

## Key Features

* Multi-protocol connectivity (WiFi, BLE, USB)
* Real-time biomedical signal visualization
* Clinical-style UI representation
* Modular and extensible architecture
* Built-in recording and export system

---

## Use Case

This system is designed for:

* Biomedical engineering prototyping
* Real-time physiological monitoring research
* Embedded system validation
* Educational demonstration of biosignal processing
* Future AI-assisted diagnostic development

---

## Summary

The ESP32 Health Monitor v8.1 web interface provides a real-time biomedical visualization platform that integrates multiple physiological sensors into a unified browser-based system. It emphasizes real-time responsiveness, modular architecture, and extensibility for advanced biomedical applications.
