
# 🧠 Medical Data ETL Pipeline

A simple **ETL (Extract, Transform, Load)** pipeline built with **Python + Pandas**, designed to clean and process a medical dataset in a fully containerized environment using **Docker** and **Docker Compose**.

---

## 🚀 Features

* 📥 **Extract** — Reads raw medical data from a CSV file
* 🔄 **Transform** — Cleans missing values and normalizes column names
* 📤 **Load** — Saves the cleaned dataset to a new CSV file
* 🐳 **Dockerized** — Easily run the entire pipeline using Docker
* 🧩 **Compose Ready** — Includes `docker-compose.yml` for seamless orchestration

---

## 📂 Project Structure

```
├── Dockerfile
├── docker-compose.yml
├── data/
│   ├── Medicaldataset.csv
│   └── CleanedMedicalData.csv (generated)
├── main.py
└── README.md
```

---

## ⚙️ How It Works

1. **Extract:** Reads the raw dataset from `/data/Medicaldataset.csv`.
2. **Transform:**

   * Drops rows with missing values
   * Normalizes column names (lowercase + underscores)
3. **Load:** Saves the cleaned data as `/data/CleanedMedicalData.csv`.

---

## 🐳 Run with Docker

### 1️⃣ Build the image

```bash
docker build -t medical-etl .
```

### 2️⃣ Run the container

```bash
docker run -v $(pwd)/data:/data medical-etl
```

### 3️⃣ Or use Docker Compose

```bash
docker-compose up
```

---

## ✅ Output

After running, you’ll find your cleaned dataset here:

```
/data/CleanedMedicalData.csv
```

---

## 💡 Example Logs

```
Data extraction completed  
Data transformation completed  
Data loading completed  
Data pipeline completed successfully  
```


