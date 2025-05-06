---
layout: post
title: "Prompt Engineering: La Fórmula Matemática que los Cursos de $500 No Quieren que Conozcas"
date: 2025-05-05 00:00:00 +0000
categories: [IA, humor]
tags: [prompt engineering, LLMs, matemáticas, crítica social]
seo:
  meta_description: "Descubre cómo una simple función 𝒫(Ins, En, Salida) desmonta los caros cursos de prompt engineering."
  meta_keywords: "prompt engineering, función de prompts, crítica a cursos de IA, humor tecnológico"
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

###Las 15+1 Técnicas Traducidas a "Humano"
<p style="text-align: justify; text-justify:inner-word;">
<strong>Lo que enseñan los cursos:</strong> Nombres pomposos como "few-shot learning/one-shot/chain of thoughts".<br>
<strong>Lo que realmente son:</strong>  
</p
<br>
<strong>1. One-shot</strong><br>
   <strong>-Curso</strong>: "Añade un vector de entrenamiento, con input-output, para que el modelo lo use de ejemplo".<br>  
   <strong>-Humano</strong>: <italic>"CALCULA el IGV de estos montos, sabiendo que el IGV se calcula asi"</italic>.
   
<p align="center">
  <img src="{{ '/assets/images/posts/prompt-one-shot.png' | relative_url }}" 
       alt="Prompt en one shot" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Prompt utilizando un ejemplo, para enseñar como se debe realizar la tarea
  </span>
</p>

<strong>2. Contexto</strong><br>
   <strong>Curso</strong>: "Añade metadata para alinear el espacio vectorial".<br>
   <strong>Humano</strong>: <italic>"BUSCAME el abrigo, el ROJO, no el azul que parece sábana fantasma"</italic>.

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-context.png' | relative_url }}" 
       alt="Prompt contextual" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Como se ve un prompt utilizando tecnica "sofisticada" de contexto
  </span>
</p>

<strong>3. Cadena de pensamiento</strong><br> 
   <strong>Curso</strong>: "Descomposición recursiva de intenciones semánticas".<br>
   <strong>Humano</strong>: <italic>"CORTA el pelo así... no, así no... ¡como en la foto de Pinterest!"</italic>. 

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
	Se entiende que <strong>no se explica de forma extensiva todas las tecnicas involucradas y de caracter popular en el Prompt engineering</strong>, sin embargo, solo basta una pequeña busqueda para entender que todas tienen patrones de diseño, bastante parecidas, y resulta conveniente nombrar esta seccion "15+1", puesto que ese +1, no es mas que una tecnica llamada <strong>"GraphPrompt"</strong>, que posee en su haber un formalismo mas elegante basado en grafos, vectores y patrones de homomorfismos, de tal forma que profundizaremos en esta tecnica en una entrada futura del blog.
</p>

###La Función P: Una propuesta de generalizacion
<p style="text-align: justify; text-justify:inner-word;">
<strong>Ecuación salvadora:</strong><br>
\[
\mathscr{P}\Big(\mathtt{Ins} \mid \mathcal{C}_{\text{Ins}} + \varepsilon,\ \mathcal{D}_{\text{in}},\ \mathtt{Sal} \mid \mathcal{C}_{\text{Sal}}\Big) \to \mathbb{R}
\]
 
<strong>Donde:</strong><br>
- **𝒫** (Función de Prompt):  <br>
  *Proceso que transforma entradas en respuestas del agente IA*  <br>
  - Ejemplo: `"Traduce esto" → "Bonjour"`<br>

- **Ins** (Instrucción):  <br>
  *Directriz principal para la IA*  <br>
  - Ejemplo: `"Resume este texto"`<br>

- **𝒞<sub>Ins</sub>** (Contexto de Instrucción):  <br>
  *Marco de referencia para la instrucción*  <br>
  - Si no existe: `𝒞<sub>Ins</sub> = 0`  <br>
  - Ejemplo: `"Como experto en biología..."`<br>

- **ε** (Ruido/Aleatoriedad):  <br>
  *Ambigüedad no intencional en la instrucción*  <br>
  - Ejemplo: `"Haz algo creativo"` (¿Qué es "creativo" para la IA?)<br>

- **𝒟<sub>in</sub>** (Datos de Entrada):  <br>
  *Información proporcionada a la IA*  <br>
  - Ejemplo: `Ejemplos, conceptos o datos crudos`<br>

- **Sal** (Salida Esperada):  <br>
  *Formato/estructura deseada para la respuesta*  <br>
  - Ejemplo: `"En formato de tabla"`<br>

- **𝒞<sub>Sal</sub>** (Contexto de Salida): <br> 
  *Restricciones adicionales para la respuesta*  <br>
  - Ejemplo: `"Usa analogías de videojuegos"`<br>

- **ℝ** (Respuesta):  <br>
  *Output generado por la IA*  <br>
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

###¿Por Qué los Cursos en "Prompt Engineering" de $300 Son un Timo?
<p style="text-align: justify; text-justify:inner-word;">
<strong>Para explicarlo de forma bastante sencillita:</strong><br>
- Ellos venden: \( \text{Diploma} = 300\$ \times \text{FOMO} \).<br>
- Tú necesitas: \( \text{Sentido común} + \text{Paciencia} \).  <br>

<strong>Ejemplo real:</strong>  <br>
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

###Conclusión: Tú Ya Sabías Todo Esto
> <strong>Dominar prompts</strong> = Saber explicarte + probar iterativamente.  
> <strong>Los cursos caros son como NFT</strong>: pura especulación.  
> <strong>La funcion P</strong>: util para quienes piensen en terminos mas tecnicos.  

<p align="center">
  <img src="{{ '/assets/images/posts/personas-riendo.png' | relative_url }}" 
       alt="Personas escribiendo prompt con propositos" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Felicidad por obtener resultados con proposito, bajo tu propio pensamiento.
  </span>
</p>

###Recursos Reales (y Gratis)
- (https://www.promptingguide.ai/es) - Lo que los cursos copian y quien le debo este research.  <br>
- <strong>GraphPrompt: Unifying Pre-Training and Downstream Tasks for Graph Neural Networks</strong> - <italic>Zemin Liu, Xingtong Yu, Yuan Fang, Xinming Zhang</italic><br>

Te ha parecido interesante, ¿Has pagado por un curso como estos? de ser asi, o conocer a alguien que lo haya hecho, compartelo y no olvides dejar un comentario, de este modo podemos hacer que la funcion P, sea cada vez mas "Poderosa".

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/C1C41DTDL2)