# 📚 Book Management System with FastAPI

This project is a simple yet functional **Book Management API** built using **FastAPI**. It demonstrates RESTful API principles and Python backend development skills by simulating a library/bookstore system. The API allows users to **add**, **search**, **borrow**, **return**, and **delete books**, with features such as **fine calculation**, **prime number filtering**, and **analytics** on most borrowed books.

---

## 💡 Thought Process & Design Philosophy

This project was designed to solve a common library use case: tracking and managing books programmatically. I broke down the functionality into clear endpoints and data models using FastAPI and Pydantic. The data is stored in a Python list for simplicity, mimicking a basic in-memory database.

Key goals:

* Learn and apply REST API development with FastAPI
* Implement core library functionalities
* Understand request/response handling using Pydantic models
* Practice modular, readable, and extensible code organization

---

## 🚀 How to Run This Project

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/book-management-fastapi.git
   cd book-management-fastapi
   ```

2. Install dependencies:

   ```bash
   pip install fastapi uvicorn
   ```

3. Run the server:

   ```bash
   uvicorn main:app --reload
   ```

4. Visit the interactive docs at: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)



## 🧩 Project Structure

### 📁 Models

Defined using `Pydantic` for request validation:

* `BookFullRequest`: For full data (title, author, and ID)
* `BookRequest`: Partial data model
* `BookNameRequest`: Accepts only book title
* `BookAuthorRequest`: Accepts only author name



## 📌 API Endpoints & Functionality

### 📖 View All Books

**`GET /all-books`**
Returns all books currently in the system.

### 🔍 Get Book by Title

**`POST /get-book-by-name`**
Finds books by their title. Case-insensitive.

### 🔍 Get Books by Author

**`POST /get-books-by-author`**
Finds books by author's name.

### ➕ Add a Book

**`POST /add-book`**
Adds a new book only if the title-author combo doesn't already exist.

### ❌ Delete Book by Title

**`POST /delete-by-name`**
Removes a book using its title.

### 📥 Borrow Book by Author

**`POST /borrow-book-by-author`**
Borrows a book using the author's name if it's available on the shelf.

### 📥 Borrow Book by Title

**`POST /borrow-book-by-title`**
Borrows a book using the title.

### 📤 Return Book by Author

**`POST /return-book-by-author`**
Returns a borrowed book and calculates the fine (if overdue).

### 📤 Return Book by Title

**`POST /return-book-by-title`**
Same as above but uses title instead of author.

### 💰 Fine Calculation Logic

**`pay_fine(present_book)`**

* No fine for the first 14 days
* ₦500/day fine after that

### 🧮 Get Books with Prime Number Suffix

**`GET /get-prime-suffix`**
Returns books whose titles end in a **prime number** (e.g. "Clean Code 7").

### 📚 Get Borrowed Books

**`GET /get-borrowed-books`**
Returns books that are currently borrowed (not in shelf).

### 📗 Get Available Books

**`GET /get-available-books`**
Returns books that are currently available in the shelf.

### 🔝 Most Borrowed Book

**`GET /most-borrowed-book`**
Returns the book(s) that have been borrowed the most number of times.



## 🧠 Helper Functions

* **`is_prime(n)`**
  Checks if a given number is a prime using an efficient square-root method.

* **`get_book_by_title(title)`**
  Matches titles (case-insensitive) and returns matching books or "not found".

* **`get_all_books()`**
  Returns the entire books list.



## 🔧 Sample Book Data

Books are stored as a list of dictionaries with fields like:

```python
{
    "id": 101,
    "title": "The Pragmatic Programmer 1",
    "author": "Andrew Hunt",
    "in_shelf": True,
    "times_borrowed": 5
}
```

Some books include a `borrow_date` field to track when they were borrowed and determine if a fine applies.


## 🙋‍♀️ Author

**Eyitoyosi Alabi**

* [LinkedIn](https://linkedin.com/in/eyitoyosi-alabi-bab6011b4)
* [GitHub](https://github.com/Eyitoyosi)
* Data Scientist | Python Developer | Aspiring AI Engineer


