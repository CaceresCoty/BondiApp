# 🚌 Proyecto Final: BondiApp (Sistema de Autenticación y Navegación)

Este proyecto es una aplicación nativa de Android desarrollada en Java. El objetivo principal es demostrar la **persistencia de datos local (SQLite)**, la autenticación de usuarios y la navegación secuencial a través de un flujo de Activities.

---

## 💾 1. Módulo de Persistencia y Autenticación (SQLite)

La aplicación utiliza la clase `DatabaseHelper.java` para gestionar una base de datos local SQLite (`UsuariosBondi.db`).

| Componente | Archivo | Acción Funcional |
| :--- | :--- | :--- |
| **REGISTRARSE** | `MainActivity.java` | Ejecuta `dbHelper.insertUser()`. **Guarda los datos** (`username` y `password`) en la tabla `usuarios` del DB local. |
| **INGRESAR** | `MainActivity.java` | Ejecuta `dbHelper.checkUser()`. **Verifica la autenticación** contra los registros guardados. |

**Integridad de la Base de Datos:**
* La tabla `usuarios` está configurada con `ID` (PK/AI) y `username` con la restricción `UNIQUE`.
* Se confirmó que la función de guardar es **completamente funcional** mediante la extracción y verificación del archivo `UsuariosBondi.db` con DB Browser for SQLite.

---

## 🗺️ 2. Flujo de Navegación del Usuario (3 Pantallas)

El sistema demuestra una navegación lógica y validada entre todas las Activities.

| Pantalla | Archivo/Clase | Funcionalidad |
| :--- | :--- | :--- |
| **Pantalla 1** | `MainActivity.java` | Punto de entrada y autenticación. En caso de éxito, navega a la Pantalla 2. |
| **Pantalla 2** | `Principal.java` | Muestra un saludo personalizado (ej: "Bienvenido, [Usuario]"). El botón **"TERMINAL QUARANTA"** inicia la navegación a la Pantalla 3. |
| **Pantalla 3** | `BusquedaLineaActivity.java` | Destino final del flujo de búsqueda. |

---

## 📸 3. Material de Entrega y Escalabilidad

Para la evaluación, se proporciona la siguiente evidencia:

* **Capturas de Pantalla (Caps):** Imágenes que muestran la interfaz de **Login/Registro** y **Selección de Terminal**.
* **Mención de Videos:** La estructura de la aplicación está diseñada para una **futura integración multimedia** (como búsqueda de rutas en video), lo que garantiza la escalabilidad del proyecto.
