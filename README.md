# Bookstore Management System

This is a Django-based backend project that provides full CRUD functionality for managing books and authors in a bookstore inventory. It also integrates with the Google Books API to search and fetch book data.

## Features

- Full CRUD operations for books and authors
- Sorting inventory by title or price (ascending or descending)
- Search for books by title and/or author
- Integration with Google Books API:
  - Search and fetch book details
  - Add books directly from Google
  - Bulk add up to 10,000 books
- Bulk delete books by title
- JSON-based API responses (no frontend included)

## Technologies Used

- Python 3.11
- Django 4.x
- SQLite3 (default Django database)
- Requests (for Google Books API integration)

## Project Structure

├── inventory/ # Django app: book & author models, views, and routes │ ├── migrations/ │ ├── admin.py │ ├── apps.py │ ├── models.py │ ├── tests.py │ ├── urls.py │ └── views.py │ ├── readers_haven/ # Django project configuration │ ├── init.py │ ├── asgi.py │ ├── settings.py │ ├── urls.py │ └── wsgi.py │ ├── manage.py ├── requirements.txt └── README.md


## Installation and Running

1. Clone the repository:

git clone https://github.com/AbdellahSbh/Bookstore_management_system_project.git cd Bookstore_management_system_project

2. Create a virtual environment and activate it:

python -m venv env env\Scripts\activate # On Windows 
source env/bin/activate # On macOS/Linux

3. Install dependencies:

pip install -r requirements.txt


4. Run database migrations:

python manage.py makemigrations python manage.py migrate


5. Start the development server:

python manage.py runserver


## API Endpoints

### Books

| Endpoint                   | Method | Description                                              |
|---------------------------|--------|----------------------------------------------------------|
| /sort_inventory           | GET    | Sort books by title or price (AtoZ, ZtoA, Asc, Desc)     |
| /search_books             | GET    | Search books from Google API by title or author          |
| /add_books                | GET    | Add a new book manually (title, authors, price, stock)   |
| /update_book              | GET    | Update an existing book’s information                    |
| /delete_book              | GET    | Delete a book by title                                   |
| /fetch_books_from_google  | GET    | Fetch a list of books via keyword search                 |
| /fetch_and_add_book       | GET    | Search Google and auto-add the first book result         |
| /bulk_add_books           | GET    | Bulk import up to 10,000 books from Google Books         |
| /bulk_delete_books        | GET    | Delete multiple books by passing a list of titles        |

### Authors

| Endpoint       | Method | Description                               |
|----------------|--------|-------------------------------------------|
| /add_authors   | GET    | Add a new author (name and optional bio)  |
| /get_authors   | GET    | Retrieve all existing authors             |

## Notes

- All endpoints are accessed using the GET method for simplicity, but REST best practices recommend using POST, PUT, DELETE for data modification.
- Input validation and error handling are implemented.
- The system assumes authors already exist when adding a book manually.

## License

This project is developed for academic purposes as part of the Programming Clinic module at Lancaster University Leipzig, Michaelmas Term 2025.


