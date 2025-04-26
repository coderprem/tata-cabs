# 🚖 Tata Cabs – Android App for Smart Cab Booking in Power Plant Environment

Tata Cabs is a real-world Android application built for employees working inside a power plant environment to streamline cab bookings and eliminate inefficiencies caused by the traditional manual process. It includes two modules:
- **Tata Cabs** – Employee (User) App
- **Tata Drivers** – Driver App

> 🔧 Built with **Jetpack Compose**, **MVVM Architecture**, **Firebase**, **Google Maps**, **Dagger Hilt**, and more.

---

## 📽️ Demo & Showcase

🎥 **App Demo Video**: [Watch on GitHub](https://github.com/user-attachments/assets/1008b457-ee9d-4ddc-9587-c0d11950192f)  
🔗 **LinkedIn Project Post**: [See on LinkedIn](https://www.linkedin.com/posts/coderprem_opentowork-androiddeveloper-kotlin-activity-7316476853165142017-sY6E?utm_source=share&utm_medium=member_desktop&rcm=ACoAADvE3xUBqM8yexe04EBquKaOLn-GIBRnzkA)

---

## 📌 Problem Statement

At a power plant where ~20 drivers are hired, employees traditionally call drivers one by one to book a ride. Issues included:
- No central system to check driver availability or current ride status
- Employees had to split total monthly fare equally across departments
- Drivers sometimes picked rides far away or with no seats available
- No verification or filtering system for ride misuse or fake bookings

---

## ✅ Solution Overview

Tata Cabs solves the above with:
- **Smart driver assignment** using location + seat availability
- **OTP-based secure login**
- **Automatic monthly billing** per department
- **Live tracking and ride management**
- **Role-based access and login restriction**
- **Real-time push notifications using Cloud Functions**

---

## 🧠 Core Features

### 🔐 Authentication
- OTP login using Firebase Auth
- Phone Selector API for auto-fetching mobile number
- Registered driver verification using Firestore collection
- Multiple login prevention using UID & DataStore

### 🚗 Ride Booking (User App)
- Select drop location from predefined list
- Smart nearest driver allocation based on availability & distance
- Realtime route display using Google Maps
- Ride details shown in bottom sheet with contact options
- Notifications sent to driver on booking/cancel

### 📍 Driver App Features
- See new ride assignments with pickup/drop markers on map
- Ride acceptance/decline options
- "Pickup" & "Complete Ride" buttons with logic-based constraints
- Availability toggle to go offline if not active
- Color-coded markers (Yellow = Pickup, Red = Drop, Blue = In-Progress)

### 🧾 Billing & Reports
- Monthly bill auto-generated using Cloud Function
- Department-wise ride tracking and billing
- Email sent to department heads with Excel report:


### 📊 Upcoming Features
- In-app dashboards for:
- Employees (total rides, total km, fare usage)
- Drivers (completed rides, distance, incentives)
- Pagination & local caching
- Kotlin Multiplatform support (Android + iOS)

---

## 🛠️ Tech Stack

| Layer              | Tech Used |
|-------------------|-----------|
| UI                | Jetpack Compose, Material3, Lottie, Accompanist |
| State Management  | ViewModel, LiveData, Compose State, DataStore |
| Navigation        | Jetpack Navigation Component |
| Dependency Injection | Dagger Hilt |
| Location & Maps   | Google Maps Compose, Maps KTX, Location Services |
| Authentication    | Firebase Auth (Phone & Google) |
| Backend & Storage | Firebase Firestore, Firebase Functions, Firebase Messaging |
| Networking        | Retrofit, OkHttp, Gson Converter, OAuth2 HTTP |
| Local Storage     | DataStore Preferences, Kotlin Serialization |
| Media             | Coil for image loading |

---

## 📦 App Modules

### `Tata Cabs` – User Module
- Employee profile setup
- Ride booking & tracking
- Past ride history
- Monthly usage dashboard (planned)

### `Tata Driver` – Driver Module
- Real-time ride assignment
- Pickup/drop workflow with constraints
- Past ride logs
- Availability toggle
- Notifications for new/cancelled rides

---

## 🔒 Security & Abuse Prevention

- OTP login required for access
- Only one device login per user/driver
- Employees can't complete a ride until:
- Driver has marked it "Picked up"
- Employee is within 150m of destination
- Inactive drivers are flagged offline via scheduled Cloud Function (every 8h)
- Users can't edit phone number or department once registered

---

## 🔔 Firebase Cloud Functions

| Trigger | Action |
|--------|--------|
| On New Ride | Send notification to assigned driver |
| On Ride Cancel | Notify relevant party |
| On 1st of Month | Generate billing per department |
| Every 8h | Check driver last active location, mark inactive if stale |
| On Status Change | Sync status across user/driver apps |

---

## 📧 Monthly Excel Report Structure

Generated and emailed automatically to department heads:
```text
Columns: Ride ID, Employee Name, Employee Number, Pickup, Destination, Distance, Completed At, Driver Name, Driver Number, Fare
Row: Grand total (rides, fare, distance)
```
## 🚀 Future Roadmap

- [ ] Dashboard analytics with charts  
- [ ] Driver incentives per km  
- [ ] Kotlin Multiplatform (KMP) integration  
- [ ] Admin web panel for monitoring  

---

## 👨‍💻 Author

**Prem Kumar**  
📧 [erprem013@gmail.com](mailto:erprem013@gmail.com)  
🔗 [LinkedIn](https://www.linkedin.com/in/coderprem/)  
💻 [GitHub](https://github.com/coderprem)

---

## 🏷️ Tags

`#AndroidDev` `#JetpackCompose` `#Firebase` `#MVVM` `#MobileApp` `#DaggerHilt` `#GoogleMaps` `#Kotlin` `#PowerPlantApp` `#CloudFunctions`
