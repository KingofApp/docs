# 📲 Configuración del sistema de notificaciones push con KoaPush Notifications

## 🧰 Requisitos Previos

Antes de comenzar, asegúrate de contar con los siguientes elementos:

* Un sitio WordPress funcional con usuarios registrados.
* Una aplicación desarrollada con **King of App**.
  
En King of app:
* El servicio **KoaPush Notifications** activo y configurado.
* El servicio **WP Koa Push Notifications** instalado en tu app.
  
En wordpress:
* Koa Suite instalado en el wordpress.

---

## 🔗 Asociar el dispositivo al usuario

Para enviar notificaciones a usuarios específicos, es necesario **asociar el código de dispositivo** proporcionado por el servicio KoaPush con el usuario correspondiente.

### 🔄 ¿Cómo se realiza la asociación?

Si los usuarios de tu app son los mismos de WordPress (y el login está embebido en la app), puedes usar el plugin **WP Koa Push Notifications**.

Al agregar el servicio **Koa Push Notifications** en el constructor de servicios de **King of App**, la app intentará contactar con WordPress.

> ✅ Si el usuario está logueado en la app, el sistema asociará automáticamente el **código de dispositivo al usuario**, lo que permitirá enviarle notificaciones desde WordPress.

---

## 🔧 Configurar las notificaciones en WordPress

### 1. Accede al menú de configuración

En el panel de administración de WordPress:

* Ve a **Koa Suite**
* Haz clic en **Push Notifications** en el menú superior.

Ahí verás una **lista de usuarios** y un botón para enviar notificaciones si tienen un dispositivo asociado.

---

### 2. Configura los permisos de Firebase

En la pestaña **Settings** del plugin:

* **Sube el archivo JSON** de cuenta de servicio de Firebase.

---

## 🔐 Obtener las credenciales de Firebase

### 1. Ingresa a Firebase Console

* Abre: [https://console.firebase.google.com](https://console.firebase.google.com)
* Selecciona tu proyecto o crea uno nuevo.

---

### 2. Obtener el ID del proyecto

* Haz clic en el ícono de engranaje junto a “Project Overview”.
* Selecciona **Configuración del proyecto**.
* En la pestaña **General**, copia el **ID del proyecto**.

---

### 3. Crear y descargar la cuenta de servicio

* Ve a **Cuentas de servicio**.
* Ignora el código mostrado.
* Haz clic en el botón azul para **crear la cuenta de servicio**.
* Se descargará un archivo `.json`.

> 💾 Este archivo es el que debes subir en la configuración del plugin en WordPress.

---

## 🚀 Enviar notificaciones a usuarios específicos

Una vez configurado todo, podrás enviar notificaciones desde el panel de WordPress.

---

### ✉️ Enviar notificaciones vía REST API

El plugin también habilita un **endpoint REST** para integraciones personalizadas.

#### Ejemplo con `curl`:

```bash
curl --location 'https://tudominio.com/?rest_route=%2Ffirebase%2Fv1%2Fsend-notification%2F' \
--header 'Content-Type: application/json' \
--header 'Authorization: ••••••' \
--data '{
  "device_token":"eNyb6nJbTsSxXuPpsQZONn:APA91bHN6zMEJ0I1SJRqIobbNAvAVceTWs937Uv3UNL_VKdK5Mqt0_pPlLKVPxhJIfcbNyYRKFykLJycLFeXijQfnA_cehqA1SOK9dI_glED3K4OlvXc0AI",
  "user_id": "1",
  "title": "Título de la notificación",
  "body": "Tu mensaje aquí"
}'
```
