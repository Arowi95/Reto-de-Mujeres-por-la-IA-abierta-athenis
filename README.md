# Reto "Mujeres por la IA Abierta"

Reto organizado por la **Secretaría de Estado de Digitalización e Inteligencia Artificial (SEDIA)**, en el marco de la **Comunidad IA de Código Abierto**, para impulsar una inteligencia artificial abierta más diversa, inclusiva y libre de sesgos, incorporando el talento de mujeres a su diseño y construcción desde el principio.

## Entidades colaboradoras

- **Universitat Politècnica de Catalunya (UPC)** y su centro de investigación **IDEAI** (Intelligent Data Science and Artificial Intelligence)
- **Col·legi Oficial d'Enginyeria en Informàtica de Catalunya (COEINF)** y su comisión de género donesCOEINF.
- **OVHcloud**

## Objetivos del reto

- Desarrollar soluciones de IA abierta que permitan visibilizar la presencia de las mujeres y analizar su representación y protagonismo en el entorno digital.
- Fomentar soluciones reutilizables, publicadas en abierto bajo licencias de código abierto.
- Visibilizar el talento técnico de mujeres en el ámbito de la inteligencia artificial.
- Facilitar la transferencia de conocimiento, la innovación abierta y la incorporación de la perspectiva de género al desarrollo tecnológico.

## El desafío

Los equipos deberán:

1. Realizar una **propuesta conceptual de métricas** para cuantificar la presencia de mujeres y su rol protagonista en los contenidos digitales. Por ejemplo, analizando audio, ¿cuales serian los indicadores de rol protagonista? Algunos serian hablar al principio de un acto publico, o cerrarlo.... pero puede haber muchos más. ¿Tu equipo cómo lo va a tratar en el reto?
2. Construir un **sistema inteligente** capaz de analizar vídeos, audios o textos para extraer dichas métricas, pudiendo elegirse una única modalidad (vídeo, audio o texto).
3. Definir un **plan de puesta en producción**, incluyendo los permisos o acuerdos necesarios para un despliegue ético y legal.

## Recursos para los equipos

### Infraestructura de cómputo (OVHcloud)

OVHcloud ha cedido dos tipos de recursos para la realización del reto, máquinas virtuales para cómputo con GPU y AI Endpoints con acceso a distintos modelos.

#### Máquinas virtuales

Se facilitará a cada equipo un entorno virtual compartido para cómputo con GPU, con las siguientes características:

- Entornos **preconfigurados** con jupyterlab.
- **GPU:** 2 NVIDIA V100S.
- Uso exclusivo para el reto, no transferibles entre equipos.

> ⚠️ Las GPU V100S pueden presentar incompatibilidades con versiones recientes de algunos LLM y con determinadas precisiones numéricas.

#### APIs de modelos: OVHcloud AI Endpoints

Se facilitará a cada equipo un access token para utilizar el AI Endpoints de OVHcloud, inferencia serverless de modelos abiertos a través de una **API compatible con OpenAI**.

- **URL base:** `https://oai.endpoints.kepler.ai.cloud.ovh.net/v1`
- **Catálogo de modelos:** https://www.ovhcloud.com/en/public-cloud/ai-endpoints/catalog/
- **Acceso:** uso gratuito con límites de peticiones.
- Uso exclusivo para el reto, no transferibles entre equipos.
- Puedes usarlo para configurar un asistente de código y para realizar tareas específicas según el modelo seleccionado. Para configurar el asistente de código con el AI Endpoint puedes seguir las instrucciones en este [link](https://docs.ovhcloud.com/en/guides/public-cloud/ai-machine-learning/ai-endpoints-code-assistant)

### Recursos aportados por la UPC / IDEAI



### Formación y mentoría

Jornadas formativas:

- 14 de octubre
  * 09:30 – 10:00 | Bienvenida SEDIA e infraestructura para el reto (OVHcloud)
  * 13:00 – 15:00 | Perspectiva de género — Karina Gibert
- 15 de octubre
  * 10:00 – 12:00 | Técnicas de tratamiento de voz y texto — Adrián Rodríguez Fonollosa
- 16 de octubre
  * 10:00 – 12:00 | Técnicas de tratamiento de imagen y vídeo — Verónica Vilaplana
  * 16:00 – 18:00 | Marco ético — Karina Gibert
- 17 de octubre
  * 09:00 – 11:00 | Innovación — Montse Guardia
 
Adicionalmente se pondrá a disposición de las participantes durante el reto una **presentación sobre buenas prácticas de código abierto**.

El material de las formaciones quedará a disposición de las participantes para poder consultarlo posteriormente.


## Requisitos de los proyectos

- Incorporar IA como elemento relevante de la solución.
- Estar orientados a un caso de uso concreto y aplicable, y ser técnicamente viables en el plazo previsto.
- Cumplir el marco ético europeo de la IA y la normativa vigente en privacidad, protección de datos e inteligencia artificial.
- Aceptar la publicación del repositorio como software de código abierto.
- Si se usan LLM mediante API, la solución debe ser **agnóstica respecto al modelo** y permitir integrar modelos abiertos. Se valorará positivamente el uso efectivo de modelos abiertos.

No se admitirán proyectos sin componente tecnológico significativo, sin relación con la IA o con la temática del reto, que no puedan publicarse en abierto o que incumplan la perspectiva ética y de género o la legalidad vigente.

## Entregables

Antes del **30 de octubre de 2026 a las 08:00**:

1. Repositorio público con el código, documentado y publicado bajo una licencia reconocida por la OSI o la FSF y con las especificaciones del apartado de [Código Abierto](#codigo-abierto).
2. `README.md` con descripción de la solución, instrucciones de instalación y uso, componentes de terceros y sus licencias, y hoja de ruta.
3. Presentación `.pptx` (máx. 20 diapositivas) con métricas, datos utilizados, aproximación, resultados experimentales, demo, plan de puesta en producción, perspectiva de género, marco ético, cumplimiento normativo, riesgos y conclusiones.
4. Vídeo explicativo de 5 minutos.

Previo al inicio del evento del **4 de noviembre de 2026**:

5. Versión corta del `.pptx` para una presentación de 5 minutos con demo.

La falta de cualquier entregable en plazo implica la exclusión del proceso de evaluación.

## Código Abierto

- El código se publicará en un repositorio público dentro de la **organización de GitHub de la Comunidad IA de Código Abierto**.
- Licencias reconocidas por la Open Source Initiative o la Free Software Foundation.
- El proyecto debe ser técnicamente reproducible y reutilizable por terceros.
- Se permite software preexistente si se identifica claramente, se respeta su licencia y es compatible con la del proyecto. Solo se evaluará lo desarrollado durante el periodo del reto.
- Se valorará positivamente el cumplimiento con las buenas prácticas indicadas en la presentación sobre código abierto que se os facilitará a lo largo del reto.

## Evaluación

Jurado técnico (evaluación previa en remoto) y jurado de alto nivel (decisión final tras la presentación presencial: 5 min de exposición + 3 min de preguntas).

**Bloque 1 – Valoración técnica (60 %)**
- Calidad técnica de la solución: 30 %
- Perspectiva de género: 10 %
- Alineamiento con principios de código abierto: 10 %
- Aspectos éticos y normativos: 5 %
- Plan de despliegue: 5 %

**Bloque 2 – Propuesta y defensa (40 %)**
- Impacto: 15 %
- Innovación: 15 %
- Comunicación: 10 %

## Términos y condiciones

La participación implica la aceptación íntegra de los [términos y condiciones del reto](docs/terminos-y-condiciones.pdf).

## Contacto

comunidad.ia.os@digital.gob.es
