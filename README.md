# EgyBooks - Online Library Website

A comprehensive Django-based online library management system that allows users to browse, search, purchase, and borrow books. The platform features a user-friendly interface with advanced search capabilities, shopping cart functionality, and a personal library management system.

## 📚 Features

### User Features
- **User Authentication & Profiles**
  - User registration and login system
  - Custom user profiles with profile pictures
  - Password change functionality
  - Profile editing capabilities

- **Book Catalog**
  - Browse books by category, author, or search
  - Advanced search functionality (by title, author, category, or description)
  - Filter books by price range and category
  - Sort books by price, title, or publication date
  - Detailed book pages with descriptions, images, and metadata
  - View similar books based on categories

- **Shopping Cart**
  - Add books to cart with quantity selection
  - Real-time cart updates via API
  - Stock availability checking
  - Cart item management
  - Checkout process

- **Personal Library**
  - View borrowed books
  - Track due dates and overdue books
  - Return books functionality
  - Manage book quantities
  - Library status tracking (Reading, Completed, Plan to Read, Owned)

### Admin Features
- **Book Management**
  - Add new books with cover images
  - Edit existing book information
  - Delete books
  - Manage book stock and availability
  - Category and author management

- **User Management**
  - Admin dashboard
  - User profile management
  - Library oversight

## 🛠️ Tech Stack

- **Backend Framework**: Django 5.0.1
- **API Framework**: Django REST Framework 3.14.0
- **Authentication**: Django REST Framework Simple JWT 5.3.0
- **CORS**: django-cors-headers 4.3.1
- **Database**: SQLite (development)
- **Frontend**: HTML, CSS, JavaScript, Bootstrap
- **Python Version**: Python 3.12+

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Python 3.12 or higher
- pip (Python package installer)
- Git

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/Online-Library-Website.git
   cd Online-Library-Website
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment**
   
   On Windows:
   ```bash
   venv\Scripts\activate
   ```
   
   On macOS/Linux:
   ```bash
   source venv/bin/activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Run migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Create a superuser (admin account)**
   ```bash
   python manage.py createsuperuser
   ```

7. **Collect static files**
   ```bash
   python manage.py collectstatic
   ```

8. **Run the development server**
   ```bash
   python manage.py runserver
   ```

9. **Access the application**
   - Open your browser and navigate to `http://127.0.0.1:8000/`
   - Admin panel: `http://127.0.0.1:8000/admin/`

## 📁 Project Structure

```
Online-Library-Website/
│
├── books/                    # Main books app
│   ├── models.py            # Book, Category, Author models
│   ├── views.py             # Book views and API endpoints
│   ├── urls.py              # Book URL routing
│   ├── forms.py             # Book forms
│   ├── admin.py             # Admin configuration
│   └── templates/           # Book templates
│
├── users/                    # User management app
│   ├── models.py            # Custom User and UserProfile models
│   ├── views.py             # Authentication and profile views
│   ├── urls.py              # User URL routing
│   ├── forms.py             # User forms
│   └── templates/           # User templates
│
├── library/                  # Library management app
│   ├── models.py            # LibraryBook and BorrowedBook models
│   ├── views.py             # Library views
│   ├── urls.py              # Library URL routing
│   └── templates/           # Library templates
│
├── cart/                     # Shopping cart app
│   ├── models.py            # Cart and CartItem models
│   ├── views.py             # Cart views
│   ├── urls.py              # Cart URL routing
│   └── templates/           # Cart templates
│
├── EgyBooksBackend/          # Main project configuration
│   ├── settings.py          # Django settings
│   ├── urls.py              # Main URL configuration
│   └── wsgi.py              # WSGI configuration
│
├── media/                    # User-uploaded files
│   └── profile_pictures/    # User profile pictures
│
├── static/                   # Static files (CSS, JS, images)
│
├── db.sqlite3               # SQLite database (development)
├── manage.py                # Django management script
└── requirements.txt         # Python dependencies
```

## 🎯 Key Models

### Book Model
- Title, author, category
- Description, cover image, ISBN
- Price, stock, availability status
- Publication date, pages, language

### User Model
- Custom user model with email authentication
- Extended profile with phone, address, profile picture

### Library Models
- **LibraryBook**: Books in user's personal library with status tracking
- **BorrowedBook**: Books currently borrowed with due dates

### Cart Models
- **Cart**: User's shopping cart
- **CartItem**: Individual items in the cart with quantities

## 🔑 API Endpoints

- `GET /api/book/<book_id>/` - Get book details in JSON format
- `POST /api/cart/add_item/` - Add book to cart

## 🎨 Features in Detail

### Search Functionality
- Search by title, author, category, or description
- Combine search with filters (category, price range)
- Sort results by relevance, price, or date

### Shopping Cart
- Real-time stock validation
- Quantity management
- Automatic tax calculation (10%)
- Persistent cart per user

### Library Management
- Track borrowed books with due dates
- Overdue book detection
- Return functionality
- Book status management

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 👥 Authors

- Your Name - [GitHub Profile](https://github.com/yourusername)

## 🙏 Acknowledgments

- Django community for the excellent framework
- Bootstrap for the UI components
- All contributors who have helped improve this project

## 📞 Support

If you have any questions or need help, please open an issue on GitHub or contact the project maintainers.

---

**Note**: This is a development version. For production deployment, consider:
- Using a production database (PostgreSQL recommended)
- Setting up proper static file serving
- Configuring environment variables for sensitive settings
- Setting up HTTPS
- Implementing proper error logging and monitoring
