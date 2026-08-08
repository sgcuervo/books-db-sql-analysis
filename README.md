# Análisis de Base de Datos Editorial — Propuesta de Valor para Plataforma de Lectura
El confinamiento por COVID-19 disparó el consumo de libros digitales y atrajo 
nuevas startups al mercado editorial. ¿Qué insights puede extraer una plataforma 
de lectura de su propia base de datos para construir una propuesta de valor 
competitiva?

### Herramientas y tipo de proyecto
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Análisis de Datos](https://img.shields.io/badge/AN%C3%81LISIS_DE_DATOS-blue?style=for-the-badge)
![Consultas SQL](https://img.shields.io/badge/CONSULTAS_SQL-blue?style=for-the-badge)

## Preguntas clave:
1. ¿Cuántos libros contemporáneos (post-2000) tiene el catálogo?
2. ¿Qué libros generan mayor engagement — combinando calificaciones y reseñas?
3. ¿Qué editorial tiene mayor presencia en el catálogo?
4. ¿Qué autores tienen las mejores calificaciones con volumen suficiente?
5. ¿Qué tan activos son los usuarios más comprometidos de la plataforma?

## Metodología
Se exploraron cinco tablas relacionales mediante consultas SQL: libros, autores, 
editoriales, calificaciones y reseñas. Para el análisis de autores se filtraron 
únicamente títulos con al menos 50 calificaciones, evitando sesgos por volumen 
insuficiente. Para la editorial líder se excluyeron publicaciones menores a 50 
páginas para eliminar folletos del análisis.

## Insights clave:

1. **819 libros publicados después del año 2000.** El catálogo garantiza una 
oferta de contenido contemporáneo relevante para usuarios actuales.

2. **993 libros con calificaciones y reseñas calculadas.** La combinación de 
participación activa (reseñas escritas) y valoración general (calificación 
promedio) permite identificar qué títulos generan mayor engagement real.

3. **Penguin Books lidera el catálogo con 42 títulos de más de 50 páginas.** 
Las editoriales con mayor volumen representan alianzas estratégicas prioritarias 
para ampliar la oferta de contenido.

4. **J.K. Rowling y Mary GrandPré tienen la calificación promedio más alta 
(4.29)** entre autores con volumen suficiente de calificaciones, posicionándolas 
como referentes de calidad para la plataforma.

5. **Los usuarios más activos generan en promedio 24.3 reseñas de texto.** 
El segmento de usuarios con más de 50 calificaciones produce contenido orgánico 
que influye en decisiones de otros lectores — un activo de alto valor para la 
plataforma.

## Recomendaciones estratégicas:
1. **Priorizar alianza con Penguin Books** como socio editorial estratégico 
dado su volumen de catálogo.
2. **Destacar autores de alta calificación** como J.K. Rowling en la propuesta 
de valor de la plataforma para atraer nuevos usuarios.
3. **Implementar programa de fidelización para usuarios activos** — recompensas 
o acceso anticipado a nuevos títulos para el segmento de más de 50 calificaciones, 
que ya genera contenido orgánico de valor.
4. **Usar el ratio reseñas/calificación como métrica de engagement** para 
identificar títulos con alta participación activa vs pasiva.

## Diccionario de datos

**Tabla `books` — información de libros:**
- `book_id` — identificador del libro
- `author_id` — identificador del autor
- `title` — título del libro
- `num_pages` — número de páginas
- `publication_date` — fecha de publicación
- `publisher_id` — identificador de la editorial

**Tabla `authors` — información de autores:**
- `author_id` — identificador del autor
- `author` — nombre del autor

**Tabla `publishers` — información de editoriales:**
- `publisher_id` — identificador de la editorial
- `publisher` — nombre de la editorial

**Tabla `ratings` — calificaciones de usuarios:**
- `rating_id` — identificador de la calificación
- `book_id` — identificador del libro calificado
- `username` — nombre del usuario
- `rating` — calificación numérica otorgada

**Tabla `reviews` — reseñas de usuarios:**
- `review_id` — identificador de la reseña
- `book_id` — identificador del libro reseñado
- `username` — nombre del usuario
- `text` — texto de la reseña

## Cómo reproducir el análisis

```bash
git clone https://github.com/sgcuervo/books-db-sql-analysis

cd books-db-sql-analysis

pip install -r requirements.txt

jupyter notebook notebooks/analysis.ipynb
```
Los datasets originales están incluidos en `/datasets/`.
