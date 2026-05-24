# phantomR-8831 Laboratory

Welcome to my toolset repository. Here I build and maintain scripts for system resilience, calculations, and OS protection.

## Core Modules

### 1. Parrot OS Docker Shield (`parrot-shield.sh`)
A lightweight bash automation tool designed for **Parrot OS** to protect the host system from crashes caused by untrusted Docker containers.
* **The Problem:** Docker logs, hidden layers, and containers can easily starve disk space or cause kernel panics on pentest distros.
* **The Solution:** Automates system snapshots via `Timeshift` before running containers and cleans up Docker junk in one click.

### 2. Resilience Model (`resilience_model.py`)
Python core module dedicated to system stability testing and uptime modeling.

### 3. Building Calculator (`building_calc.py`)
Custom logic calculation engine used for infrastructure estimations.

## Installation & Usage (Docker Shield)

1. Make the script executable:
```bash
   chmod +x parrot-shield.sh
