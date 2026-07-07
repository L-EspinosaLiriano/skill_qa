# Skill: Diseño y Redacción Profesional de Casos de Prueba

## 📌 Descripción de la Habilidad

Capacidad para transformar historias de usuario, criterios de aceptación, reglas de negocio, diseños funcionales y requerimientos técnicos en especificaciones operativas detalladas denominadas **Casos de Prueba**.

El objetivo de esta habilidad es garantizar una cobertura funcional adecuada de los requerimientos, validar el comportamiento esperado del sistema, detectar ambigüedades antes de la ejecución, reducir riesgos de negocio y prevenir fallos en ambientes productivos.

Los casos de prueba deben ser:

- Claros.
- Reproducibles.
- Trazables.
- Atómicos.
- Medibles.
- Priorizados según riesgo.
- Basados únicamente en fuentes de información confirmadas.
- Aptos para ejecución manual o automatización cuando corresponda.

> Los casos de prueba funcionales no garantizan por sí solos cobertura de código. La cobertura de código debe medirse mediante pruebas unitarias, de integración o automatizadas utilizando herramientas especializadas.

---

# 🧭 Conceptos Clave y Glosario Técnico

## Caso de Prueba — Test Case

Instrumento operativo que define las precondiciones, datos, acciones y resultados esperados necesarios para validar que una funcionalidad se comporte según lo establecido.

## Escenario de Prueba — Test Scenario

Descripción de alto nivel de una situación funcional que debe validarse. Un escenario puede originar uno o varios casos de prueba.

## Oráculo de Pruebas — Source of Truth

Fuente primaria utilizada para determinar el comportamiento correcto del sistema.

Puede incluir:

- Historia de usuario.
- Criterios de aceptación.
- Reglas de negocio.
- Prototipos o diseños aprobados.
- Contratos de API.
- Documentación funcional.
- Documentación técnica.
- Expertos del negocio.
- Product Owner.
- Arquitectura aprobada.

## Precondición

Estado previo obligatorio en el que debe encontrarse el sistema, el usuario, los datos o el ambiente antes de ejecutar un caso de prueba.

## Postcondición

Estado final o efecto secundario esperado después de ejecutar un caso de prueba.

Ejemplos:

- Actualización de un registro.
- Creación de una auditoría.
- Cambio de estado.
- Envío de una notificación.
- Actualización de un contador.

> No todas las pruebas requieren postcondiciones.

## Limpieza de Datos — Test Cleanup

Acciones requeridas para restablecer el entorno después de ejecutar una prueba.

Ejemplos:

- Eliminar registros creados.
- Restaurar estados.
- Desbloquear usuarios.
- Limpiar archivos temporales.

## Datos de Prueba

Valores específicos utilizados durante la ejecución.

Deben indicar:

- Valor.
- Tipo.
- Propósito.
- Clasificación.
- Estado requerido.
- Origen.
- Si son reutilizables o temporales.

## Trazabilidad

Relación verificable entre un caso de prueba y su fuente de origen.

Ejemplos:

- Historia de usuario.
- Criterio de aceptación.
- Requisito funcional.
- Regla de negocio.
- Defecto.
- Diseño aprobado.

## Tabla de Decisión

Técnica utilizada para modelar combinaciones de condiciones y acciones.

Cuando existen `n` condiciones booleanas, el número máximo teórico de combinaciones es:

\[
2^n
\]

No siempre es necesario ejecutar todas las combinaciones.

Se deben eliminar:

- Combinaciones imposibles.
- Combinaciones redundantes.
- Reglas equivalentes.
- Escenarios sin valor funcional.
- Casos de bajo riesgo cuando exista una estrategia de reducción aprobada.

## Partición de Equivalencia

Técnica que divide los valores de entrada en grupos que deberían producir un comportamiento equivalente.

Ejemplo para un campo de edad entre 18 y 65:

- Menor de 18.
- Entre 18 y 65.
- Mayor de 65.

## Análisis de Valores Límite

Técnica que valida valores cercanos a los bordes permitidos.

Ejemplo:

- 17.
- 18.
- 19.
- 64.
- 65.
- 66.

## Transición de Estados

Técnica utilizada cuando el comportamiento depende del estado actual del sistema.

Ejemplo:

- Pendiente.
- Aprobado.
- Rechazado.
- Cancelado.

## Pairwise

Técnica de reducción de combinaciones que busca cubrir pares significativos de variables sin ejecutar todas las combinaciones posibles.

Se recomienda cuando existe una gran cantidad de condiciones y la ejecución total no es viable.

## Enmascaramiento de Errores

Antipatrón en el que se utilizan múltiples datos inválidos simultáneamente y un error intermedio impide observar otro.

## Caso de Alto Nivel

Caso que describe un flujo general y asume conocimiento previo del sistema.

## Caso de Bajo Nivel

Caso detallado que especifica acciones, datos y resultados de forma atómica.

## Prueba Positiva

Valida el comportamiento esperado utilizando datos válidos.

## Prueba Negativa

Valida el comportamiento del sistema ante datos inválidos, estados incorrectos o condiciones no permitidas.

## Riesgo

Resultado de combinar el impacto de una falla con su probabilidad de ocurrencia.

\[
Riesgo = Impacto \times Probabilidad
\]

## Severidad

Nivel de impacto técnico o funcional que tendría una falla.

## Prioridad

Orden en el que debe diseñarse, ejecutarse o automatizarse una prueba.

## Criterio de Entrada

Condiciones que deben cumplirse antes de iniciar la ejecución de pruebas.

## Criterio de Salida

Condiciones que deben cumplirse para considerar finalizada una fase de pruebas.

---

# 🧠 Principios Obligatorios

## 1. No inventar comportamientos

No deben inventarse:

- Mensajes de error.
- Códigos HTTP.
- Registros en base de datos.
- Reglas de negocio.
- Tiempos de espera.
- Límites.
- Postcondiciones.
- Cambios de estado.
- Notificaciones.
- Validaciones.
- Permisos.

Si la información no está definida, debe registrarse como:

- Ambigüedad.
- Pregunta abierta.
- Dependencia.
- Supuesto temporal.
- Riesgo funcional.

## 2. Basarse en el oráculo

Todo resultado esperado debe tener respaldo en una fuente confirmada.

## 3. Mantener trazabilidad

Todo caso de prueba debe estar vinculado a uno o varios requisitos.

## 4. Diseñar casos atómicos

Cada paso debe contener una sola acción principal y un resultado esperado verificable.

## 5. Aislar inicialmente los errores

Las pruebas negativas deben comenzar validando una condición incorrecta a la vez.

Después deben agregarse pruebas combinadas para validar:

- Múltiples errores simultáneos.
- Orden de presentación de mensajes.
- Persistencia de errores.
- Limpieza de campos.
- Reglas de prioridad.
- Comportamiento acumulado.

## 6. Priorizar por riesgo

Las funcionalidades críticas deben probarse primero.

## 7. Proteger los datos

No se deben utilizar:

- Contraseñas reales.
- Tokens productivos.
- Datos personales reales.
- Información bancaria real.
- Credenciales compartidas.
- Datos sensibles sin anonimización.

## 8. Garantizar reproducibilidad

Un caso debe poder ser ejecutado por otro integrante del equipo sin depender de conocimiento implícito.

---

# 🎯 Plan de Ejecución Paso a Paso

## Paso 1: Analizar el Insumo

Leer y analizar:

- Historia de usuario.
- Criterios de aceptación.
- Reglas de negocio.
- Diseños.
- Diagramas.
- Documentación técnica.
- Contratos de API.
- Casos existentes.
- Defectos relacionados.

Identificar:

- Actor.
- Objetivo.
- Flujo principal.
- Flujos alternos.
- Validaciones.
- Excepciones.
- Estados.
- Dependencias.
- Integraciones.
- Roles.
- Permisos.
- Datos involucrados.

## Paso 2: Identificar el Oráculo de Pruebas

Registrar las fuentes utilizadas.

```markdown
**Fuentes del Oráculo:**

- Historia: CWD-0000
- Criterios: CA-01, CA-02 y CA-03
- Diseño: Figma versión 4
- Regla de negocio: RN-12
- Contrato API: OpenAPI 3.0
```

Cuando exista conflicto entre fuentes, no asumir cuál es correcta. Registrar la inconsistencia y escalarla.

## Paso 3: Detectar Ambigüedades

Antes de diseñar los casos, identificar:

- Requisitos incompletos.
- Criterios contradictorios.
- Mensajes no definidos.
- Límites ausentes.
- Flujos sin resultado.
- Diferencias entre diseño y requerimiento.
- Estados no contemplados.
- Permisos no especificados.
- Dependencias externas no definidas.
- Casos sin comportamiento de error.

```markdown
## Preguntas y Ambigüedades Detectadas

| ID | Hallazgo | Impacto | Pregunta | Responsable |
|---|---|---|---|---|
| A-01 | No se indica el máximo de intentos | Alto | ¿Cuántos intentos puede realizar el usuario? | Negocio |
| A-02 | El diseño y el criterio muestran mensajes distintos | Medio | ¿Cuál texto debe considerarse oficial? | UX / PO |
```

## Paso 4: Registrar Supuestos

Cuando no sea posible obtener una respuesta inmediata, documentar los supuestos.

```markdown
## Supuestos Temporales

- Se asume que el usuario se bloquea después de cinco intentos.
- Se asume que el campo admite hasta 100 caracteres.
- Se asume que el endpoint responde en menos de cinco segundos.
```

Todo supuesto debe quedar marcado como pendiente de validación.

## Paso 5: Identificar Componentes

Enumerar los elementos involucrados.

Ejemplo:

- Campo de usuario.
- Campo de contraseña.
- Botón de inicio.
- Servicio de autenticación.
- Base de datos.
- Servicio de auditoría.
- Token de sesión.
- Mensaje de error.
- Sistema de bloqueo.

## Paso 6: Identificar Reglas de Negocio

```markdown
## Reglas de Negocio Identificadas

- RN-01: Solo los usuarios activos pueden iniciar sesión.
- RN-02: La contraseña debe tener mínimo ocho caracteres.
- RN-03: La cuenta se bloquea después del límite definido.
```

## Paso 7: Clasificar Riesgos

Evaluar cada flujo según:

- Impacto.
- Probabilidad.
- Frecuencia de uso.
- Exposición al usuario.
- Dependencias.
- Historial de defectos.
- Complejidad.
- Criticidad financiera.
- Criticidad regulatoria.

| Funcionalidad | Impacto | Probabilidad | Riesgo | Prioridad |
|---|---:|---:|---:|---|
| Inicio de sesión | 5 | 4 | 20 | Alta |
| Cambio de avatar | 2 | 2 | 4 | Baja |

Escala sugerida:

- 1: Muy bajo.
- 2: Bajo.
- 3: Medio.
- 4: Alto.
- 5: Crítico.

## Paso 8: Seleccionar Técnicas de Diseño

### Tabla de decisión

Usar cuando existen reglas combinadas y varias condiciones modifican el resultado.

### Partición de equivalencia

Usar cuando existen rangos o grupos de datos.

### Valores límite

Usar cuando hay mínimos, máximos, cantidades, fechas, longitudes o rangos.

### Transición de estados

Usar cuando el comportamiento depende del estado previo.

### Pairwise

Usar cuando existen demasiadas combinaciones y la ejecución exhaustiva no es viable.

### Casos de uso

Usar para validar flujos completos de usuario.

### Pruebas exploratorias

Usar como complemento cuando existen riesgos no cubiertos, alta incertidumbre o una funcionalidad nueva.

## Paso 9: Crear una Matriz de Escenarios

```markdown
| ID | Escenario | Tipo | Prioridad | Técnica | Criterio Cubierto |
|---|---|---|---|---|---|
| ESC-01 | Login con credenciales válidas | Positivo | Alta | Caso de uso | CA-01 |
| ESC-02 | Contraseña incorrecta | Negativo | Alta | Equivalencia | CA-02 |
| ESC-03 | Cuenta bloqueada | Negativo | Alta | Estados | CA-03 |
```

## Paso 10: Cubrir Tipos de Escenarios

Evaluar, cuando apliquen:

- Camino feliz.
- Flujos alternos.
- Validaciones negativas.
- Valores límite.
- Roles y permisos.
- Persistencia.
- APIs.
- Integraciones.
- Estados.
- Concurrencia.
- Seguridad.
- Accesibilidad.
- Rendimiento.
- Compatibilidad.

## Paso 11: Definir Precondiciones

```markdown
**Precondiciones:**

- El ambiente QA debe estar disponible.
- El usuario debe estar desautenticado.
- Debe existir una cuenta activa.
- La cuenta no debe estar bloqueada.
- El servicio de autenticación debe estar operativo.
```

## Paso 12: Definir Datos de Prueba

```markdown
| Dato | Valor | Clasificación | Propósito | Estado Requerido |
|---|---|---|---|---|
| Usuario | usuario.activo@test.com | Válido | Flujo positivo | Activo |
| Contraseña | Password123! | Válido | Autenticación | Vigente |
| Usuario bloqueado | bloqueado@test.com | Negativo | Validar restricción | Bloqueado |
```

## Paso 13: Redactar Casos Atómicos

> Cada paso debe contener una sola acción principal y un resultado esperado directamente verificable.

## Paso 14: Definir Resultado Esperado General

```markdown
**Resultado Esperado General:**

El usuario accede correctamente al sistema, se crea una sesión válida y se muestra la pantalla principal autorizada para su perfil.
```

## Paso 15: Definir Postcondiciones

Solo documentar efectos confirmados.

## Paso 16: Definir Limpieza de Datos

```markdown
**Limpieza Posterior:**

- Cerrar la sesión.
- Eliminar los registros creados durante la prueba.
- Restaurar el estado original del usuario.
```

## Paso 17: Definir Evidencias

```markdown
**Evidencias Requeridas:**

- Captura del resultado.
- Código y cuerpo de respuesta de la API.
- Registro de consola si ocurre un error.
- Consulta de base de datos antes y después.
- Identificador de transacción.
```

## Paso 18: Evaluar Automatización

```markdown
**Candidato a Automatización:** Sí  
**Nivel:** API  
**Suite:** Regresión  
**Frecuencia:** Por despliegue  
**Estabilidad:** Alta
```

## Paso 19: Revisar Cobertura

```markdown
| Criterio | Casos Asociados | Cobertura |
|---|---|---|
| CA-01 | TC-LOGIN-001 | Cubierto |
| CA-02 | TC-LOGIN-002, TC-LOGIN-003 | Cubierto |
| CA-03 | Sin casos | Pendiente |
```

## Paso 20: Revisión de Calidad

Confirmar:

- Trazabilidad.
- Títulos claros.
- Precondiciones verificables.
- Datos definidos.
- Pasos atómicos.
- Resultados medibles.
- Ausencia de comportamientos inventados.
- Cobertura positiva y negativa.
- Riesgo y prioridad.
- Evidencias.
- Automatización.
- Limpieza.
- Reproducibilidad.

---

# 🏷️ Convención de Nombres

Usar:

```text
[Componente] - [Acción] - [Condición] - [Resultado]
```

Ejemplos:

- Login - Autenticar usuario con credenciales válidas.
- Login - Rechazar contraseña incorrecta.
- Campañas - Impedir guardar sin nombre obligatorio.
- Solicitudes - Mostrar error al consultar un registro inexistente.

---

# 📋 Plantilla Estándar de Caso de Prueba

```markdown
### 🆔 [ID_DEL_CASO] - [Título descriptivo]

**Historia Relacionada:** [ID]  
**Criterio de Aceptación:** [CA-XX]  
**Requisito Relacionado:** [RF-XX]  
**Regla de Negocio:** [RN-XX]  
**Módulo:** [Nombre del módulo]  
**Componente:** [Pantalla, API o servicio]  
**Tipo de Prueba:** [Funcional / API / Integración / UI]  
**Nivel:** [Sistema / Integración / Componente]  
**Prioridad:** [Alta / Media / Baja]  
**Riesgo:** [Crítico / Alto / Medio / Bajo]  
**Suite:** [Smoke / Sanity / Regresión]  
**Candidato a Automatización:** [Sí / No]

---

## Descripción

[Descripción breve y precisa de la funcionalidad o condición bajo prueba.]

## Fuentes del Oráculo

- [Historia de usuario]
- [Criterio de aceptación]
- [Diseño aprobado]
- [Regla de negocio]
- [Contrato de API]

## Precondiciones

- [Precondición 1]
- [Precondición 2]
- [Precondición 3]

## Dependencias

- [Servicio]
- [Base de datos]
- [Integración]
- [Permiso]
- [Configuración]

## Datos de Prueba

| Dato | Valor | Clasificación | Propósito | Estado Requerido |
|---|---|---|---|---|
| [Dato] | [Valor] | [Válido / Inválido / Límite] | [Propósito] | [Estado] |

## Pasos de Ejecución y Resultados

| Paso | Acción Atómica | Resultado Esperado |
|---:|---|---|
| 1 | [Acción única] | [Resultado verificable] |
| 2 | [Acción única] | [Resultado verificable] |
| 3 | [Acción única] | [Resultado verificable] |

## Resultado Esperado General

[Comportamiento final esperado del sistema.]

## Postcondiciones

- [Efecto confirmado]
- [Cambio de estado confirmado]
- [Registro generado]

## Limpieza Posterior

- [Acción de limpieza]
- [Restauración de datos]
- [Eliminación de registros]

## Evidencias Requeridas

- [Captura de pantalla]
- [Respuesta de API]
- [Consulta de base de datos]
- [Log]
- [Identificador de transacción]

## Condiciones de Bloqueo

- [Ambiente no disponible]
- [Servicio externo no operativo]
- [Datos inexistentes]
- [Permisos ausentes]

## Resultado Obtenido

_[Completar durante la ejecución con el comportamiento real observado.]_

## Estado de Ejecución

- ⚪ No ejecutado
- 🟡 En ejecución
- 🟢 Aprobado
- 🔴 Fallido
- ⚫ Bloqueado
- 🔵 No aplica

## Defecto Relacionado

- **ID:** [BUG-0000]
- **Severidad:** [Crítica / Alta / Media / Baja]
- **Evidencia:** [Enlace o referencia]
```

---

# 📑 Plantilla de Matriz de Escenarios

```markdown
| ID | Escenario | Tipo | Técnica | Prioridad | Riesgo | Criterio Cubierto | Automatizable |
|---|---|---|---|---|---|---|---|
| ESC-01 | [Escenario] | Positivo | Caso de uso | Alta | Alto | CA-01 | Sí |
| ESC-02 | [Escenario] | Negativo | Equivalencia | Alta | Alto | CA-02 | Sí |
| ESC-03 | [Escenario] | Límite | Valores límite | Media | Medio | CA-03 | Sí |
```

---

# 📐 Plantilla de Tabla de Decisión

```markdown
| Condición / Regla | R1 | R2 | R3 | R4 |
|---|---:|---:|---:|---:|
| Usuario existe | Sí | Sí | No | No |
| Contraseña válida | Sí | No | Sí | No |
| Usuario activo | Sí | Sí | N/A | N/A |
| Permitir acceso | Sí | No | No | No |
| Mostrar error | No | Sí | Sí | Sí |
```

Después de crear la tabla:

1. Eliminar combinaciones imposibles.
2. Consolidar reglas equivalentes.
3. Priorizar combinaciones críticas.
4. Aplicar pairwise si la cantidad es excesiva.
5. Crear casos separados por regla significativa.

---

# 📈 Plantilla de Trazabilidad

```markdown
| Requisito | Criterio | Regla | Caso de Prueba | Estado |
|---|---|---|---|---|
| RF-01 | CA-01 | RN-01 | TC-001 | Cubierto |
| RF-01 | CA-02 | RN-02 | TC-002 | Cubierto |
| RF-02 | CA-03 | RN-03 | Pendiente | Sin cobertura |
```

---

# 🚨 Reglas para Pruebas Negativas

## Primera fase: aislamiento

Modificar una sola condición inválida por prueba.

## Segunda fase: combinación

Agregar escenarios con errores simultáneos y validar:

- Mensaje mostrado.
- Orden de validaciones.
- Foco.
- Persistencia de datos.
- Limpieza de campos.
- Incremento de contadores.
- Llamadas innecesarias a servicios.

---

# 🔗 Reglas para Pruebas de API

Validar, cuando aplique:

- Método HTTP.
- URL.
- Encabezados.
- Autenticación.
- Autorización.
- Cuerpo de solicitud.
- Tipos de datos.
- Campos obligatorios.
- Campos opcionales.
- Códigos de respuesta.
- Estructura del cuerpo.
- Mensajes de error.
- Tiempo de respuesta.
- Paginación.
- Ordenamiento.
- Filtrado.
- Idempotencia.
- Duplicados.
- Reintentos.
- Límites.
- Seguridad.
- Persistencia.
- Auditoría.

> No inventar códigos HTTP si no existe un contrato o comportamiento confirmado.

---

# 🗄️ Reglas para Validaciones de Base de Datos

Verificar, cuando aplique:

- Creación.
- Actualización.
- Eliminación.
- Integridad referencial.
- Campos obligatorios.
- Valores predeterminados.
- Fechas.
- Usuario de creación.
- Usuario de modificación.
- Auditoría.
- Duplicados.
- Estados.
- Rollback.
- Transacciones.

> Nunca modificar directamente datos productivos para ejecutar una prueba.

---

# 🤖 Criterios de Automatización

Un caso es buen candidato cuando:

- Se ejecuta frecuentemente.
- Forma parte de smoke o regresión.
- Es crítico.
- Tiene datos estables.
- Tiene resultados objetivos.
- Reduce trabajo manual repetitivo.
- Puede ejecutarse de forma independiente.
- Tiene bajo nivel de variación visual.

---

# 🧹 Mantenimiento de Casos de Prueba

Revisar los casos cuando:

- Cambia el requerimiento.
- Cambia el diseño.
- Cambia una API.
- Se modifica una regla de negocio.
- Se detecta un defecto.
- Se elimina una funcionalidad.
- Cambian los roles.
- Cambia el flujo.
- Se modifica la arquitectura.
- Se automatiza el caso.

---

# ✅ Checklist Final de Calidad

- [ ] Existe trazabilidad con los requisitos.
- [ ] Todos los criterios de aceptación están cubiertos.
- [ ] Las ambigüedades fueron documentadas.
- [ ] Los supuestos están identificados.
- [ ] Los títulos son claros.
- [ ] Las precondiciones son verificables.
- [ ] Los datos de prueba están definidos.
- [ ] Cada paso contiene una sola acción.
- [ ] Cada resultado es verificable.
- [ ] No se inventaron comportamientos.
- [ ] Se incluyeron pruebas positivas.
- [ ] Se incluyeron pruebas negativas.
- [ ] Se validaron límites.
- [ ] Se consideraron roles y permisos.
- [ ] Se consideraron integraciones.
- [ ] Se evaluaron riesgos.
- [ ] Se definió la prioridad.
- [ ] Se identificaron evidencias.
- [ ] Se definieron postcondiciones únicamente cuando aplican.
- [ ] Se incluyó limpieza de datos.
- [ ] Se evaluó la automatización.
- [ ] Se identificaron condiciones de bloqueo.
- [ ] El caso puede ser reproducido por otro miembro del equipo.
- [ ] El contenido representa la versión vigente del requerimiento.

---

# 🏁 Resultado Esperado de la Skill

Al aplicar esta habilidad, el resultado debe ser un conjunto de casos de prueba:

- Estructurados.
- Priorizados.
- Trazables.
- Reproducibles.
- Libres de supuestos ocultos.
- Orientados al riesgo.
- Adecuados para ejecución manual.
- Evaluados para automatización.
- Basados en fuentes confirmadas.
- Preparados para Jira, TestRail, Azure DevOps o documentación Markdown.

La calidad de un caso de prueba no se mide por la cantidad de pasos, sino por su capacidad para detectar defectos, validar riesgos y demostrar objetivamente que el comportamiento del sistema cumple con los requisitos aprobados.
