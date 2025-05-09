# Bookstore Management System 📚

This is a Django-based backend project that provides full CRUD functionality for managing books and authors in a bookstore inventory. It also integrates with the Google Books API to search and fetch book data.

---

## 📌 Features

- Full CRUD operations for books and authors
- Sorting inventory by title or price (ascending or descending)
- Search for books by title and/or author
- Integration with Google Books API:
  - Search and fetch book details
  - Add books directly from Google
  - Bulk add up to 10,000 books
- Bulk delete books by title
- JSON-based API responses (no frontend)

---

## 🛠️ Technologies Used

- Python 3.11
- Django 4.x
- SQLite3 (default Django database)
- `requests` library (for Google Books API integration)

---

## 📁 Project Structure

```text
bookstore/
├── inventory/                # Django app for book & author logic
│   ├── migrations/
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── readers_haven/           # Django project config
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
├── requirements.txt
└── README.md
```

---

## 🚀 Installation & Running

### 1. Clone the repository

```bash
git clone https://github.com/AbdellahSbh/Portfolio_Bookstore_Management_by_AbdellahSbh.git
cd Portfolio_Bookstore_Management_by_AbdellahSbh
```

### 2. Create a virtual environment and activate it

```bash
# Windows
python -m venv env
env\Scripts\activate

# macOS/Linux
python3 -m venv env
source env/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Start the development server

```bash
python manage.py runserver
```

---

## 📡 API Endpoints

### Books

```text
GET  /sort_inventory            → Sort books by title or price (AtoZ, ZtoA, Asc, Desc)
GET  /search_books              → Search books from Google API by title or author
GET  /add_books                 → Add a new book manually
GET  /update_book              → Update book information
GET  /delete_book              → Delete a book by title
GET  /fetch_books_from_google   → Search and list books from Google Books API
GET  /fetch_and_add_book        → Search and auto-add the first Google book result
GET  /bulk_add_books            → Bulk import books from Google Books API
GET  /bulk_delete_books         → Bulk delete books by title
```

### Authors

```text
GET  /add_authors     → Add a new author (name and optional bio)
GET  /get_authors     → Retrieve all existing authors
```

---

## 📝 Notes

- All endpoints use the GET method for simplicity, but actual REST APIs would use POST, PUT, or DELETE for changes.
- Input validation and basic error handling are implemented.
- The system assumes authors already exist when adding books manually.

---

## 📄 License

This project is developed for academic purposes as part of the Programming Clinic module  
at Lancaster University Leipzig – Michaelmas Term 2025.
