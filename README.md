
<div align="center">
  <h1>MAGMAxRICH Number Lookup API 🔍</h1>
  <p><b>A blazing fast, FastAPI-based proxy service that fetches phone number details and injects custom MAGMAxRICH branding.</b></p>
  <p>Python | FastAPI | Uvicorn | Requests</p>
</div>

## ⚙️ How It Works
This API acts as a middleman (proxy). When a user requests information for a specific phone number, the app:
1. Receives the `phone` parameter.
2. Forwards the request to the upstream Base API (`normal-num-info.vercel.app`).
3. Intercepts the JSON response.
4. **Modifies the data** on the fly (Changes `API BY` to `@Anysnapsupport` and `Owner` to `@MAGMAxRICH`).
5. Returns the newly branded JSON data to the user.

## 🚀 Setup & Installation

### 1. Install Dependencies
Make sure you have Python installed. Then run the following command to install the required libraries:
```bash
pip install fastapi uvicorn requests

2. Run the Server
Save your code in a file named main.py and start the Uvicorn server:
uvicorn main:app --reload

The API will start running locally at http://127.0.0.1:8000
📡 API Endpoints
1. Health Check
Checks if the API is active and running.
 * URL: /
 * Method: GET
 * Response:
   {
  "message": "Welcome to MAGMAxRICH API",
  "status": "Active"
}

2. Number Lookup
Fetches the target phone number information and applies custom branding.
 * URL: /magma/lookup
 * Method: GET
 * Query Parameter:
   * phone (string, required) - The mobile number you want to look up.
 * Example Request:
   GET [http://127.0.0.1:8000/magma/lookup?phone=9876543210](http://127.0.0.1:8000/magma/lookup?phone=9876543210)

 * Expected Modified Response:
   {
  "api_name": "MAGMAxRICH",
  "result": {
    "data": {
      "Number": "9876543210",
      "Details": "...",
      "API BY": "@Anysnapsupport",
      "Owner": "@MAGMAxRICH"
    }
  }
}

(Note: If no phone number is provided, the API will return a 400 Bad Request error.)
👨‍💻 Developer & Community
 * Developer: @Smugllers
 * Telegram Group: @MAGMAxRICH
 * Support / API By: @Anysnapsupport
 * GitHub: themagmalord333-oss

