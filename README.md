
# 🧠 Medical Data ETL Pipeline

A simple **ETL (Extract, Transform, Load)** pipeline built with **Python + Pandas**, designed to clean and process a medical dataset in a fully containerized environment using **Docker**, **Docker Compose**, and automated **CI/CD** using **GitHub Actions**.

---

## 🚀 Features

* 📥 **Extract** — Reads raw medical data from a CSV file  
* 🔄 **Transform** — Cleans missing values and normalizes column names  
* 📤 **Load** — Saves the cleaned dataset to a new CSV file  
* 🐳 **Dockerized** — Easily run the entire pipeline using Docker  
* 🧩 **Compose Ready** — Includes `docker-compose.yml` for seamless orchestration  
* ⚙️ **CI/CD Integration** — Automatically builds and pushes Docker images to Docker Hub on each push to `main` branch  

---

## 📂 Project Structure

```

├── .github/
│   └── workflows/
│       └── ci-cd.yml
├── Dockerfile
├── docker-compose.yml
├── data/
│   ├── Medicaldataset.csv
│   └── CleanedMedicalData.csv (generated)
├── main.py
└── README.md

````

---

## ⚙️ How It Works

1. **Extract:** Reads the raw dataset from `/data/Medicaldataset.csv`.  
2. **Transform:**  
   * Drops rows with missing values  
   * Normalizes column names (lowercase + underscores)  
3. **Load:** Saves the cleaned data as `/data/CleanedMedicalData.csv`.  
4. **CI/CD:**  
   * On every push to the `main` branch, GitHub Actions automatically:  
     - Builds the Docker image  
     - Pushes it to Docker Hub (`dhiraj918106/simple-data-pipeline:latest`)  

---

## 🐳 Run with Docker

### 1️⃣ Build the image

```bash
docker build -t medical-etl .
````

### 2️⃣ Run the container

```bash
docker run -v $(pwd)/data:/data medical-etl
```

### 3️⃣ Or use Docker Compose

```bash
docker-compose up
```

---

## ⚙️ CI/CD Pipeline

This project includes a **GitHub Actions workflow** (`.github/workflows/ci-cd.yml`) that:

1. Checks out the repository
2. Logs in to Docker Hub using encrypted secrets (`DOCKERHUB_USERNAME`, `DOCKERHUB_TOKEN`)
3. Builds and pushes the Docker image automatically

### 🧩 Trigger

The pipeline runs **automatically** on every push to the `main` branch.

---

## ✅ Output

After running, you’ll find your cleaned dataset here:

```
/data/CleanedMedicalData.csv
```

And your latest Docker image will be available on Docker Hub as:

```
dhiraj918106/simple-data-pipeline:latest
```

---

## 💡 Example Logs

```
Data extraction completed  
Data transformation completed  
Data loading completed  
Data pipeline completed successfully  
```

---

