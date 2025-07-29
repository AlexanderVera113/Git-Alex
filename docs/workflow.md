
---

📄 **`docs/workflow.md`**

# 🧪 Git Workflow

Este documento define el flujo de trabajo estándar basado en tres ramas principales: `development`, `test` y `production`, indicando además qué rol de usuario debe ejecutar cada acción.

---

## 📌 Estructura de ramas

* **`development`**: rama base para integración de nuevas funcionalidades.
* **`test`**: rama para pruebas manuales o automáticas (QA).
* **`production`**: rama estable para despliegue en producción.

---

## 🔁 Flujo de trabajo general

```
development (pull) → feature/* → PR (Write) → test → PR (Write) → development → PR (Admin) → production
```

**Roles:**

* **Write**: Desarrolladores con permisos para crear branches, pushes y Pull Requests.
* **Admin**: Responsable de validar y fusionar cambios críticos (merge a `production`).

---

## 🚧 Flujo de desarrollo

```bash
# Rol: Write
git checkout development
git pull origin development
git checkout -b feature/nueva-funcionalidad
```

* **Write**: Subes cambios con `git push origin feature/nueva-funcionalidad`.
* **Write**: Creas un **PR hacia `test`** para QA.
* **Write**: Si todo está OK, mergeas a `development` mediante PR.
* **Admin**: Para el release, se hace PR de `development` a `production`.

---

## 🛡️ Buenas prácticas

* Usar prefijos en ramas: `feature/`, `bugfix/`, `hotfix/`.
* Hacer commits descriptivos y consistentes.
* Configurar ramas protegidas:

  * `production` debe requerir **aprobación de Admin**.
  * `development` debe requerir Pull Requests con al menos una revisión.
  * `test` se puede gestionar por usuarios con permisos **Write**.

---

## 📌 Ejemplo de nombres de ramas

* `feature/login-form`
* `bugfix/fix-navbar`
* `hotfix/crash-on-load`

---

