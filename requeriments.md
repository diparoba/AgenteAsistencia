# Documento de Especificación de Requerimientos - MilApp

## 1. Descripción del Proyecto
**MilApp** es una plataforma integral diseñada para la gestión de servicios y disponibilidad. El sistema permite la interacción fluida entre prestadores y clientes a través de una interfaz multiplataforma, garantizando la puntualidad mediante un sistema de notificaciones inteligente.

---

## 2. Stack Tecnológico Sugerido
Para maximizar la eficiencia y cumplir con el despliegue en **Web, Android e iOS** con un solo equipo de desarrollo, sugiero:

* **Frontend (Framework):** **Flutter**. 
    * *Razón:* Permite crear aplicaciones nativas para móvil y versiones web altamente optimizadas con un único código fuente (Single Codebase).
* **Backend:** **Node.js con NestJS**.
    * *Razón:* NestJS utiliza TypeScript, lo que ayuda a evitar errores y es extremadamente eficiente para manejar múltiples conexiones simultáneas de usuarios.
* **Base de Datos:** **PostgreSQL**.
    * *Razón:* Es ideal para manejar relaciones complejas entre roles, horarios y disponibilidad.
* **Infraestructura de Notificaciones:** **Firebase Cloud Messaging (FCM)**.
    * *Razón:* Es el estándar de la industria para enviar alertas en tiempo real a dispositivos móviles y navegadores web.

---

## 3. Módulos del Sistema

### Módulo 1: Gestión de Acceso (Login)
* **RF1.1:** Registro de usuarios con validación de correo electrónico.
* **RF1.2:** Autenticación segura mediante JWT (JSON Web Tokens).
* **RF1.3:** Recuperación de contraseña mediante tokens temporales enviados por email.

### Módulo 2: Roles y Disponibilidad
* **RF2.1:** **Rol Cliente:** Capacidad para visualizar calendarios de disponibilidad, reservar espacios y cancelar servicios.
* **RF2.2:** **Rol Administrador/Agente:** Gestión de horarios de atención, bloqueo de fechas especiales y visualización de agenda diaria.
* **RF2.3:** Sincronización en tiempo real: Si un cliente reserva, el espacio debe marcarse como "No disponible" para los demás instantáneamente.

### Módulo 3: Notificaciones de Recordatorio
* **RF3.1:** Notificaciones Push al celular 24 horas y 1 hora antes del servicio.
* **RF3.2:** Confirmación de reserva enviada automáticamente por correo electrónico.
* **RF3.3:** Historial de notificaciones dentro de la app para que el usuario no pierda detalles.

---

## 4. Requerimientos No Funcionales
* **RNF1 (Arquitectura):** El sistema debe ser escalable para soportar un incremento en la cantidad de usuarios concurrentes.
* **RNF2 (Seguridad):** Encriptación de contraseñas mediante algoritmos de hash (como Bcrypt).
* **RNF3 (UX/UI):** La interfaz debe ser intuitiva y adaptarse automáticamente al tamaño de pantalla (Responsive Design).