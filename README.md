# Simple LMS Backend - Minggu 2

Simple Learning Management System (LMS) Backend menggunakan Python built-in `http.server`.

## Struktur Project

```
minggu-2/
├── server.py
├── modules/
│   ├── __init__.py
│   ├── courses.py
│   ├── students.py
│   └── assignments.py
├── .venv/
├── .gitignore
└── README.md
```

## Deskripsi Modul

### `server.py`
Entry point aplikasi. HTTP Server sederhana yang berjalan di `localhost:8000` dengan endpoint:
- `GET /` - Info server
- `GET /health` - Health check
- `GET /courses` - Daftar mata kuliah
- `GET /students` - Daftar mahasiswa
- `GET /assignments` - Daftar tugas

### `modules/courses.py`
Mengelola data mata kuliah:
- `get_courses()` - Mengembalikan list course

### `modules/students.py`
Mengelola data mahasiswa:
- `get_students()` - Mengembalikan list student

### `modules/assignments.py`
Mengelola data tugas:
- `get_assignments()` - Mengembalikan list assignment

## Cara Menjalankan

```bash
# Aktifkan virtual environment
.venv\Scripts\activate

# Jalankan server
python server.py
```

Server akan berjalan di `http://localhost:8000`

## Contoh Response

**GET /courses**
```json
{
  "courses": [
    {"id": 1, "name": "Pemrograman Sisi Server"},
    {"id": 2, "name": "Basis Data"}
  ]
}
```

**GET /students**
```json
{
  "students": [
    {"id": 1, "name": "Andi"},
    {"id": 2, "name": "Siti"}
  ]
}
```

**GET /assignments**
```json
{
  "assignments": [
    {"id": 1, "title": "Backend Fundamentals"}
  ]
}
```