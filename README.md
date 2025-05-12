
# Weather Data Fetcher

## 📝 Overview
The **Weather Data Fetcher** is a Python application that retrieves weather data for cities in a specified country using the OpenWeatherMap API.  
It processes city data from a JSON file, fetches current weather information, and saves the results to a CSV file for further analysis.

The application is designed with robust error handling, logging, and retry mechanisms to ensure reliable operation.

---

## ✨ Features
- Fetches weather data for multiple cities in batches using the OpenWeatherMap Group API.
- Filters cities by country code (default: `US`).
- Converts UNIX timestamps to local time for sunrise and sunset.
- Saves detailed weather attributes (e.g., temperature, humidity, wind speed) to a CSV file.
- Implements logging to track events and errors, with output to both a file (`app.log`) and the console.
- Uses environment variables for secure API key management.
- Retries failed API requests with exponential backoff using the `tenacity` library.

---

## ✅ Prerequisites
- Python 3.11 or higher  
- An OpenWeatherMap API key  
- A `city_list.json` file containing city data (available from OpenWeatherMap)  
- Internet connection for API requests  

---

## 🚀 Installation

### 1. Clone the repository:
```bash
git clone https://github.com/your-username/weather-data-fetcher.git
cd weather-data-fetcher
```

### 2. Set up a virtual environment (recommended):
```bash
python -m venv venv
# On macOS/Linux:
source venv/bin/activate
# On Windows:
venv\Scriptsctivate
```

### 3. Install dependencies:
```bash
pip install -r requirements.txt
```

**`requirements.txt` should include:**
```
requests
python-dotenv
pandas
tenacity
```

---

### 4. Set up environment variables

Create a `.env` file in the project root and add your API key:
```
app_id=your_api_key_here
```

---

### 5. Prepare the city list

- Place the `city_list.json` file inside a `Data` directory:
  ```
  Data/city_list.json
  ```
- Ensure it contains valid JSON data with `id`, `name`, and `country` fields.

---

## ⚙️ Usage

### Run the application:
```bash
python main.ipynb
```

### Or convert the notebook to a Python script:
```bash
jupyter nbconvert --to script main.ipynb
python main.py
```

---

## 📤 Output
- Weather data will be saved to: `Weather Data.csv`
- Logs will be written to: `app.log`
- Console will display logs and any errors

---

## 🛠 Customize
- To change the country code, edit the `load_cities()` call in `main()`:
  ```python
  load_cities(logger, country='CA')  # For Canada
  ```
- To adjust the log level, set `LOG_LEVEL` in your `.env`:
  ```
  LOG_LEVEL=DEBUG
  ```

---

## 📁 File Structure
```
weather-data-fetcher/
├── Data/
│   └── city_list.json        # JSON file with city data
├── .env                      # Environment variables (API key)
├── main.ipynb                # Jupyter Notebook with the application code
├── app.log                   # Log file for application events
├── Weather Data.csv          # Output CSV file with weather data
├── requirements.txt          # Python dependencies
└── README.md                 # This file
```

---

## 🤝 Contributing

Contributions are welcome!  
To contribute:

1. Fork the repository  
2. Create a new branch:  
   ```bash
   git checkout -b feature/your-feature
   ```
3. Make your changes and commit:  
   ```bash
   git commit -m "Add your feature"
   ```
4. Push to your forked branch:  
   ```bash
   git push origin feature/your-feature
   ```
5. Open a Pull Request

Please follow PEP 8 style guidelines and include tests where applicable.

---

## 📜 License

This project is licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [OpenWeatherMap](https://openweathermap.org/) for providing the weather API.  
- Built with **Python** and **Jupyter Notebook** for ease of development and experimentation.
