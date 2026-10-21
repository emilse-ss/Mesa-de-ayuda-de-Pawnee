# Auditoría · Versión B
Código: ___
Repositorio público propio: ___
Rama: ___

## B-01 · No se guarda la edición del avistamiento
### Síntoma
Acción/datos, esperado y observado ANTES:
A la hora de editar un avistamiento, el backend rechazaba el cuerpo ("Campos no permitidos en el cuerpo"). La consola mostrabba un PUT inválido y también había un ERR_INTERNET_DISCONNECTED.

### Causa
Explicación causal y archivo/capa, no solo su nombre:
El formulario estaba enviando criaturaId cuando era necesario el campo criatura para poder porcesar el cuerpo de los datos.

### Cambio
Qué modifiqué, por qué resuelve la causa y commit de corrección:
Establecer criatura dentro de los parámetros de crear y enviar, de esta forma son validados correctamente.

### Prueba
Pasos/comando, datos, status/resultado esperado y observado DESPUÉS; archivo de evidencia:
    datos[id ? 'criaturaId' : 'criatura'] = form.criatura; pasa a
    datos.criatura = form.criatura;

### Estado
Resuelto / parcial / no resuelto. Si es parcial, qué falta:
Resuelto

## B-02 · El detalle no identifica a la criatura
### Síntoma
Acción/datos, esperado y observado ANTES:

### Causa
Explicación causal y archivo/capa, no solo su nombre:

### Cambio
Qué modifiqué, por qué resuelve la causa y commit de corrección:

### Prueba
Pasos/comando, datos, status/resultado esperado y observado DESPUÉS; archivo de evidencia:

### Estado
Resuelto / parcial / no resuelto. Si es parcial, qué falta:

## B-03 · Se acepta un tipo de criatura inválido
### Síntoma
Acción/datos, esperado y observado ANTES:
El reporte indica que la API permite actualizar una criatura con el tipo inválido fantasma.

### Causa
Explicación causal y archivo/capa, no solo su nombre:
En la capa de servicios, criaturas.service.ts, la actualización de Mongoose no activa validaciones del esquema. El modelo sí restringe tipo a los valores permitidos.

### Cambio
Qué modifiqué, por qué resuelve la causa y commit de corrección:
Agregar runValidators: true a las opciones de actualización. De esta manera reconoce los datos para poder validarlos.

### Prueba
Pasos/comando, datos, status/resultado esperado y observado DESPUÉS; archivo de evidencia:
Sin prueba posterior confirmada; falta verificar tipo válido, rechazo de fantasma con 400 y que un GET conserve el tipo válido anterior.

### Estado
Resuelto / parcial / no resuelto. Si es parcial, qué falta:
Parcial. Falta una cinfirmación dentro de un cliente HTTP.


## B-04 · El filtro de avistamientos no actualiza
### Síntoma
Acción/datos, esperado y observado ANTES:

### Causa
Explicación causal y archivo/capa, no solo su nombre:

### Cambio
Qué modifiqué, por qué resuelve la causa y commit de corrección:

### Prueba
Pasos/comando, datos, status/resultado esperado y observado DESPUÉS; archivo de evidencia:

### Estado
Resuelto / parcial / no resuelto. Si es parcial, qué falta:

