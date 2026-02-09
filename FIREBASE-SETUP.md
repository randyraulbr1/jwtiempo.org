# Configuración de Firebase para JW Tiempo

## Problema: Error al registrar anciano como administrador

Si el anciano no puede registrarse o acceder al panel de administración, es porque las **reglas de seguridad** de Firebase Realtime Database deben configurarse correctamente.

---

## Pasos para configurar las reglas de Firebase

### 1. Entrar a Firebase Console

1. Ve a **https://console.firebase.google.com**
2. Inicia sesión con tu cuenta de Google
3. Selecciona el proyecto **jwtiempoorg**

### 2. Configurar Realtime Database Rules

1. En el menú izquierdo, haz clic en **Realtime Database** (o **Base de datos en tiempo real**)
2. Haz clic en la pestaña **Rules** (Reglas)
3. **Borra** todo el contenido actual de las reglas
4. **Copia y pega** el siguiente contenido:

```json
{
  "rules": {
    "usuarios": {
      ".read": "auth != null && root.child('admins').child(auth.uid).val() == true",
      "$uid": {
        ".read": "auth != null && auth.uid == $uid",
        ".write": "auth != null && auth.uid == $uid"
      }
    },
    "reportes": {
      "$year": {
        "$month": {
          ".read": "auth != null && root.child('admins').child(auth.uid).val() == true",
          "$uid": {
            ".read": "auth != null && (auth.uid == $uid || root.child('admins').child(auth.uid).val() == true)",
            ".write": "auth != null && auth.uid == $uid"
          }
        }
      }
    },
    "admins": {
      "$uid": {
        ".read": "auth != null",
        ".write": "auth != null && auth.uid == $uid"
      }
    },
    "adminsInfo": {
      "$uid": {
        ".read": "auth != null",
        ".write": "auth != null && auth.uid == $uid"
      }
    }
  }
}
```

5. Haz clic en **Publicar** (o **Publish**)

---

## Después de publicar las reglas

1. Espera 1-2 minutos
2. Intenta registrar un anciano nuevamente en **admin-registro.html**
3. El registro debería completarse y redirigir a **admin.html**

---

## Si ya registraste un anciano pero dio error

Si el usuario se creó en Firebase Authentication pero no se guardó en `/admins/`, puedes añadirlo manualmente:

1. En Firebase Console → **Realtime Database** → pestaña **Data**
2. Haz clic en el ícono **+** junto a la raíz
3. Añade un nodo llamado **admins**
4. Dentro de **admins**, añade un hijo con el **UID del usuario** (puedes verlo en Authentication → Users) y valor **true**

---

## Ubicación en Firebase Console

```
Firebase Console
  └── Proyecto: jwtiempoorg
        └── Realtime Database
              └── Rules (Reglas)  ← Aquí pegas las reglas
```
