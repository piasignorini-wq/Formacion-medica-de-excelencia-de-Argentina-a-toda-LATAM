# Proyecto: Difusión de Cursos Médicos en LATAM mediante Técnicas de Prompting

## 📌 Descripción
Este proyecto se desarrolla en el marco del curso de *Prompt Engineering*.  
El objetivo es diseñar y aplicar diferentes técnicas de prompting (**zero-shot, one-shot y few-shot**) para resolver un caso práctico de difusión de cursos médicos en Latinoamérica (LATAM).

Los objetivos específicos fueron:  
1. Relevar asociaciones médicas en LATAM con datos de contacto y autoridades.  
2. Identificar temáticas médicas relevantes a nivel local y regional.  
3. Relevar noticias de actualidad en salud que sean de interés para profesionales médicos.  
4. Generar un manual de imagen institucional con identidad visual cercana a los públicos de LATAM.  

---

## 🛠️ Metodología
Se aplicaron diferentes técnicas de prompting según la necesidad de cada objetivo:

- **Asociaciones médicas:** One-shot prompting  
- **Temáticas médicas relevantes:** Few-shot prompting  
- **Noticias de actualidad:** Few-shot prompting  
- **Manual de imagen:** Zero-shot prompting  

---

## 📂 Estructura del Repositorio

| Archivo | Descripción |
|---------|------------|
| [README.md](README.md) | Explicación general del proyecto |
| [prompts.md](prompts.md) | Compilado de todos los prompts utilizados |
| [asociaciones.py](asociaciones.py) | Ejemplo de código en Python con un prompt (One-shot) |
| [tematicas.md](tematicas.md) | Ejemplos de prompts y salidas esperadas para temáticas médicas (Few-shot) |
| [noticias.md](noticias.md) | Ejemplos de prompts y salidas esperadas para noticias de salud (Few-shot) |
| [manual-imagen.md](manual-imagen.md) | Prompt para generación creativa del manual de imagen (Zero-shot) |

---

## 💻 Ejemplo de Código
Se utilizó la librería oficial de OpenAI para ejecutar los prompts.  
Ejemplo para generar un listado de asociaciones médicas en Brasil (One-shot prompting):

```python
from openai import OpenAI

client = OpenAI()

prompt = """
Dado el siguiente formato de ejemplo:  
"Asociación Médica Argentina | contacto@ama.org.ar | Presidente: Dr. Juan Pérez"  

Genera un listado con al menos 5 asociaciones médicas de Brasil siguiendo exactamente el mismo formato.
"""

response = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[{"role": "user", "content": prompt}]
)

print(response.choices[0].message.content)
