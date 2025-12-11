# 🐍 Portfolio Backend - Django (Blog & Casos de Estudio)

<div align="center">

![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-5.2-092E20?style=for-the-badge&logo=django&logoColor=white)
![DRF](https://img.shields.io/badge/DRF-3.16-red?style=for-the-badge&logo=django&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-17-316192?style=for-the-badge&logo=postgresql&logoColor=white)

**API REST para blog técnico y casos de estudio**

[📖 API Docs](#endpoints) • [📝 Admin Panel](#admin-panel) • [🚀 Deploy](#deploy)

</div>

---

## 📖 **Descripción**

Backend **Django** que actúa como "narrador" del portfolio. Maneja:
- 📝 **Blog técnico** con posts en Markdown
- 📊 **Casos de estudio** detallados (challenge → solution → impact)
- 🏷️ **Sistema de tags** para categorización
- 👨‍💼 **Admin panel** para gestión de contenido
- 🔍 **Búsqueda full-text** (opcional con PostgreSQL)

---

## 🏗️ **Arquitectura**

```
portfolio-backend-django/
├── config/                      # Settings del proyecto
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── blog/                        # App principal
│   ├── models/
│   │   ├── __init__.py
│   │   ├── post.py              # Modelo Post
│   │   ├── tag.py               # Modelo Tag
│   │   └── case_study.py        # Modelo CaseStudy
│   ├── serializers/
│   │   ├── post_serializer.py
│   │   └── case_study_serializer.py
│   ├── views/
│   │   ├── post_viewset.py
│   │   └── case_study_viewset.py
│   ├── admin.py                 # Admin panel config
│   ├── urls.py
│   └── apps.py
├── api/                         # URLs y routing
│   ├── urls.py
│   └── routers.py
├── requirements.txt
├── Dockerfile
├── manage.py
└── README.md
```

---

## 🚀 **Quick Start**

### **Pre-requisitos**
```bash
Python 3.12+
PostgreSQL 17+ (o SQLite para dev)
Poetry
Docker
```

### **Instalación Local**

```bash
# Clonar el repo
git clone https://github.com/enlabedev/portfolio-backend-django.git
cd portfolio-backend-django

# Crear virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Instalar dependencias
poetry install

# Copiar .env
cp .env.example .env
nano .env  # Editar configuración

# Ejecutar migraciones
python manage.py migrate

# Crear superusuario
python manage.py createsuperuser

# Cargar datos de ejemplo
python manage.py loaddata initial_data.json

# Ejecutar servidor
python manage.py runserver 8082
```

### **URLs de Desarrollo**
- 🌐 **API**: http://localhost:8082/api/
- 👨‍💼 **Admin Panel**: http://localhost:8082/admin/
- 📖 **API Browser**: http://localhost:8082/api/blog/

---

## 🔌 **Endpoints API**

### **Base URL**
```
http://localhost:8082/api
```

---

### **📊 Health Check**

```http
GET /health/
```

**Response:**
```json
{
  "status": "healthy",
  "version": "1.0.0",
  "database": "connected",
  "total_posts": 12,
  "published_posts": 8
}
```

---


## 👨‍💼 **Admin Panel**

### **Acceso**
```
http://localhost:8082/admin/
```

### **Features del Admin**

✅ **Posts Management**
- Editor WYSIWYG para contenido Markdown
- Preview antes de publicar
- Programar publicación (scheduled posts)
- Gestión de tags
- View count tracking

✅ **Case Studies Management**
- CRUD completo
- Upload de imágenes
- JSON fields para metrics y tech_stack

---

## 🧪 **Testing**

### **Ejecutar Tests**

```bash
# Todos los tests
python manage.py test

# Con coverage
coverage run --source='.' manage.py test
coverage report

# Tests específicos
python manage.py test blog.tests.test_post

# Con output verbose
python manage.py test --verbosity=2
```

---

## 📚 **Recursos**

- [📖 Django Docs](https://docs.djangoproject.com)
- [🔌 Django REST Framework](https://www.django-rest-framework.org)
- [☁️ Deploy Django on Cloud Run](https://cloud.google.com/python/django/run)

---

## 🤝 **Contribuciones**

Ver guía en el [repo principal](https://github.com/enlabedev/portfolio-infra).

---

## 👨‍💻 **Autor**

**Enrique Lazo Bello** - Senior Software Engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/enlabe)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/enlabedev)

---

## 📄 **Licencia**

MIT License

---

<div align="center">

Made with 🐍 Django and ❤️

</div>
