# Multi-Agent-AI-System-using-Google-ADK

# Multi-Agent AI System using Google ADK 🚀

This project implements a **Multi-Agent AI System** that takes a user-defined goal and routes it through multiple intelligent agents. Each agent enriches and processes the information received from the previous one until the objective is fulfilled.

## 🌟 Features

* Developed with **FastAPI** and deployable in **Google Colab** using **Ngrok**
* Agents are capable of inter-communication, chaining tasks, and resolving complex goals
* Compatible with external APIs like:

  * SpaceX Launch Data (via [SpaceX API](https://github.com/r-spacex/SpaceX-API))
  * Weather Forecast (via [OpenWeatherMap API](https://openweathermap.org/api))
  * Bitcoin Price Checker (via [CoinGecko API](https://www.coingecko.com/))
* Built-in Evaluation Tracking via FastAPI endpoints

## 🛠 Technologies Used

* Python
* FastAPI
* Ngrok (for exposing Colab endpoints)
* Requests (for API calls)

## 📦 Installation

> All setup is designed to run inside a Google Colab notebook.

1. Upload `.env.txt` file containing your API keys (e.g., NewsAPI, OpenWeatherMap)

```bash
API_KEY=your_api_key_here
```

2. Start the FastAPI server:

```python
!uvicorn main:app --reload --port 8000 &
```

3. Run Ngrok to expose the server:

```python
from pyngrok import ngrok
public_url = ngrok.connect(8000)
print("🚀 FastAPI running at:", public_url)
```

4. Access the FastAPI Swagger UI:
   👉 [https://b660-35-233-131-53.ngrok-free.app/docs](https://b660-35-233-131-53.ngrok-free.app/docs)

## 🧪 Evaluation Examples

### 1. SpaceX Launch Delay Checker

```json
{
  "goal": "Get the date and summary of the next SpaceX launch"
}
```

**Expected Output:** Mission name, rocket, launch pad, weather at location, launch delay risk.

### 2. Bitcoin Price Checker

```json
{
  "goal": "Get the current Bitcoin price in INR"
}
```

**Expected Output:** Current price of Bitcoin in INR, possibly with % change or timestamp.

### ✅ How to Use

1. Go to [FastAPI Docs](https://b660-35-233-131-53.ngrok-free.app/docs)
2. Click on `POST /evaluate`
3. Click **Try it out** → Paste any of the above JSON goals → Click **Execute**
4. View the output in real-time

## 📂 Endpoints

| Method | Endpoint     | Description                      |
| ------ | ------------ | -------------------------------- |
| POST   | /evaluate    | Evaluate a goal with multi-agent |
| GET    | /evaluations | View all past evaluations        |

---

## 👤 Author

**Aditya Kumar Pandey**
MTech (AI & Data Science), IIIT Bhagalpur

📧 [aditya.240201001@iiitbh.ac.in](mailto:aditya.240201001@iiitbh.ac.in)
📞 +91 7858826847

---

Feel free to ⭐️ this repo if you found it useful!
