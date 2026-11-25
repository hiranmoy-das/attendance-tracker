<div align="center">

# 📋 Smart Student Attendance Management System

*A lightweight, desktop-first attendance tracking application powered by Python, Tkinter, and Pandas.*

[![Python 3.x](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![GUI: Tkinter](https://img.shields.io/badge/GUI-Tkinter-FF6F00?style=for-the-badge)](https://docs.python.org/3/library/tkinter.html)
[![Data: Pandas](https://img.shields.io/badge/Data-Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-2EA44F?style=for-the-badge)](LICENSE)

[**About**](#-about-the-project) • [**Architecture**](#-system-architecture--data-flow) • [**Quick Start**](#-quick-start-guide) • [**Storage Schema**](#-csv-storage-schema) • [**Roadmap**](#-future-enhancements)

</div>

---

## 🎯 About the Project

Managing daily classroom attendance manually is repetitive and error-prone. **Smart Student Attendance Management System** replaces paper registers with a clean, offline-ready desktop GUI built in Python. It enables educators and administrators to authenticate securely, enroll students with unique ID validation, and log daily attendance directly into structured, spreadsheet-compatible CSV records.

### Key Highlights

| Capability | Description |
| :--- | :--- |
| **Role-Gated Access** | Built-in login verification prevents unauthorized edits to attendance logs. |
| **UID Integrity Checks** | Automatically detects and blocks duplicate Student UIDs during enrollment. |
| **Automated Date Indexing** | Dynamically appends new `YYYY-MM-DD` columns to the master CSV upon daily submission. |
| **Zero-Database Overhead** | Uses Pandas and local CSV storage—no external server setup required. |
| **Full Roster Control** | Add, update, or remove student profiles and review historical attendance at a glance. |

---

## 📸 Interface Preview

<div align="center">
  <img src="image_attendance_tracker.jpg" alt="Attendance Tracker Application Dashboard" width="80%">
  <br>
  <em>Main desktop workspace featuring student enrollment, daily status toggles, and record management.</em>
</div>

---

## 🔄 System Architecture & Data Flow

```text
┌───────────────────┐     ┌──────────────────────┐     ┌─────────────────────────┐
│  1. Authentication│ ──► │ 2. Roster Management │ ──► │ 3. Daily Attendance Log │
│  (Login Screen)   │     │ (Add/Edit/Verify UID)│     │ (Mark 'P' or 'A' Status)│
└───────────────────┘     └──────────────────────┘     └────────────┬────────────┘
                                                                    │
                                                                    ▼
┌───────────────────┐     ┌──────────────────────┐     ┌─────────────────────────┐
│  5. Audit & Export│ ◄── │ 4. Dynamic Schema    │ ◄── │  Pandas DataFrame Engine│
│  (Excel / Sheets) │     │ (Auto-Date Columns)  │     │  (attendance_records.csv)│
└───────────────────┘     └──────────────────────┘     └─────────────────────────┘
```

### Repository Layout

```text
attendance-tracker/
├── attendance_tracker.py        # Core Tkinter GUI, auth logic, and Pandas handlers
├── attendance_records.csv       # Auto-generated master attendance ledger
├── image_attendance_tracker.jpg # UI preview screenshot
├── LICENSE                      # MIT License terms
└── README.md                    # Project documentation
```

---

## ⚡ Quick Start Guide

### 1. System Requirements
- **Python:** Version 3.8 or higher
- **Libraries:** `pandas` (standard `tkinter` and `datetime` are bundled with Python)

### 2. Clone & Install

```bash
# Clone the repository
git clone [https://github.com/hiranmoydas/attendance-tracker.git](https://github.com/hiranmoydas/attendance-tracker.git)
cd attendance-tracker

# Install Pandas
pip install pandas
```

> **Linux Users:** If Tkinter is missing from your Python build, install it via your package manager:
> `sudo apt-get install python3-tk` (Ubuntu/Debian) or `sudo dnf install python3-tkinter` (Fedora).

### 3. Launch the Application

```bash
python attendance_tracker.py
```

---

## 💾 CSV Storage Schema

On first run, the system initializes `attendance_records.csv` and appends a new date column each time attendance is recorded:

| Name | UID | 2026-01-15 | 2026-01-16 | 2026-01-17 |
| :--- | :---: | :---: | :---: | :---: |
| John Doe | `001` | `P` | `P` | `A` |
| Jane Smith | `002` | `P` | `A` | `P` |
| Alex Johnson | `003` | `A` | `P` | `P` |

- **`P`** — Present
- **`A`** — Absent

---

## 🛠️ Troubleshooting

<details>
<summary><strong>ModuleNotFoundError: No module named 'pandas'</strong></summary>
<br>
Ensure you are installing Pandas into the same Python environment used to run the script:
<pre><code>python -m pip install pandas</code></pre>
</details>

<details>
<summary><strong>Tkinter GUI fails to launch</strong></summary>
<br>
Verify your Tkinter installation by running <code>python -m tkinter</code>. A small test dialog should appear. If it fails, reinstall Python with Tcl/Tk support enabled.
</details>

<details>
<summary><strong>PermissionError when saving attendance</strong></summary>
<br>
Close <code>attendance_records.csv</code> if it is currently open in Microsoft Excel or another spreadsheet editor before clicking Save inside the app.
</details>

---

## 🗺️ Future Enhancements

- [ ] **SQLite Backend Support** — Migrate from flat CSV files to relational storage for large institutions.
- [ ] **Automated Analytics Dashboard** — Generate percentage reports and low-attendance alerts.
- [ ] **QR / Barcode Check-In** — Scan student ID cards for instant attendance marking.
- [ ] **One-Click PDF & Excel Reports** — Export formatted monthly summaries.
- [ ] **Modern UI Themes** — Add dark mode and custom color palettes.

---

## 🤝 Contributing

Contributions, bug reports, and feature requests are always welcome:

1. Fork this repository
2. Create a feature branch (`git checkout -b feature/amazing-improvement`)
3. Commit your changes (`git commit -m "Add amazing improvement"`)
4. Push to your branch (`git push origin feature/amazing-improvement`)
5. Open a Pull Request

---

## 📜 License & Author

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for full details.

<div align="center">

**Developed by [Hiranmoy Das](https://github.com/hiranmoydas)**  
*Built with Python, Tkinter & Pandas*

</div>
