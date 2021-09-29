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



## **REGLAS DE NEGOCIO:**
- RN000 El sistema tiene un unico perfil y rol de usuario Gerente.
- RN001 El gerente puede gestionar pacientes.
- RN002	El gerente puede gestionar turnos.
- RN003	El gerente puede administrar el catálogo de productos.
- RN004	Descuentos para aplicar sobre valor de productos de catálogo.
- RN005	El sistema guarda un historial de atenciones de cada paciente.

  
| Nombre: | El sistema tiene un unico perfil y rol de usuario Gerente (actor principal del sistema). |
| ----- | ---- |
| Identificador: | *RN000* |
| Descripción: | El sistema tendrá un perfil y rol de usuario, siendo el mismo Gerente. El Gerente debe poder tener completa operabilidad en el sistema, pudiendo gestionar los pacientes, turnos y catálog, así como poder gestionar y configurarlos descuentos del sistema. |
| Condiciones/consideraciones: | N/A |
| Ejemplo casos: | - El Gerente debe tener completo control del sistema para su completa operabilidad sobre los módulos existentes: gestión de pacientes, gestión de turnos, administración de catálogo, configuración de descuentos y actualización de observaciones para el historial de cada paciente. |
| Fuente: | Operabilidad de sistema integral, 1er relevamiento |
| Reglas relacionadas: | RN001, RN002, RN003, RN004 |  


| Nombre: | El Gerente puede gestionar pacientes. |
| ----- | ---- |
| Identificador: | *RN001* |
| Descripción: | El sistema permitirá al Gerente realizar la administración de los pacientes. Debe permitir registrar un nuevo paciente, modificar y dar de baja los existentes. |
| Condiciones/consideraciones: | El paciente no debe existir con anterioridad para proceder con el alta. En caso de modificación/baja, debe existir un paciente sobre el cual realizar la operación. |
| Ejemplo casos: | - En caso de que un nuevo paciente se agregue a la cartera de clientes, se debe poder dar de alta el mismo con todos los datos necesarios para operar. - En caso de que un cliente modifique alguno de sus datos o el Gerente requiera corregir datos ingresados, debe tener potestad de realizarlo en plenitud de acción. - En caso de que un cliente finalice su tratamiento o desee discontinuarlo, el Gerente debe poder dar de baja el mismo. |
| Fuente: | Operabilidad de pacientes, 1er relevamiento |
| Reglas relacionadas: | N/A |  


| Nombre: | El Gerente puede gestionar turnos. |
| ----- | ---- |
| Identificador: | *RN002* |
| Descripción: | El sistema permitirá al Gerente realizar la gestión de turnos de los pacientes. Debe permitir registrar un nuevo turno, modificar y/o cancelar existentes. |
| Condiciones/consideraciones: | El cliente debe estar registrado en las tablas de paciente para poder gestionar el turno y encontrarse activo. |
| Ejemplo casos: | - En caso de que registre un turno a un paciente, se debe poder ingresar todos los datos pertinentes al tratamiento a realizar (detallados en la descripción de la funcionalidad relacionada). - En caso de que un cliente solicite la modificación del turno, el Gerente deberá estar habilitado a modificar los datos ingresados con anterioridad siempre que el sistema verifique que no se sobreponga con otro, teniendo en consideración el tipo de tratamiento a realizar. - En caso de que un cliente desee cancelar su turno, el Gerente debe tener potestad de cancelarlo/anularlo. |
| Fuente: | Necesidad de operabilidad sobre turnos de pacientes, 1er relevamiento |
| Reglas relacionadas: | RN001, RN005 |  


| Nombre: | El Gerente puede administrar el catálogo de productos. |
| ----- | ---- |
| Identificador: | *RN003* |
| Descripción: | El sistema permitirá al Gerente realizar la administración del catálogo de productos. Debe permitir ingresar un nuevo producto, modificar y/o discontinuar existentes. |
| Condiciones/consideraciones: | N/A |
| Ejemplo casos: | - En caso de que un paciente desee realizar la compra de los productos para continuar su tratamiento en el hogar, el Gerente debe poder consultar el valor final de los items según marca, nombre y/o uso para proveer la información al cliente. - Deberá poder ver el costo acorde al descuento, que el Gerente tendrá potestad de aplicar o no en caso de ser un paciente en tratamiento activo o de tener una promoción externa activa. |
| Fuente: | Catálogo de productos para consultas, 2do relevamiento |
| Reglas relacionadas: | N/A |  


| Nombre: | Descuentos para aplicar sobre valor de productos de catálogo. |
| ----- | ---- |
| Identificador: | *RN004* |
| Descripción: | El sistema permitirá al Gerente configurar el porcentaje, actualizar o discontinuar descuentos. |
| Condiciones/consideraciones: | No se debe requerir información de ningún paciente para acceder al módulo. |
| Ejemplo casos: | - En caso de que un cliente desee realizar la compra de los productos para continuar su tratamiento en el hogar y se encuentre en tratamiento activo, será pasivo de recibir el descuento, quedanda a juicio del Gerente la aplicación del mismo. - En caso de que el Gerente desee aplicar un descuento promocional con algún otro criterio, deberá mostrarse el precio final del producto consultado, dejando a criterio del Gerente su aplicación. |
| Fuente: | Catálogo de productos para consultas, 2do relevamiento |
| Reglas relacionadas: | RN003 |  


| Nombre: | El sistema guarda un historial de atenciones de cada paciente. |
| ----- | ---- |
| Identificador: | *RN005* |
| Descripción: | El sistema registrará en base de datos el historial de atenciones asociado a cada paciente tras cada turno (según lo detallado en la funcionalidad relacionada), información que será ingresada por el Gerente tras cada atención realizada en los turnos previamente registrados. Permitirá al Gerente agregar las observaciones y detalle del trabajo realizado, mismos que conformarán el historial médico. |
| Condiciones/consideraciones: | Debe existir un paciente registrado y contar con el turno. |
| Ejemplo casos: | - El Gerente debe poder, al realizar la atención correspondiente al cliente, actualizar el historial con una nueva entrada, adjuntando la información relevada tras la sesión. - El Gerente debe poder consultar, sin necesidad de un turno activo, el historial de cualquier paciente accediendo por su identificación, para poder tener libre acceso a la información necesaria para brindar el servicio. |
| Fuente: | Historial de atenciones particular por paciente, 1er relevamiento |
| Reglas relacionadas: | RN001, RN002 |  
