# 🐶 PetLog: Historial Médico Automatizado para Mascotas
PetLog es una aplicación web Full-Stack diseñada para digitalizar y automatizar el registro de la salud de mascotas. Está enfocada en la gestión de vacunas, desparasitaciones y visitas veterinarias, generando recordatorios automáticos para los dueños.

Este proyecto fue desarrollado utilizando Laravel en el backend y el TALL Stack para el frontend, sirviendo como demostración de dominio de todas las características avanzadas del ecosistema.

## 🛠️ Stack Tecnológico
| Categorías | Herramienta |Versión | 
| --- | --- | ---|
| Lenguaje de programación | PHP | ^8.2 | 
| Framework Principal | Laravel | ^12.0 | 
| Frontend Dinámico | Laravel Livewire | |
| Componentes Livewire | Livewire Volt | ^1.7.0 |
| Autenticación | Laravel Fortify | ^1.30 |
| Testing | Pest | ^4.1 |
| Base de Datos | MySQL | | 
| Compilador | Vite | ^7.0.4 |
| Framework CSS | Tailwind CSS | ^4.0.7 |
| Post-Procesador CSS | Autoprefixer | ^10.4.20 |

## Instalación y Configuración
Sigue estos pasos para levantar el proyecto en tu entorno local:
### 1. Clonar el Repositorio
```zsh
git clone git@github.com:tu_usuario/PetLog.git
cd PetLog
```
### 2. Configurar Laravel
Instala las dependencias de Composer y Node:
```zsh
composer install
npm install
```
### 3. Archivo .env
Crea el archivo de configuración y genera la clave de aplicación:

```zsh
cp .env.example .env
php artisan key:generate
```
Asegúrate de configurar tu conexión a la base de datos en el archivo .env.

### 4. Base de Datos y Seeders
Ejecuta las migraciones y los seeders para inicializar la base de datos:

```zsh
php artisan migrate --seed
```
### 5. Compilar Assets
Compila el CSS (Tailwind) y el JavaScript (Alpine/Livewire):

```zsh
npm run dev
# o usar 'npm run watch' para desarrollo en tiempo real
```
### 6. Ejecutar la Aplicación
```zsh
php artisan serve
```

##  Plan de Desarrollo (MVP)
El MVP (Producto Mínimo Viable) se estructura en tres fases clave para asegurar un producto funcional y robusto.

### FASE 1: Core (CRUD Básico y Autenticación)
El objetivo es tener la aplicación funcionando con los modelos y la seguridad básica.
| Tarea | Descripción | Tecnología Principal | Estado |
| --- | --- | --- | --- |
| A1. Autenticación | Configurar rutas de login/registro. | Laravel / Breeze | <span style="color=orange">Pendiente</span> |
| A2. Migraciones y Modelos | Crear migraciones y modelos para User, Pet, Visit, y Vaccination. Establecer relaciones Eloquent. | Eloquent ORM | <span style="color=orange">Pendiente</span> |
| A3. Dashboard Livewire | Crear el componente principal Livewire para listar las mascotas del usuario. | Livewire | <span style="color=orange">Pendiente</span> |
| A4. CRUD de Mascotas | Formulario Livewire para añadir/editar mascotas. Validaciones de formulario (Laravel). | Livewire / Blade| <span style="color=orange">Pendiente</span> |

### FASE 2: Historial Médico y Autorización
El foco es capturar la información crítica de salud y asegurar que solo el dueño pueda acceder a sus datos.
| Tarea | Descripción | Tecnología Principal | Estado |
| --- | --- | --- | --- |
| B1. Policies de Acceso | Implementar PetPolicy, VisitPolicy, y VaccinationPolicy para autorización estricta. | Laravel Policies| <span style="color=orange">Pendiente</span> |
| B2. CRUD de Vacunas | Componente Livewire para añadir, editar y listar vacunas específicas de una mascota. | Livewire / Blade| <span style="color=orange">Pendiente</span> |
| B3. CRUD de Visitas | Componente Livewire para registrar visitas y notas del veterinario. | Livewire / Blade| <span style="color=orange">Pendiente</span> |
| B4. Subida de Fotos | Permitir la subida de una foto de perfil para cada mascota. | Laravel Storage| <span style="color=orange">Pendiente</span> |

### FASE 3: Automatización y Calidad (Demostración Avanzada)
Esta fase es la que demuestra el conocimiento completo del ecosistema Laravel.
| Tarea | Descripción | Tecnología Principal | Estado |
| --- | --- | --- | --- |
| C1. Scheduler para Recordatorios | Crear un comando Artisan ejecutado por Scheduler (daily) para identificar citas próximas (7 días). | Laravel Scheduler
| C2. Jobs y Queues | Despachar un Job asíncrono que busca las mascotas con recordatorios y les envía notificaciones. | Laravel Queues
| C3. Notificaciones por Email | Implementar Notification con template de Blade para enviar el recordatorio al dueño. | Laravel Notificable
| C4. Pruebas Funcionales | Escribir pruebas con Pest para el CRUD de Mascotas y el flujo de recordatorios (Aserciones de Base de Datos y Email). | Pest 
## Contribución
Las contribuciones son bienvenidas. Si tienes sugerencias o quieres mejorar alguna característica, por favor:
1. Haz un fork del repositorio.
2. Crea una nueva rama (`git checkout -b feature/AmazingFeature`).
3. Comitéa tus cambios (`git commit -m 'Add some AmazingFeature'`).
4. Haz push a la rama (`git push origin feature/AmazingFeature`).
5. Abre un Pull Request.