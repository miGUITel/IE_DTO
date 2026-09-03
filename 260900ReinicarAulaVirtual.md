# Procedimiento anual para reutilizar un curso Moodle

El objetivo es **reutilizar el mismo curso Moodle con una nueva promoción**, manteniendo en la plataforma los datos históricos del alumnado anterior y utilizando la función **Reiniciar** para realizar en una sola operación la desmatriculación de los estudiantes y el desplazamiento de las fechas al nuevo curso académico.

La copia de seguridad tiene una función secundaria porque, con nuestros permisos, **no puede incluir datos de usuario**; sirve para proteger la estructura y los materiales del curso, pero no las entregas, intentos o calificaciones del alumnado. 

# 1. Resumen de tareas

1. **Exportar las calificaciones.**
2. **Crear opcionalmente una copia de seguridad del curso.**
3. **Reiniciar el curso.**
   1. Comprobar la fecha de inicio del curso anterior.
   2. Desmarcar todas las opciones del formulario de reinicio.
   3. Seleccionar la nueva fecha de inicio.
   4. Dar de baja a los usuarios con rol **Estudiante**.
4. **Comprobar el resultado del reinicio.**
5. **Matricular al alumnado del nuevo curso.**
6. **Tener en cuenta los riesgos de la reutilización.**

---

# 2. Procedimiento detallado

## 1. Exportar las calificaciones

**Dónde:**
**Calificaciones → Exportar → Hoja de cálculo Excel** (o CSV).

Exportar todas las calificaciones antes de modificar el curso y guardar el archivo identificando módulo y curso académico, por ejemplo:

`ED_2025-26_calificaciones.xlsx`

**Por qué:** constituye una copia histórica sencilla y fácilmente consultable de las notas. Es especialmente importante porque nuestras copias de seguridad no pueden incluir datos de usuario. 

---

## 2. Crear opcionalmente una copia de seguridad

**Dónde:**
**Más → Reutilización del curso → Copia de seguridad**

Crear y descargar, si se considera conveniente, una copia `.mbz` con las actividades, recursos, archivos, banco de preguntas y estructura del curso.

Por ejemplo:

`ED_2025-26_estructura.mbz`

En nuestro Moodle aparece una cruz roja en **«Incluir usuarios matriculados»**, por lo que esta copia **no contiene las entregas, intentos ni otros datos del alumnado**. Su finalidad es poder recuperar la estructura y los materiales si posteriormente modificamos o borramos algo accidentalmente. 

---

# 3. Reiniciar el curso

**Dónde:**
**Más → Reutilización del curso → Reiniciar**

El reinicio realizará dos operaciones que nos interesan: **desmatricular la promoción anterior y desplazar las fechas del curso**. Moodle permite precisamente dar de baja de forma masiva a todos los usuarios que tengan un determinado rol. ([MoodleDocs][1])

## 3.1. Comprobar la fecha de inicio del curso anterior

Antes de entrar en Reiniciar:

**Configuración → General → Fecha de inicio del curso**

Comprobar que corresponde realmente al curso que acaba de terminar. Por ejemplo, para 2025-26 podría ser:

**1 de septiembre de 2025**

Si no es correcta, modificarla y guardar.

**Por qué:** Moodle calcula el desplazamiento de las actividades comparando la fecha de inicio anterior con la nueva. Si la fecha antigua es incorrecta, también lo será el desplazamiento. Moodle confirma que al especificar una nueva fecha de comienzo en el reinicio, las fechas del curso se desplazan en la misma cantidad. ([MoodleDocs][1])

---

## 3.2. Desmarcar todo al final del formulario

En:

**Más → Reutilización del curso → Reiniciar**

ir al final y utilizar **«No seleccionar ninguno»**.

Después comprobar que han quedado desmarcadas todas las opciones de borrado, especialmente:

* **Todas las entregas** de tareas.
* **Todos los intentos** de cuestionarios.
* **Todos los mensajes** de foros.
* Datos de finalización.
* Grupos y agrupamientos.
* Anotaciones, comentarios y demás datos de usuario.

**Por qué:** queremos desmatricular a los estudiantes, **no borrar su información histórica**. El reinicio de Moodle permite elegir individualmente qué datos se eliminan y advierte de que la eliminación de esos datos es irreversible. ([MoodleDocs][2])

---

## 3.3. Seleccionar la nueva fecha inicial del curso

En la sección **General** del formulario:

**Fecha de inicio del curso → Habilitar ✅**

Introducir la fecha que se considere adecuada como comienzo del nuevo curso académico.

En principio:

**Fecha de finalización → Habilitar ❌**

salvo que también interese modificarla.

**Por qué:** Moodle utilizará la diferencia entre la fecha anterior y esta nueva fecha para desplazar automáticamente las fechas de las actividades, evitando tener que modificarlas una por una. ([MoodleDocs][1])

![alt](./img/Captura%20de%20pantalla%202026-09-02%20125814.png)
---

## 3.4. Dar de baja a los estudiantes

En la sección **Roles**:

**Dar de baja a usuarios → Estudiante**

No seleccionar **Profesor** ni otros roles.

Mantener desmarcadas las demás opciones de esta sección, como:

* Todas las asignaciones de rol locales.
* Todas las modificaciones en el curso.

Ejecutar finalmente **Reiniciar curso**.

**Por qué:** esta opción desmatricula de forma masiva a quienes tienen el rol seleccionado. Moodle la describe expresamente como una operación de *unenrolment*, por lo que evita tener que seleccionar y desmatricular manualmente a todos los alumnos desde Participantes. ([MoodleDocs][2])

Además, elimina el riesgo que habíamos detectado con la desmatriculación manual masiva: **seleccionar accidentalmente también al profesor y perder el acceso al propio curso**. En la versión anterior de la guía ya habíamos señalado este peligro. 

---

# 4. Comprobar el resultado del reinicio

Una vez terminado:

1. Entrar en **Participantes** y comprobar que los estudiantes antiguos ya no aparecen matriculados.
2. Revisar varias actividades:

   * una tarea;
   * un cuestionario;
   * alguna restricción de acceso por fecha.
3. Comprobar que sus fechas se han desplazado correctamente al nuevo curso.

Después habrá que corregir manualmente las excepciones derivadas del calendario escolar: festivos, evaluaciones, Navidad, Semana Santa, etc. En la guía anterior ya contemplábamos esta revisión posterior. 

---

# 5. Matricular al alumnado del nuevo curso

**Dónde:**
**Participantes → Matricular usuarios**

Matricular normalmente a los estudiantes de la nueva promoción.

El resultado será:

* **Promoción actual:** matriculada y utilizando el curso.
* **Promociones anteriores:** desmatriculadas, pero manteniendo en Moodle los datos que no hayamos eliminado durante el reinicio.

Si posteriormente necesitamos consultar la información de un alumno antiguo, podemos **volver a matricularlo temporalmente**, consultar sus datos y volver a desmatricularlo.

---

# 6. Riesgos y precauciones

Este procedimiento **conserva mucho histórico, pero no equivale a mantener congelada una copia completa del curso anterior**.

Al desmatricular y volver a matricular posteriormente a un alumno pueden producirse algunos cambios: las **asignaciones manuales a grupos pueden perderse**, las suscripciones a foros vuelven a su configuración predeterminada, algunas fechas de finalización pueden cambiar y, dependiendo del método de matriculación y de la configuración del servidor, alguna calificación puede requerir restauración o recálculo. ([MoodleDocs][3])

Además:

* Nuestra `.mbz` **no protege los datos del alumnado**, porque no tenemos permiso para incluirlos.
* Al modificar cada año actividades y materiales, el curso deja de ser una reproducción exacta de cómo era años atrás.
* Algunos plugins o tipos de actividad pueden no soportar completamente el reinicio; por eso es importante comprobar varias actividades después de ejecutarlo.
* **Nunca deben marcarse accidentalmente las opciones «Todas las entregas», «Todos los intentos», etc.**, porque esas opciones sí eliminan información. Moodle advierte expresamente de que los datos seleccionados para eliminar durante un reinicio se pierden de forma permanente. ([MoodleDocs][2])

Por ello, la combinación que utilizaremos será:

**Excel anual de calificaciones + copia opcional de estructura + datos históricos conservados en el propio Moodle mediante desmatriculación.**

Esta versión me parece ya bastante más operativa que la anterior: el **paso 3 concentra todo lo delicado del cambio de curso** y reduce bastante el texto sin perder las advertencias importantes.

[1]: https://docs.moodle.org/405/en/course/reset?utm_source=chatgpt.com "Reset course - MoodleDocs"
[2]: https://docs.moodle.org/502/en/course/reset?utm_source=chatgpt.com "Reset course - MoodleDocs"
[3]: https://docs.moodle.org/403/en/Unenrolment?utm_source=chatgpt.com "Unenrolment - MoodleDocs"
