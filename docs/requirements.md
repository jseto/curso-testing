# Proyecto de Reserva de Clases como un Servicio en la Nube 

## Requisitos de la Aplicación

- Permitir la existencia de multiples escuelas

### Actuando como Administrador de una Escuela

#### Definir Curso

- Solo el administrador puede definir un curso

- Asignar Título

- Asignar Profesor

	- Impedir asignar a un profesor ya asignado

		- no se asignará si el profesor ya tiene ocupados la hora y el día

- Asignar Número máximo de Alumnos

	- no deberia poderse asignar menos de 1 plaza

- Asignar Horario

	- Impedir asignar horario si el profesor no está disponible

	- Asignar Días de no disponibilidad (vacaciones, fines de semana,...)

- Asignar nivel del curso

#### Definir alumno

- Solo el administrador puede definir a un alumno

- Asignar nombre

- Asignar nivel conocimientos

#### Definir profesor

- Solo el administrador o el mismo profesor puede definir a un profesor

- Asignar nombre

- Asignar nivel docente

- Asignar disponibilidad de horario

### Actuando como Alumno

#### Matricularse en un curso

- Solo el mismo alumno o el administrador pueden martricular

- Permitir seleccionar curso

	- No permitir matricularse a un curso de nivel superior a sus conocimientos

	- No permitir matricularse a un curso completo

	- Verificar que el horario seleccionado está disponible.