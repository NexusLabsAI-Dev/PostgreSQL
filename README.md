# SQL Trainer — Práctica Interactiva de SQL

Herramienta de estudio para aprender y practicar SQL desde nivel básico hasta avanzado, directamente en el navegador. Sin instalaciones, sin backend, sin registro.

---

## ¿Qué es?

Una aplicación web estática que incluye un motor SQL real (SQLite vía sql.js) corriendo en el navegador. Escribes queries, las ejecutas y el sistema valida automáticamente si tu resultado es correcto.

---

## Contenido

| Bloque | Tema | Ejercicios |
|--------|------|-----------|
| Bloque 0 | Comandos psql (`\l`, `\dt`, `\d`, `\du`...) | 5 |
| Bloque 2 | DDL — Tablas y Constraints | 5 |
| Bloque 5 | SELECT, WHERE, ORDER BY, LIKE, CASE | 5 |
| Bloque 6 | Funciones Agregadas (COUNT, SUM, AVG, GROUP BY, HAVING) | 5 |
| Bloque 7 | Funciones de Texto (UPPER, LOWER, SUBSTR, REPLACE, \|\|) | 5 |
| Bloque 8 | Funciones de Fecha (strftime, EXTRACT, AGE) | 4 |
| Bloque 9 | JOINs (INNER, LEFT, RIGHT, SELF, 3 tablas) | 5 |
| Bloque 10 | Subqueries (IN, NOT IN, EXISTS, correlacionadas) | 5 |
| Bloque 11 | DML — INSERT, UPDATE, DELETE | 5 |
| Bloque 12 | Transacciones (BEGIN, COMMIT, ROLLBACK, SAVEPOINT, ACID) | 5 |
| Bloque 14 | Vistas (CREATE VIEW, MATERIALIZED VIEW) | 4 |
| Bloque 15 | Usuarios y Permisos (GRANT, REVOKE, CREATE ROLE) | 5 |
| Bloque 17 | CTEs y WITH RECURSIVE | 4 |

**Total: 57 ejercicios**

---

## Características

- **Motor SQL real en el navegador** — powered by [sql.js](https://sql.js.org) (SQLite compilado a WebAssembly)
- **Validación automática** — compara tu resultado con el esperado fila por fila
- **Sistema de intentos** — hasta 5 intentos por ejercicio; las pistas aparecen progresivamente
- **Referencia rápida** — cada bloque incluye sintaxis y ejemplos de cada comando antes de los ejercicios
- **Progreso persistente** — guardado en localStorage, sobrevive al cerrar el navegador
- **100% estático** — un solo archivo HTML, funciona offline después de la primera carga

---

## Base de datos de práctica

La app incluye una base de datos de ejemplo con 4 tablas:

```
departamentos → empleados → asignaciones → proyectos
```

- 4 departamentos
- 10 empleados (con jerarquía jefe/subordinado para SELF JOIN)
- 4 proyectos
- 12 asignaciones

---

## Uso

### Opción 1 — Local

1. Descarga `index.html`
2. Doble clic para abrirlo en cualquier navegador (Chrome, Firefox, Edge)
3. Requiere conexión a internet para cargar sql.js desde CDN

### Opción 2 — GitHub Pages

Accede directamente desde el navegador sin descargar nada:

🔗 **[Ver en GitHub Pages](https://tuusuario.github.io/sql-trainer)**

---

## Diferencias SQLite vs PostgreSQL

La app corre SQLite en el navegador. La sintaxis es 95% compatible con PostgreSQL. Las diferencias principales se señalan con notas en cada ejercicio:

| Función | SQLite | PostgreSQL |
|---------|--------|-----------|
| Autoincremento | `INTEGER PRIMARY KEY` | `SERIAL PRIMARY KEY` |
| Fecha actual | `date('now')` | `CURRENT_DATE` |
| Extraer año | `strftime('%Y', fecha)` | `EXTRACT(YEAR FROM fecha)` |
| Diferencia de fechas | `julianday(f2) - julianday(f1)` | `f2 - f1` |
| Primeros N chars | `SUBSTR(col, 1, n)` | `LEFT(col, n)` |
| FULL OUTER JOIN | ❌ No soportado | ✅ Soportado |
| CREATE OR REPLACE VIEW | ❌ No soportado | ✅ Soportado |

---

## Stack técnico

- HTML5 / CSS3 / JavaScript vanilla
- [sql.js 1.10.2](https://github.com/sql-js/sql.js) — SQLite compilado a WebAssembly
- [JetBrains Mono](https://www.jetbrains.com/legalforms/mono/) — tipografía
- Sin frameworks, sin dependencias npm, sin build tools

---

## Cómo publicar en GitHub Pages

1. Crea un repositorio en GitHub
2. Sube `index.html` como archivo principal (o renómbralo a `index.html`)
3. Ve a **Settings → Pages**
4. En **Branch** selecciona `main` y carpeta `/root`
5. Haz clic en **Save**
6. En unos minutos tu URL será: `https://tuusuario.github.io/nombre-repo`

---

## Autor

**Fernando** — Tecnología · Soporte · Ciberseguridad  
Estudiante de certificaciones CompTIA Linux+, Security+ y Pentest+

---

*Proyecto de estudio personal — Nexus Labs AI*
