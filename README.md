# 🏨 Hotel Management System — Kivy

A desktop **Hotel Management System** built with **Python, Kivy, and SQLite**. The application provides a graphical interface for managing hotel rooms, guests, and bookings, including check-in, check-out, and automatic bill calculation.

## 📌 Project Overview

This project is designed to simplify basic hotel management operations through a simple desktop GUI.

The system allows hotel staff to:

- Manage hotel rooms
- Register and manage guests
- Check guests in and out
- Track room availability
- Maintain active bookings
- Maintain booking history
- Automatically calculate bills based on the number of nights stayed

## ✨ Features

### 🛏️ Rooms Management
- Add rooms with:
  - Room number
  - Room type
  - Price per night
- Supported room types:
  - Single
  - Double
  - Suite
  - Deluxe
- View room status as **Available** or **Occupied**
- Delete selected rooms
- Prevent duplicate room numbers

### 👤 Guest Management
- Add guest details:
  - Name
  - Phone number
  - Email
- View registered guests
- Delete guest records

### 📅 Booking Management
- Select a guest and available room for check-in
- Automatically mark a checked-in room as **Occupied**
- View active bookings
- Check out selected bookings
- Automatically calculate the total bill
- Automatically change the room status back to **Available**
- Maintain permanent booking history

### 💰 Automatic Bill Calculation

The total bill is calculated using:

```text
Total Bill = Number of Nights × Price Per Night
```

A minimum charge of one night is applied, even for a same-day checkout.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Application logic |
| Kivy | Graphical User Interface |
| SQLite | Local database |
| `sqlite3` | Database operations |
| `datetime` | Date and checkout calculations |

## 🗄️ Database Structure

The application uses a local SQLite database named:

```text
hotel.db
```

The database is created automatically when the application is run for the first time.

It contains three main tables:

### `rooms`
Stores room information such as room number, room type, price, and availability status.

### `guests`
Stores guest information including name, phone number, and email.

### `bookings`
Stores booking information including room, guest, check-in date, check-out date, booking status, and total bill.

## 🏗️ Project Architecture

The application is organized into three main layers:

### 1. Database Layer
The `Database` class handles SQLite operations such as:

- Creating tables
- Adding and deleting rooms
- Adding and deleting guests
- Creating bookings
- Checking out bookings
- Retrieving active and historical bookings

### 2. UI Helper Layer
Reusable components are used for:

- Information and confirmation popups
- Table rows
- Scrollable table views

### 3. Screen Layer

The application contains separate screens for:

- `RoomsScreen`
- `GuestsScreen`
- `BookingsScreen`

A `ScreenManager` is used to switch between the screens.

## 📁 Project Structure

```text
Hotel-Management-System-Kivy/
│
├── hotel_management_kivy.py
├── requirements.txt
├── README.md
├── screenshots/
│   ├── rooms.png
│   ├── guests.png
│   └── bookings.png
│
└── documentation/
    └── Hotel_Management_System_Documentation.pdf
```

> The `screenshots` and `documentation` folders are optional and can be added when organizing the GitHub repository.

## ⚙️ Requirements

- Python **3.8 or higher**
- Kivy

## 🚀 Installation & Running

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Open the project folder

```bash
cd Hotel-Management-System-Kivy
```

### 3. Install the required package

```bash
pip install -r requirements.txt
```

### 4. Run the application

```bash
python hotel_management_kivy.py
```

### 5. Database creation

On the first launch, the application automatically creates:

```text
hotel.db
```

The database stores room, guest, and booking information locally.

## 🖥️ Application Navigation

The application provides three main sections:

```text
Hotel Management System

├── Rooms
│   ├── Add Room
│   ├── View Rooms
│   └── Delete Room
│
├── Guests
│   ├── Add Guest
│   ├── View Guests
│   └── Delete Guest
│
└── Bookings
    ├── Check-In
    ├── Active Bookings
    ├── Check-Out
    └── Booking History
```

## 🔒 Data Integrity

The system includes several basic data-integrity rules:

- Room numbers must be unique.
- Only available rooms are displayed for check-in.
- Checking in changes a room to **Occupied**.
- Checking out changes the room back to **Available**.
- Completed bookings remain in booking history.
- SQLite foreign keys are enabled for room and guest relationships.

## ⚠️ Current Limitations

The current version does not include:

- Staff login/authentication
- Search or filtering
- PDF invoice/receipt export
- Editing existing rooms or guests
- Network/multi-user database support
- Future date-range room availability

The application is designed for **single-user, single-computer use** with a local SQLite database.

## 🔮 Future Enhancements

Possible improvements include:

- 👤 Staff authentication and login
- ✏️ Edit room and guest information
- 🧾 PDF invoice generation
- 🔍 Search and filtering
- 📅 Future booking and date-range availability
- 📱 Packaging the application as a mobile app using Kivy's Android/iOS build tools

## 🧪 Troubleshooting

### `ModuleNotFoundError: No module named 'kivy'`

Install Kivy:

```bash
pip install kivy
```

Or install all dependencies:

```bash
pip install -r requirements.txt
```

### Room already exists

Room numbers must be unique. Check the Rooms section for an existing room with the same number.

### Data appears to be missing

Make sure `hotel.db` is located in the same folder from which the application is being run. Running the application from a different directory can create a new database file.

## 📚 Documentation

Detailed project documentation is included in the repository and covers:

- Project overview
- Requirements
- Installation
- Features
- Database structure
- Python code
- Code architecture
- Business logic
- Limitations
- Future enhancements
- Troubleshooting

## 👩‍💻 Author

**Bhagwagar Krishita**

B.Sc.IT — Department of Computer Science  
Vanita Vishram, Surat

## ⭐ Project Purpose

This project was developed as part of an **Advanced Python** project to demonstrate the use of Python, Kivy GUI development, SQLite database management, and application-level business logic.

---

⭐ If you find this project useful, consider giving the repository a star!
