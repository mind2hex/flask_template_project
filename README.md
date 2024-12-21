# flask_template_project
Template for flask projects

```
project_name/
│
├── app/                        # Inicial directory of the app
│   ├── __init__.py             # App Factory
│   ├── routes.py               # route definitions (endpoints)
│   ├── models.py               # DB models definitions 
│   ├── forms.py                # Formulary definitions (Flask-WTF)
│   ├── templates/              # HTML templates (Jinja2)
│   │   └── base.html
│   ├── static/                 # (CSS, JS, imágenes)
│   │   ├── css/
│   │   ├── js/
│   │   └── images/
│   └── blueprints/             # (optional) Blueprints
│       ├── __init__.py
│       └── example/
│           ├── __init__.py
│           ├── routes.py
│           └── templates/
│               └── example/
│                   └── example.html
│
├── migrations/                 # Database file migrations (Flask-Migrate)
│
├── tests/                      # Unit tests
│   ├── __init__.py
│   └── test_routes.py
│
├── instance/                   # Environment configuration (excluded from repository)
│   └── config.py
│
├── requirements.txt            # Proyect dependencies
│
├── config.py                   # General configuration
│
├── run.py                      # Main file to run the app
│
└── README.md                   # Project documentation
```

### Detalle de los elementos principales

1. **`app/`**:
   - Contiene la lógica principal de la aplicación.
   - Usa el patrón **App Factory** en `__init__.py` para inicializar Flask y sus extensiones.

2. **`static/` y `templates/`**:
   - `static/` almacena archivos estáticos como CSS, JS e imágenes.
   - `templates/` contiene los archivos HTML renderizados con Jinja2.

3. **`config.py`**:
   - Define configuraciones para diferentes entornos (`DevelopmentConfig`, `ProductionConfig`, etc.).
   - Ejemplo:
     ```python
     class Config:
         SECRET_KEY = 'your_secret_key'
         SQLALCHEMY_DATABASE_URI = 'sqlite:///site.db'
         DEBUG = False

     class DevelopmentConfig(Config):
         DEBUG = True
     ```

4. **`migrations/`**:
   - Utilizado con `Flask-Migrate` para manejar las migraciones de la base de datos.

5. **`instance/`**:
   - Almacena configuraciones específicas del entorno, como claves o bases de datos locales.
   - Excluido del repositorio (`.gitignore`).

6. **`run.py`**:
   - El punto de entrada para correr la aplicación.
   - Ejemplo:
     ```python
     from app import create_app

     app = create_app()

     if __name__ == "__main__":
         app.run(debug=True)
     ```

7. **Pruebas (`tests/`)**:
   - Estructura organizada para pruebas unitarias y de integración.
   - Usa herramientas como `pytest` o `unittest`.

---

Esta estructura facilita la escalabilidad, modularidad y mantenibilidad, especialmente en proyectos grandes o con múltiples colaboradores.