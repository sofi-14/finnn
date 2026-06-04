# 🐾 Huellitas

**Huellitas** es un sistema de gestión integral diseñado para optimizar los procesos operativos, médicos y legales de un refugio de rescate y adopción animal.

El objetivo principal del proyecto es mejorar la administración de registros, documentos y procesos internos del refugio, ya que antes de la implementación digital existían diversos problemas relacionados con el manejo de documentos en papel, pérdida de información, desorganización y dificultad para dar seguimiento a los animales rescatados.

Por ello, se desarrolló una **base de datos** y una **página web** que permiten al refugio tener un mayor alcance, tanto para encontrar adoptantes como para recibir apoyo de personas interesadas en realizar donaciones económicas, de alimento o de productos de limpieza.

---

## Objetivo del proyecto

El propósito de Huellitas es digitalizar y optimizar la gestión de un refugio animal mediante una plataforma que permita:

- Administrar información de animales rescatados.
- Registrar procesos médicos, legales y de adopción.
- Facilitar la búsqueda de adoptantes.
- Organizar donaciones económicas y en especie.
- Reducir el uso de documentos físicos.
- Mejorar la seguridad, disponibilidad y consulta de la información.

---

## Desarrollo del proyecto por prácticas

Durante el desarrollo del proyecto se trabajó con diferentes prácticas de la materia, las cuales permitieron construir progresivamente la lógica, estructura y funcionamiento del sistema.

### Práctica 1: Modelo Entidad-Relación

En esta práctica nació la idea inicial del proyecto. Antes de llevarlo a código, se analizaron las problemáticas del refugio y se propuso una solución mediante la creación de un **Modelo Entidad-Relación (MER)**.

Este modelo permitió identificar las entidades principales, sus atributos y las relaciones necesarias para representar correctamente los procesos del refugio.

---

### Práctica 2: Modelo Entidad-Relación Extendido

A partir del MER inicial, se identificaron algunas limitaciones en el diseño. Por ello, se desarrolló un **Modelo Entidad-Relación Extendido (MER Extendido)**.

Gracias a esta práctica fue posible representar de forma más clara jerarquías, especializaciones y generalizaciones, permitiendo tener una idea más completa de lo que se quería ofrecer al cliente.

---

### Práctica 3: Modelo Relacional

En esta práctica se transformó el MER Extendido en un **Modelo Relacional**.

Se aplicaron reglas de transformación, propagación de llaves, jerarquías y restricciones para convertir el diseño conceptual en una estructura lógica de tablas. Esto fue de gran ayuda para preparar el proyecto antes de implementarlo en código.

---

### Práctica 3.1: Arquitectura en la nube

En esta práctica se trabajó con alojamiento web y servicios en la nube.

El reto principal fue crear una arquitectura híbrida, conectando un frontend estático en **GitHub Pages** con un backend dinámico en **Render** y una base de datos serverless en **Supabase**.

Esto permitió comprender cómo interactúan los sistemas en producción y cómo proteger credenciales mediante variables de entorno.

---

### Práctica 4: Creación física de la base de datos

En esta práctica se creó físicamente la base de datos utilizando **PostgreSQL**.

Se aplicaron sentencias **DDL** para estructurar las tablas con restricciones reales de dominio, como:

- `NOT NULL` para campos obligatorios.
- `UNIQUE` para evitar datos repetidos, como correos o INE.
- `CHECK` para validar datos específicos.

Además, mediante sentencias **DCL**, se implementó un esquema de seguridad basado en roles y permisos, permitiendo que cada usuario del refugio tenga acceso únicamente a las funciones correspondientes a su puesto.

---

### Práctica 5: Transaccionalidad y manipulación de datos

En esta práctica se trabajó con sentencias **DML** y se analizó cómo podía reaccionar el sistema ante diferentes cargas de información.

Se desarrollaron scripts para poblar la base de datos en distintos niveles:

- Carga ligera para pruebas iniciales.
- Carga media para validación del comportamiento.
- Carga masiva con millones de registros para simular escenarios de producción.

Esto permitió evaluar la estabilidad y eficiencia de la base de datos.

---

### Práctica 6: Normalización

En esta práctica se trabajó con conjuntos de datos reales y desordenados obtenidos de Kaggle, con el objetivo de llevarlos hasta la **Tercera Forma Normal (3FN)**.

Esta práctica ayudó a identificar dependencias parciales y transitivas, asegurando que el diseño del proyecto fuera más óptimo, eficiente y libre de redundancias o anomalías al insertar, actualizar o eliminar información.

---

### Práctica 7: Álgebra Relacional básica

En esta práctica se estudió la fundamentación matemática de las bases de datos mediante el **Álgebra Relacional**.

Se trabajó con operadores básicos como:

- Selección.
- Proyección.
- Unión.
- Intersección.
- Diferencia.

Esto permitió comprender cómo se construyen las consultas desde una perspectiva matemática.

---

### Práctica 8: Álgebra Relacional avanzada

En esta práctica se trabajó con operadores avanzados del álgebra relacional, como:

- Reuniones o `JOIN`.
- Funciones de agregación como `COUNT`, `SUM` y `AVG`.
- Agrupaciones.

Estos conceptos influyeron directamente en la capacidad del sistema para generar reportes y estadísticas de manera eficiente.

---

### Práctica 9: Cálculo Relacional

Esta práctica representó la culminación teórica de la materia.

A diferencia del álgebra relacional, el **Cálculo Relacional** permitió formular consultas de manera declarativa utilizando lógica de primer orden, cuantificadores existenciales y universales.

Gracias a esto, se pudo demostrar la completitud relacional del sistema, asegurando que la estructura de las tablas es robusta y capaz de resolver consultas lógicas de forma segura y finita.

---

## Tecnologías utilizadas

- PostgreSQL
- Supabase
- Render
- GitHub Pages
- HTML
- CSS
- JavaScript
- SQL

---

## 🖼️ Evidencias del proyecto

<details>
<summary>Modelo Entidad-Relación</summary>

<br>

![Modelo Entidad-Relación](url imagen)

</details>

<details>
<summary>Modelo Entidad-Relación Extendido</summary>

<br>

![Modelo Entidad-Relación Extendido](url imagen)

</details>

<details>
<summary>Modelo Relacional</summary>

<br>

![Modelo Relacional](url imagen)

</details>

<details>
<summary>Base de Datos</summary>

<br>

![Base de Datos](url imagen)

</details>

<details>
<summary>Página Web</summary>

<br>

![Página Web](url imagen)

</details>

<details>
<summary>Capturas del sistema</summary>

<br>

![Captura 1](url imagen)

![Captura 2](url imagen)

![Captura 3](url imagen)

</details>

---

## Conclusión

El proyecto **Huellitas** permitió aplicar de manera práctica los temas vistos durante la materia de bases de datos, desde el diseño conceptual hasta la implementación física y despliegue en la nube.

A través de cada práctica se fortaleció el desarrollo del sistema, logrando una solución más organizada, segura y funcional para apoyar la gestión de un refugio animal.
