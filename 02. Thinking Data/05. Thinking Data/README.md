# 🧹 Customer Data Cleaning & Preprocessing (AIML)

This project demonstrates **real-world data cleaning techniques** using Python and Jupyter Notebook. It focuses on handling **missing data**, **inconsistent data types**, and **duplicate records**, which are critical steps before applying any **AI / Machine Learning model**.


## 📌 Thinking Data Overview

In real-world applications, data is rarely clean. This repository shows how to:

- Load JSON data
- Identify and handle **missing values**
- Convert **text-based numeric data** into numbers
- Handle **float vs integer inconsistencies**
- Remove **duplicate records**
- Prepare data for **Machine Learning**

The project uses a small but realistic customer feedback dataset to explain these concepts clearly.



## 📂 Project Structure

```
├── customer_data.json      # Raw customer data (messy, real-world style)
├── ThinkingData.ipynb      # Jupyter Notebook with cleaning logic
├── README.md               # Project documentation
```



## 📊 Example Dataset (`customer_data.json`)

```json
[
  {
    "name": "Alice",
    "rating": "5",
    "feedback": "Great product!!",
    "age": "25"
  },
  {
    "name": "Bob",
    "rating": "four",
    "feedback": "ok but late Delivery",
    "age": "30"
  },
  {
    "name": "Charlie",
    "rating": "two",
    "feedback": "BAD EXPERIENCE"
  },
  {
    "name": "Diana",
    "rating": "5",
    "feedback": "Loved it!",
    "age": "28"
  },
  {
    "name": "Eve",
    "rating": "3.5",
    "feedback": "Average - could be better",
    "age": "20"
  },
  {
    "name": "Alice",
    "rating": "5",
    "feedback": "Great product again!",
    "age": "25"
  }
]
```

🔴 Notice the problems:
- Ratings stored as **text**, **numbers**, and **floats**
- Missing `age` value for one customer
- Duplicate entry for **Alice**



## ❓ What Is Missing Data?

**Missing data** occurs when a value is not present for a feature (column).

Example:
```json
{
  "name": "Charlie",
  "rating": "two",
  "feedback": "BAD EXPERIENCE"
}
```

➡️ `age` is missing



## ⚠️ Why Missing Data Is a Problem

Missing data can:

- ❌ Cause **runtime errors** (`KeyError`)
- ❌ Break ML models (most models require complete numeric data)
- ❌ Reduce model accuracy
- ❌ Bias predictions

📌 **Important:**
> Machine Learning models **cannot guess missing values automatically**.



## 🛠 Handling Missing Data

(Simple version – same style as notebook)

```python
# handle missing age value

def handleMissing(data):
    for user in data:
        agedata = user.get("age")
        if(agedata == None):
            user["age"] = "Null"   # default value for missing age
```

✔ Beginner-friendly and easy to understand



## 🔢 Cleaning Inconsistent Numeric Data

Ratings appear as:
- "four"
- "5"
- "3.5"

### ✅ Convert Text Ratings to Numbers

```python
# cleaning data four --> 4

def clean_data(data):
    # map to fix numeric data
    text_to_num = {
        "one": 1,
        "two": 2,
        "three": 3,
        "four": 4,
        "five": 5
    }

    for user in data:
        rating = user["rating"].strip().lower()

        if rating in text_to_num:
            rating = text_to_num[rating]

        user["rating"] = rating
```python
def clean_ratings(data):
    # map text ratings to numbers
    text_to_num = {
        "one": 1,
        "two": 2,
        "three": 3,
        "four": 4,
        "five": 5
    }

    for user in data:
        # take rating and normalize text
        rating = user["rating"].strip().lower()

        # convert text rating to number
        if rating in text_to_num:
            user["rating"] = text_to_num[rating]
        else:
            # convert numeric string or float-like value
            user["rating"] = float(rating)
```python
def clean_ratings(data):
    text_to_num = {
        "one": 1,
        "two": 2,
        "three": 3,
        "four": 4,
        "five": 5
    }

    for user in data:
        rating = user["rating"]

        if isinstance(rating, str):
            rating = rating.strip().lower()
            if rating in text_to_num:
                rating = text_to_num[rating]
            else:
                rating = float(rating)

        user["rating"] = rating
```



## 🔄 Handling Float vs Integer Ratings

(Simple approach used in notebook)

```python
# 4.5 → 4

def float_to_int(data):
    for user in data:
        if 0 <= float(user["rating"]) <= 9:
            user["rating"] = int(float(user["rating"]))
```python
def float_to_int(data):
    for user in data:
        # convert float rating like 3.5 → 3
        user["rating"] = int(user["rating"])
```python
def float_to_int(data):
    for user in data:
        if isinstance(user["rating"], float):
            user["rating"] = int(user["rating"])
```



## 🧹 Removing Duplicate Records

Duplicate data biases models and inflates statistics.

### ❌ Problem Example

```json
{
  "name": "Alice",
  "rating": "5"
}
```
Appears **twice**

### ✅ Solution

```python
def remove_duplicates(data):
    seen = set()        # store unique names
    result = []        # store cleaned data

    for user in data:
        # normalize name (remove spaces, lowercase)
        name = user.get("name", "").strip().lower()

        # if name not seen before, keep record
        if name not in seen:
            seen.add(name)        # mark name as seen
            result.append(user)   # add user to result

    return result
```python
def remove_duplicates(data):
    seen = set()
    result = []

    for user in data:
        name = user.get("name", "").strip().lower()
        if name not in seen:
            seen.add(name)
            result.append(user)

    return result
```



## 🚀 Why Data Cleaning Is Critical for AIML

| Step | Reason |
|----|----|
| Missing data handling | Prevent crashes & bias |
| Numeric conversion | Models need numbers |
| Duplicate removal | Prevent data leakage |
| Type consistency | Stable training |

📌 **80% of ML work is data preprocessing**



## ▶️ How to Run This Project

1. Clone the repository
2. Open Jupyter Lab / Notebook
3. Run `ThinkingData.ipynb` step by step
4. Observe data before & after cleaning



## 🧠 Learning Outcomes

By completing this project, you will understand:

- Real-world data issues
- Why preprocessing matters
- How data affects ML models
- How to build a clean data pipeline



## 📌 Future Improvements

- Convert data to Pandas DataFrame
- Add data validation rules
- Visualize ratings
- Feed cleaned data into ML model



## ⭐ If You Found This Helpful

Give the repo a ⭐ and keep learning AIML 🚀

