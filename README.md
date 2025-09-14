
📌 Todo Application (Laravel + Vue.js + MySQL)

A full-stack Todo Application built with:

* Laravel 10 (API backend with Sanctum authentication)
* Vue 3 + Vite (frontend SPA)
* MySQL (database)

This project is structured into two main folders:

* `backend/` → Laravel API
* `frontend/` → Vue.js SPA

---

 🚀 Features

* User Authentication (Register/Login via Laravel Sanctum)
* Todo CRUD (Create, Read, Update, Delete)
* Status management (`pending`, `in-progress`, `completed`)
* Due date support
* Each user sees **only their own todos**
* Clean architecture using **Single Action Classes**
* RESTful API + Vue Router frontend

---
 ⚙️ Tech Stack

* PHP 8.1 + Laravel 10
* MySQL 8
* Node.js 18 + Vue 3 + Vite
* Docker (optional, for easy setup)



 🛠️ Getting Started

1️⃣ Clone the repository

```bash
git clone https://github.com/<your-username>/todo-app.git
cd todo-app
```



 2️⃣ Backend Setup (Laravel)

```bash
cd backend
composer install
cp .env.example .env
php artisan key:generate
```

Update `.env` database credentials:

```env
DB_DATABASE=todo_app
DB_USERNAME=root
DB_PASSWORD=root
```

Run migrations:

```bash
php artisan migrate
```

Start server:

```bash
php artisan serve --port=8000
```

API will run at:
👉 `http://127.0.0.1:8000/api`

---

 3️⃣ Frontend Setup (Vue)

Open new terminal:

```bash
cd frontend
npm install
npm run dev
```

App runs at:
👉 `http://127.0.0.1:5173`

---

4️⃣ Docker Setup (Optional)

If you have Docker installed:

```bash
docker-compose up -d --build
```

Services:

* Backend → `http://localhost:8000`
* Frontend → `http://localhost:5173`
* Database → `localhost:3306`

Run migrations inside container:

```bash
docker-compose exec backend php artisan migrate --force
```

---

 🧪 Testing

Backend tests:

```bash
cd backend
php artisan test
```

Frontend tests (if enabled):

```bash
cd frontend
npm run test


 📂 Project Structure


todo-app/
│── backend/        # Laravel API
│── frontend/       # Vue.js SPA
│── docker-compose.yml
│── README.md



 🤝 Contributing

1. Fork the repo
2. Create a new branch (`feature/xyz`)
3. Commit changes (`git commit -m "Added xyz"`)
4. Push branch (`git push origin feature/xyz`)
5. Open a Pull Request


 📜 License

This project is open-source and available under the MIT License.
