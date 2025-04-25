# 🧪 API Testing Project — Tasfia Zaima

This repository contains a complete Postman test suite for a **Booking API**, developed and automated by **Tasfia Zaima**. It covers creating, retrieving, updating bookings, and validating responses using dynamic environment variables and randomized test data.

---

## 📦 Features

- 🔄 **Dynamic Test Data Generation** using Moment.js and randomization
- ✅ **Automated Test Validations** with Postman Test scripts
- 🔐 **Token Generation & Authorization**
- 📥 **GET Booking Validations**
- ✏️ **PUT Booking Updates**
- 📄 **Newman HTML Report** for execution summary

---

## 🧰 Technologies Used

- [Postman](https://www.postman.com/)
- [Moment.js](https://momentjs.com/)
- [Newman](https://www.npmjs.com/package/newman)

---

## 🔧 Setup Instructions

1. Clone this repository.
2. Import the Postman collection and environment.
3. Install dependencies for running Newman:
   ```bash
   npm install -g newman
   ```
4. Run the collection with:
   ```bash
   newman run <collection.json> -e <environment.json> -r html --reporter-html-export Booking-2025-04-25-06-00-10-902-0.html
   ```

---

## 📤 POST Request: Create Booking

**Body:**
```json
{ 
 "firstname": "{{firstName}}", 
 "lastname": "{{lastName}}", 
 "totalprice": {{totalprice}}, 
 "depositpaid": {{depositpaid}}, 
 "bookingdates": { 
   "checkin": "{{checkin}}", 
   "checkout": "{{checkout}}" 
 }, 
 "additionalneeds": "{{additionalneeds}}" 
}
```

**Pre-request Script Highlights:**
- Random name generation
- Date manipulation using `moment`
- Random `totalprice`, `depositpaid`, and `additionalneeds`

---

## 📥 GET Request: Retrieve Booking

**Validation Tests:**
- Status code
- First name, last name
- Check-in/check-out dates
- Total price, deposit paid
- Additional needs

---

## 🔐 POST Request: Token Generation

**Body:**
```json
{
  "username": "admin",
  "password": "password123"
}
```

**Script:**
```javascript
var data = pm.response.json();
pm.environment.set("token", data.token);
```

---

## ✏️ PUT Request: Update Booking

**Body:**
```json
{
 "firstname": "{{firstName}}",
 "lastname": "{{lastName}}",
 "totalprice": 7000,
 "depositpaid": true,
 "bookingdates": {
   "checkin": "{{checkin}}",
   "checkout": "{{checkout}}"
 },
 "additionalneeds": "Snacks"
}
```

---

## 📊 Newman Report

A full HTML Newman report is included to visualize test run results.

📁 **File Name:** `Booking-2025-04-25-06-00-10-902-0.html`  
📸 **Sample Screenshot:**  
![Newman Report Screenshot](path/to/screenshot.png)

---
## 📸 Newman Report Screenshots

Here is the Newman report:

![Newman1](Newman1.JPG)
![Newman2](Newman2.JPG)

## 📝 Author

**Tasfia Zaima**  

---

Let me know if you'd like me to export this as a `README.md` file or add a placeholder image for the report screenshot!
