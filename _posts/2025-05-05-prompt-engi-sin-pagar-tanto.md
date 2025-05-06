---
layout: post
title:  "Prompt Engineering, o como pagar 300$ para saber decir "Gracias" a un agente LLM"
date:   2025-05-05
categories: [IA, humor]
tags: [prompt engineering, LLMs, matemáticas, crítica social]
seo:
  meta_description: "Descubre cómo una simple función 𝒫(Ins, En, Salida) desmonta los caros cursos de prompt engineering. Aprende a comunicarte con IAs sin perder el humor (ni tu dinero)."
  meta_keywords: "prompt engineering, función de prompts, crítica a cursos de IA, humor tecnológico, LLMs, comunicación con IA"
---

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-fun.png' | relative_url }}" 
       alt="Problemas de comunicacion con LLM" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Comunicarse con los LLM, es sencillo, sin necesidad de cursos costosos
  </span>
</p>

<p style="text-align: justify; text-justify:inner-word;">
	Entre anuncios de cursos que prometen <strong>"dominar los LLMs por solo $300"</strong>, ideas que solo llegan cuando estas dormido, y un pizarron lleno de garabatos, descubrí una verdad incómoda: el <strong>prompt engineering</strong> es solo <strong>saber comunicarse</strong>... pero con máquinas que a veces entienden "haz un resumen" como "escribe una ópera sobre papas". Así nació mi misión: encontrar la fórmula que unifique esta jungla de técnicas, ya que para ser honestos, me resulta como minimo absurdo, tener que pagar tanta cantidad de dinero para algo que se supone traemos por defecto.
	<br>
	<strong> Disclaimer: Los prompt y sus resultados han sido realizados en DeepSeek-Web (no R1) y con calls al API de ChatGPT 3.5 </strong>
</p>

### 🎓 Las 15+1 Técnicas Traducidas a "Humano"
<p style="text-align: justify; text-justify:inner-word;">
<strong>Lo que enseñan los cursos:</strong> Nombres pomposos como "few-shot learning/one-shot/chain of thoughts".<br>
<strong>Lo que realmente son:</strong>  
</p

1. **One-shot**  
   - *Curso*: "Añade un vector de entrenamiento, con input-output, para que el modelo lo use de ejemplo".  
   - *Humano*: <i>"CALCULA el IGV de estos montos, sabiendo que el IGV se calcula asi"</i>.
   
<p align="center">
  <img src="{{ '/assets/images/posts/prompt-one-shot.png' | relative_url }}" 
       alt="Prompt en one shot" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Prompt utilizando un ejemplo, para enseñar como se debe realizar la tarea
  </span>
</p>

2. **Contexto**  
   - *Curso*: "Añade metadata para alinear el espacio vectorial".  
   - *Humano*: <i>"BUSCAME el abrigo, el ROJO, no el azul que parece sábana fantasma"</i>.

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-context.png' | relative_url }}" 
       alt="Prompt contextual" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Como se ve un prompt utilizando tecnica "sofisticada" de contexto
  </span>
</p>

3. **Cadena de pensamiento**  
   - *Curso*: "Descomposición recursiva de intenciones semánticas".  
   - *Humano*: <i>"CORTA el pelo así... no, así no... ¡como en la foto de Pinterest!"</i>. 

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-chot-1.png' | relative_url }}" 
       alt="Prompt cadena de pensamiento" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Primer prompt o inicio de la "Cadena de pensamiento".
  </span>
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-chot-2.png' | relative_url }}" 
       alt="Prompt cadena de pensamiento 2" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Encadenamiento del primer prompt de la "Cadena de pensamiento".
  </span>
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-chot-3.png' | relative_url }}" 
       alt="Prompt cadena de pensamiento 3" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Refinamiento final de "Cadena de pensamiento".
  </span>
</p>

<p style="text-align: justify; text-justify:inner-word;">
	Se entiende que no se explica de forma extensiva todas las tecnicas involucradas y de caracter popular en el Prompt engineering, sin embargo, solo basta una pequeña busqueda para entender que todas tienen patrones de diseño, bastante parecidas, y resulta conveniente nombrar esta seccion "15+1", puesto que ese +1, no es mas que una tecnica llamada "GraphPrompt", que posee en su haber un formalismo mas elegante basado en grafos, vectores y patrones de homomorfismos, de tal forma que profundizaremos en esta tecnica en una entrada futura del blog.
</p>

### 🧮 La Función P: Una propuesta de generalizacion
<p style="text-align: justify; text-justify:inner-word;">
<strong>Ecuación salvadora:</strong><br>
\[
\mathscr{P}\Big(\mathtt{Ins} \mid \mathcal{C}_{\text{Ins}} + \varepsilon,\ \mathcal{D}_{\text{in}},\ \mathtt{Sal} \mid \mathcal{C}_{\text{Sal}}\Big) \to \mathbb{R}
\]
 
<strong>Donde:</strong><br>
- **𝒫** (Función de Prompt):  
  *Proceso que transforma entradas en respuestas del agente IA*  
  - Ejemplo: `"Traduce esto" → "Bonjour"`

- **Ins** (Instrucción):  
  *Directriz principal para la IA*  
  - Ejemplo: `"Resume este texto"`

- **𝒞<sub>Ins</sub>** (Contexto de Instrucción):  
  *Marco de referencia para la instrucción*  
  - Si no existe: `𝒞<sub>Ins</sub> = 0`  
  - Ejemplo: `"Como experto en biología..."`

- **ε** (Ruido/Aleatoriedad):  
  *Ambigüedad no intencional en la instrucción*  
  - Ejemplo: `"Haz algo creativo"` (¿Qué es "creativo" para la IA?)

- **𝒟<sub>in</sub>** (Datos de Entrada):  
  *Información proporcionada a la IA*  
  - Ejemplo: `Ejemplos, conceptos o datos crudos`

- **Sal** (Salida Esperada):  
  *Formato/estructura deseada para la respuesta*  
  - Ejemplo: `"En formato de tabla"`

- **𝒞<sub>Sal</sub>** (Contexto de Salida):  
  *Restricciones adicionales para la respuesta*  
  - Ejemplo: `"Usa analogías de videojuegos"`

- **ℝ** (Respuesta):  
  *Output generado por la IA*  
  - Puede ser: `Texto, código, imágenes, etc.`
<br>

<p style="text-align: justify; text-justify:inner-word;">
	Pero no nos quedemos en palabras, usemos esta funcion, para obtener algunos ejemplos, similares a los prompt bajo tecnicas de lenguaje natural.
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-funcion-one.png' | relative_url }}" 
       alt="Prompt one shot usando funcion P" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Prompt "One-Shot" usando funcion P, como estructura.
  </span>
</p>
<br>

<p style="text-align: justify; text-justify:inner-word;">
	De este modo y bajo una comparativa rapida, podemos obtener lo siguiente en cuanto a velocidades de respuesta entre prompts.
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/comparativa-natural-funcion.png' | relative_url }}" 
       alt="Funcion P vs Lenguaje Natural" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Diferencia en tiempos de respuesta, Natural vs Funcion P, basado en calls de API de ChatGPT 3.5, medido en ms.
  </span>
</p>

### 💸 ¿Por Qué los Cursos en "Prompt Engineering" de $300 Son un Timo?
<p style="text-align: justify; text-justify:inner-word;">
<strong>Para explicarlo de forma bastante sencillita:</strong><br>
- Ellos venden: \( \text{Diploma} = 300\$ \times \text{FOMO} \).<br>
- Tú necesitas: \( \text{Sentido común} + \text{Paciencia} \).  

<strong>Ejemplo real:</strong>  
Un "experto" cobra $300 por enseñar... a usar emojis en prompts y a decir "gracias" y de hecho es por eso que te preparan no solo en ser bueno con los prompts, sino en crear productos basados en los mismos, cosa que... Sorpresa, tambien puedes aprender y construir, usando los mismos prompts. 😱  
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/fraud-diploma.png' | relative_url }}" 
       alt="Anuncio de curso con precio inflado y certificado inútil" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Invertir tu tiempo en busqueda, vale la pena, para no terminar asi.
  </span>
</p>

### 🚀 Conclusión: Tú Ya Sabías Todo Esto
> - **Dominar prompts** = Saber explicarte + probar iterativamente.  
> - **Los cursos caros** son como NFT: pura especulación.  
> - **La funcion P** util para quienes piensen en terminos mas tecnicos.  

<p align="center">
  <img src="{{ '/assets/images/posts/personas-riendo.png' | relative_url }}" 
       alt="Personas escribiendo prompt con propositos" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Felicidad por obtener resultados con proposito, bajo tu propio pensamiento.
  </span>
</p>

### 📚 Recursos Reales (y Gratis)
- [Guía de Prompting](https://www.promptingguide.ai/es) - Lo que los cursos copian y quien le debo este research.  
- <strong>GraphPrompt: Unifying Pre-Training and Downstream Tasks for Graph Neural Networks</strong) - <italic>Zemin Liu, Xingtong Yu, Yuan Fang, Xinming Zhang</italic>

Te ha parecido interesante, ¿Has pagado por un curso como estos? de ser asi, o conocer a alguien que lo haya hecho, compartelo y no olvides dejar un comentario, de este modo podemos hacer que la funcion P, sea cada vez mas "Poderosa".

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/C1C41DTDL)