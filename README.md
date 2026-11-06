💄 TechGear Beauty
TechGear Beauty es una tienda web de maquillaje y productos de belleza que permite a los usuarios explorar un catálogo de productos, consultar sus características, gestionar sus cuentas y realizar pedidos de manera sencilla.

El proyecto está desarrollado con una arquitectura basada en Django, FastAPI y MongoDB, separando la interfaz web de los servicios encargados de gestionar la información.

📌 Tabla de contenido
Descripción del proyecto
Características principales
Tecnologías utilizadas
Arquitectura del proyecto
Funcionalidades
Instalación y configuración
Ejecución del proyecto
Documentación de la API
Roles de usuario
Autor
📝 Descripción del proyecto
TechGear Beauty es una plataforma de comercio electrónico enfocada en la venta de maquillaje y productos de belleza.

Su objetivo es ofrecer una experiencia de compra intuitiva, permitiendo a los clientes consultar productos, conocer su disponibilidad, realizar pedidos y revisar su historial de compras.

Además, cuenta con un panel de administración que facilita la gestión del catálogo y una API REST que centraliza las operaciones relacionadas con productos, usuarios y pedidos.

✨ Características principales
🛍️ Catálogo de productos: visualización de productos con nombre, descripción, categoría, precio, existencias e imagen.
🔎 Filtros por categoría: permite encontrar productos según su clasificación.
📦 Control de inventario: identifica productos disponibles y agotados.
👤 Gestión de usuarios: registro e inicio de sesión.
🛒 Gestión de pedidos: permite agregar productos y cantidades a los pedidos.
💰 Cálculo de totales: calcula automáticamente el valor de cada pedido.
📋 Historial de compras: permite consultar los pedidos realizados.
⚙️ Panel de administración: permite crear, editar y eliminar productos.
🔄 Actualización de existencias: descuenta las unidades correspondientes al realizar pedidos.
🧰 Tecnologías utilizadas

Tecnología	Descripción
Python	Lenguaje principal del backend.
Django	Desarrollo de páginas web, vistas y navegación.
FastAPI	Desarrollo de servicios y API REST.
MongoDB	Base de datos NoSQL para almacenar la información.
HTML	Estructura de las páginas web.
CSS	Diseño y estilos de la interfaz.
JavaScript	Interactividad de la página web.
🏗️ Arquitectura del proyecto
El sistema utiliza una arquitectura dividida en tres componentes principales:

1. Django – Aplicación web
Se encarga de la interfaz gráfica y la interacción con los usuarios.

Responsabilidades:

Mostrar el catálogo de productos.
Gestionar el registro e inicio de sesión.
Permitir la navegación por la tienda.
Mostrar los pedidos de cada cliente.
Proporcionar el panel de administración.
2. FastAPI – Servicios REST
Se encarga de procesar las solicitudes y gestionar las operaciones del sistema.

Responsabilidades:

Consultar productos.
Registrar, actualizar y eliminar productos.
Gestionar usuarios.
Crear y consultar pedidos.
Actualizar estados de los pedidos.
Controlar las existencias.
3. MongoDB – Base de datos
Se utiliza para almacenar la información de la aplicación.

Colecciones principales:

productos: información del catálogo.
usuarios: información de las cuentas.
pedidos: artículos, cantidades, totales y estados de los pedidos.
⚙️ Funcionalidades
🛍️ Catálogo de productos
Cada producto contiene la siguiente información:

Nombre.
Descripción.
Categoría.
Precio.
Existencias.
Imagen.
Los clientes pueden consultar el catálogo, filtrar por categorías y verificar la disponibilidad de los productos.

👤 Cuentas de usuario
El sistema permite:

Registrar nuevas cuentas.
Iniciar sesión.
Asociar los pedidos a cada usuario.
Consultar el historial de compras mediante la opción Ver mis pedidos.
🛒 Gestión de pedidos
Los clientes pueden agregar productos a sus pedidos indicando las cantidades deseadas.

El sistema se encarga de:

Registrar los productos seleccionados.
Calcular el total del pedido.
Actualizar las existencias disponibles.
Asociar cada pedido con su respectivo cliente.
Gestionar el estado de los pedidos desde la API.
🔐 Panel de administración
Los usuarios con permisos de administrador pueden gestionar el catálogo de productos.

Funciones disponibles:

Agregar nuevos productos.
Editar información existente.
Eliminar productos.
Administrar precios y existencias.
🚀 Instalación y configuración
Requisitos previos
Antes de ejecutar el proyecto, asegúrate de tener instalado:

Python 3.10 o superior.
MongoDB.
Git.
pip (gestor de paquetes de Python).
1. Clonar el repositorio

bash
git clone URL_DEL_REPOSITORIO
Ingresar a la carpeta del proyecto:


bash
cd TechGear-Beauty
2. Crear un entorno virtual

bash
python -m venv venv
Activar el entorno virtual:

Windows:


bash
venv\Scripts\activate
Linux / macOS:


bash
source venv/bin/activate
3. Instalar las dependencias
Si el proyecto cuenta con un archivo requirements.txt, ejecutar:


bash
pip install -r requirements.txt
4. Configurar MongoDB
Verificar que MongoDB esté instalado y en funcionamiento.

Configurar la cadena de conexión en las variables de entorno o en el archivo de configuración correspondiente.

Ejemplo:


env
MONGODB_URI=mongodb://localhost:27017/
DATABASE_NAME=techgear_beauty
Nota: No subir credenciales, contraseñas ni archivos .env al repositorio.

▶️ Ejecución del proyecto
El proyecto utiliza dos servicios principales que deben ejecutarse de manera independiente.

Iniciar FastAPI
Desde la carpeta donde se encuentra la aplicación FastAPI:


bash
uvicorn main:app --reload
La API estará disponible en:


text
http://127.0.0.1:8000
Iniciar Django
Desde la carpeta donde se encuentra el proyecto Django:


bash
python manage.py runserver
La aplicación web estará disponible en:


text
http://127.0.0.1:8000
Importante: Si ambos servicios se ejecutan en el mismo equipo, deben utilizar puertos diferentes. Por ejemplo, FastAPI en el puerto 8000 y Django en el 8001.

📚 Documentación de la API
FastAPI proporciona documentación interactiva para consultar y probar los servicios disponibles.


Ruta	Descripción
/docs	Documentación interactiva con Swagger UI.
/health	Ruta para comprobar el estado del servicio.
Documentación Swagger:


text
http://127.0.0.1:8000/docs
Comprobación del servicio:


text
http://127.0.0.1:8000/health
👥 Roles de usuario
El sistema contempla dos tipos principales de usuarios:


Rol	Permisos
Cliente	Consultar productos, registrarse, iniciar sesión, realizar pedidos y consultar su historial.
Administrador	Gestionar el catálogo de productos y administrar la información correspondiente desde el panel de administración.
📁 Estructura general del proyecto
La estructura puede organizarse de la siguiente manera:


text
TechGear-Beauty/
│
├── django_app/
│   ├── templates/
│   ├── static/
│   ├── views.py
│   ├── urls.py
│   └── models.py
│
├── fastapi_app/
│   ├── main.py
│   ├── routes/
│   ├── services/
│   └── database/
│
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
Nota: Esta es una estructura de referencia que puedes adaptar a la organización real de tus carpetas y archivos.

🎯 Objetivo del proyecto
Desarrollar una plataforma web de comercio electrónico que integre tecnologías modernas de desarrollo backend, permitiendo gestionar productos, usuarios, inventario y pedidos mediante una arquitectura que separa la aplicación web de los servicios API y la base de datos.

👨‍💻 Autor
Desarrollador: [Isabella zambrano]

Proyecto: TechGear Beauty

Tecnologías principales: Python, Django, FastAPI y MongoDB.

⭐ Si este proyecto te resulta interesante, no olvides darle una estrella al repositorio.
