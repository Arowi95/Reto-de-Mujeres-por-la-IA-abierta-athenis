# Reto "Mujeres por la IA Abierta"

Reto organizado por la **Secretaría de Estado de Digitalización e Inteligencia Artificial (SEDIA)**, en el marco de la **Comunidad IA de Código Abierto**, para impulsar una inteligencia artificial abierta más diversa, paritaria y libre de sesgos, incorporando el talento de mujeres a su diseño y construcción desde el principio.

## Entidades colaboradoras

- **Universitat Politècnica de Catalunya (UPC)** y su centro de investigación **IDEAI** (Intelligent Data Science and Artificial Intelligence)
- **Col·legi Oficial d'Enginyeria en Informàtica de Catalunya (COEINF)**
- **OVHcloud**

## Objetivos del reto

- Desarrollar soluciones de IA abierta que permitan visibilizar la presencia de las mujeres y analizar su representación y protagonismo en el entorno digital.
- Fomentar soluciones reutilizables, publicadas en abierto bajo licencias de código abierto.
- Visibilizar el talento técnico de mujeres en el ámbito de la inteligencia artificial.
- Facilitar la transferencia de conocimiento, la innovación abierta y la incorporación de la perspectiva de género al desarrollo tecnológico.

## El desafío

Los equipos deberán:

1. Realizar una **propuesta conceptual de métricas** para cuantificar la presencia de mujeres y su rol protagonista en los contenidos digitales.
2. Construir un **sistema inteligente** capaz de rastrear vídeos, audios o textos para extraer dichas métricas.
3. Definir un **plan de puesta en producción**, incluyendo los permisos o acuerdos necesarios para un despliegue ético y legal.

## Recursos para los equipos

### Infraestructura de cómputo (OVHcloud)

OVHcloud cede recursos de cómputo en la nube alojados en centros de datos de la UE:

- **Tipo de instancia:** t2-le-180
- **GPU:** NVIDIA V100S
- Entornos **preconfigurados y validados** por la Organización.
- Uso exclusivo para el reto, no transferibles entre equipos y asignados de forma equitativa.

> ⚠️ Las GPU V100S pueden presentar incompatibilidades con versiones recientes de algunos LLM y con determinadas precisiones numéricas. No se atenderán incidencias derivadas de instalar versiones distintas a las facilitadas.

### Recursos aportados por la UPC / IDEAI

[PENDIENTE DE CONFIRMAR]

### Formación y mentoría

Jornadas formativas:

- Formación técnica sobre la infraestructura de OVHcloud.
- Perspectiva de género y marco ético.
- Técnicas de tratamiento de voz y texto.
- Técnicas de tratamiento de imagen y vídeo.
- Innovación.

Las formaciones quedarán grabadas para poder ser visualizadas por las participantes del reto posteriormente.

### APIs de modelos: OVHcloud AI Endpoints

>  [PENDIENTE DE CONFIRMAR  el acceso a AI Endpoints.]

OVHcloud AI Endpoints ofrece inferencia serverless de modelos abiertos a través de una **API compatible con OpenAI**, alojada en Europa.

- **URL base:** `https://oai.endpoints.kepler.ai.cloud.ovh.net/v1`
- **Catálogo de modelos:** https://www.ovhcloud.com/en/public-cloud/ai-endpoints/catalog/
- **Acceso:** uso gratuito con límites de peticiones, o con API key para límites más altos. La API key se genera en el [OVHcloud Manager](https://ovh.com/manager) → Public Cloud → AI & Machine Learning → AI Endpoints → API keys.

Al ser compatible con OpenAI, permite cumplir el requisito del reto de que la solución sea **agnóstica respecto al modelo**: basta con cambiar la URL base y el nombre del modelo para usar otro proveedor o un modelo desplegado en vuestra propia instancia.

## Guía rápida de instalación

### 1. Acceso al entorno de cómputo

[PENDIENTE: instrucciones de acceso a las instancias que facilitará la Organización en la formación del 7 de octubre.]

### 2. Preparar el entorno de Python

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install openai python-dotenv
```

### 3. Configurar las credenciales

Crea un archivo `.env` en la raíz del proyecto (y añádelo a `.gitignore` para no publicarlo nunca):

```bash
OVHCLOUD_API_KEY=tu_api_key
OVHCLOUD_BASE_URL=https://oai.endpoints.kepler.ai.cloud.ovh.net/v1
```

### 4. Primera llamada a un modelo

```python
import os
from dotenv import load_dotenv
from openai import OpenAI

load_dotenv()

client = OpenAI(
    api_key=os.getenv("OVHCLOUD_API_KEY", ""),
    base_url=os.getenv("OVHCLOUD_BASE_URL"),
)

# Consulta los modelos disponibles
for model in client.models.list():
    print(model.id)

# Ejemplo de llamada (sustituye el modelo por uno del catálogo)
response = client.chat.completions.create(
    model="Meta-Llama-3_3-70B-Instruct",
    messages=[{"role": "user", "content": "Hola, ¿qué puedes hacer?"}],
)
print(response.choices[0].message.content)
```

> 💡 Los nombres de los modelos pueden cambiar: consulta siempre el catálogo o usa `client.models.list()` antes de fijar uno en vuestro código.

## Requisitos de los proyectos

- Incorporar IA como elemento relevante de la solución.
- Estar orientados a un caso de uso concreto y aplicable, y ser técnicamente viables en el plazo previsto.
- Cumplir el marco ético europeo de la IA y la normativa vigente en privacidad, protección de datos e inteligencia artificial.
- Aceptar la publicación del repositorio como software de código abierto.
- Si se usan LLM mediante API, la solución debe ser **agnóstica respecto al modelo** y permitir integrar modelos abiertos. Se valorará positivamente el uso efectivo de modelos abiertos.

No se admitirán proyectos sin componente tecnológico significativo, sin relación con la IA o con la temática del reto, que no puedan publicarse en abierto o que incumplan la perspectiva ética y de género o la legalidad vigente.

## Entregables

Antes del **27 de octubre de 2026 a las 23:59**:

1. Repositorio público con el código, documentado y publicado bajo una licencia reconocida por la OSI o la FSF.
2. `README.md` con descripción de la solución, instrucciones de instalación y uso, componentes de terceros y sus licencias, y hoja de ruta.
3. Presentación `.pptx` (máx. 20 diapositivas) con métricas, datos utilizados, aproximación, resultados experimentales, demo, plan de puesta en producción, perspectiva de género, marco ético, cumplimiento normativo, riesgos y conclusiones.
4. Vídeo explicativo de 5 minutos.

El **4 de noviembre de 2026**, al inicio de la final:

5. Versión corta del `.pptx` para una presentación de 5 minutos con demo.

La falta de cualquier entregable en plazo implica la exclusión del proceso de evaluación.

## Código abierto

- El código se publicará en un repositorio público dentro de la **organización de GitHub de la Comunidad IA de Código Abierto**.
- Licencias reconocidas por la Open Source Initiative o la Free Software Foundation.
- El proyecto debe ser técnicamente reproducible y reutilizable por terceros.
- Se permite software preexistente si se identifica claramente, se respeta su licencia y es compatible con la del proyecto. Solo se evaluará lo desarrollado durante el periodo del reto.

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

## Reconocimiento

- **1.er puesto:** presentación de su solución en el **II Encuentro de Mujeres y Tecnología** (Madrid, 16–19 de noviembre de 2026) y sesión en Discord ante la Comunidad.
- **2.º y 3.er puesto:** entradas para el II Encuentro de Mujeres y Tecnología y sesión en Discord ante la Comunidad.
- **Todos los equipos:** certificado nominal de participación y difusión de resultados en la web y el Discord de la Comunidad.

## Términos y condiciones

La participación implica la aceptación íntegra de los [términos y condiciones del reto](docs/terminos-y-condiciones.pdf).

## Contacto

comunidad.ia.os@digital.gob.es
