# 🏥 Nurse Scheduling Problem (NSP)

## 📌 Overview  
This project implements an **optimized nurse scheduling system** using **Linear Programming (LP)** with **PuLP**. It assigns **32 nurses** over a **31-day period**, ensuring:  
- **Fair workload distribution**  
- **Regulatory compliance**  
- **Shift demand fulfillment**  
- **Nurse preferences (preferred/off days)**  

The output is **JSON-formatted** for easy integration into hospital management systems.

---

## ✨ Features  

✅ **Optimized nurse assignments** across **day, evening, and night shifts**  
✅ **Fair workload distribution** (max shifts per nurse per month/day)  
✅ **Shift demand satisfaction** (CNL, Head Nurse, and Regular Nurse requirements)  
✅ **Regulation compliance** (no consecutive night-to-morning shifts)  
✅ **Nurse preferences handled** (preferred and off days)  
✅ **JSON-formatted output** for easy integration  
✅ **Penalty-based demand balancing** to adjust scheduling conflicts  
✅ **Ensures leadership presence** (at least one CNL or Head Nurse per shift)  

---

## 📅 Problem Description  

The schedule assigns **nurses** to three daily shifts:  
-  **Day Shift** 
-  **Evening Shift** 
-  **Night Shift**

Each nurse is assigned a **unique ID (0-31)** and belongs to one of the following roles:  
- **CNL (Clinical Nurse Leader)** → ID **0**  
- **Head Nurse** → IDs **1–5**  
- **Regular Nurse** → IDs **6–31**  

### ✅ Constraints & Rules  
✔ **Shift Demand Compliance:** Ensures the required number of nurses per shift.  
✔ **Leadership Presence:** At least **one Head Nurse or CNL per shift**.  
✔ **Fair Workload:** Limits **max shifts per nurse per month** (**31**) and **per day** (**2**).  
✔ **No Night-to-Morning Transition:** Prevents consecutive **night → day** shifts.  
✔ **Nurse Preferences:** Enforces **preferred working days** and **off-days**.  
✔ **Penalty-based Demand Balancing:** Minimizes over/understaffing with penalties.  

---


## Output Format
- The script generates a JSON schedule with:
- **Date and weekday**
- **Shift type (day, evening, night)**
- **Assigned nurses (ID and role)**
- **Head Nurse and CNL assignments**
  
### Example Output
```
[
    {
        "date": "2024-01-01",
        "weekday": "Monday",
        "shift": "day",
        "nurses_assigned": [
            {"id": 7, "role": "Nurse"},
            {"id": 1, "role": "Head"}
        ],
        "head_nurse": {"id": 1, "role": "Head"},
        "cnl_nurse": {"id": null, "role": "None"}
    },
    {
        "date": "2024-01-01",
        "weekday": "Monday",
        "shift": "night",
        "nurses_assigned": [
            {"id": 12, "role": "Nurse"},
            {"id": 2, "role": "Head"}
        ],
        "head_nurse": {"id": 2, "role": "Head"},
        "cnl_nurse": {"id": null, "role": "None"}
    }
]
```

## ⚡ Installation  

Clone the repository and install dependencies:  
```bash
git clone https://github.com/pirsarandib/nurse_scheduling_problem
cd nurse-scheduling
pip install pulp  
```
