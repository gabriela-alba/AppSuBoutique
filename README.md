# Aplicación Su boutique

## **Detalle del alcance:**

Este proyecto es un sistema de gestión de operaciones principales tales como registro, historial de pacientes, catálogo de productos y gestión de visitas para una clínica de cosmetología para el cuidado de piel.

## **Descripción de las funcionalidades:**

_**Registro de pacientes**_

El paciente se debe registrar con los siguientes datos:
- Nombre
- Apellido
- DNI
- Fecha de nacimiento (calendario)
- Teléfono
- Domicilio
- Descripción (antecedentes médicos)
    - Biotipo de piel: es la clasificación del tipo de piel (grasa, seca, mixta, etc.)
    - Fototipo de piel: es la clasificación de los tonos de piel del 1 al 5
- Tratamiento / observaciones

El sistema notificará en caso de ya existir un usuario con el mismo DNI

_**Catálogo de productos**_

El nuevo producto se debe agregar con los siguientes datos:
- Nombre
- Precio

El sistema permitirá:
- Agregar nuevo producto con precio
- Modificar producto
- Eliminar producto

_**Agendar visitas (sólo para owner del sistema inicialmente)**_

- Reservar turno
- Fecha (calendario)
- Hora
- Paciente (desplegable)

El sistema permitirá:
- Modificar turno
- Eliminar turno
- Notificación automática vía sms o whatsapp

## **Lógica de negocio:**

- El sistema permitirá registrar pacientes
- Solo se podrá agendar un turno a un paciente que haya sido previamente registrado en el sistema
- Los turnos serán gestionados por el product owner quedando bajo su responsabilidad establecer los horarios de inicio y fin del servicio, así como la cantidad de pacientes máximos que se atenderán diariamente
- El sistema aplicará un descuento en caso de que el paciente se encuentre en tratamiento activo
- El catálogo disponible de forma online no será utilizado para E-Commerce. Su función será facilitar al product owner la gestión de sus productos para ofrecerlos a sus clientes durante las consultas de forma presencial
