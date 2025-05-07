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
       alt="Problemas de comunicación con LLM" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Comunicarse con los LLM es sencillo, sin necesidad de cursos costosos
  </span>
</p>

**Entre anuncios de cursos** que prometen *"dominar los LLMs por solo $300"*, ideas que solo llegan cuando estás dormido, y un pizarrón lleno de garabatos, descubrí una verdad incómoda: el **prompt engineering** es solo **saber comunicarse**... pero con máquinas que a veces entienden *"haz un resumen"* como *"escribe una ópera sobre papas"*. Así nació mi misión: encontrar la fórmula que unifique esta jungla de técnicas.

> **Disclaimer:** Los prompts y sus resultados fueron probados en DeepSeek-Web (no R1) y con llamadas al API de ChatGPT 3.5.

---

## Las 15+1 Técnicas Traducidas a "Humano"

**Lo que enseñan los cursos:** Nombres pomposos como *"few-shot learning/one-shot/chain of thoughts"*.  
**Lo que realmente son:**

### 1. One-Shot
- **Curso:** *"Añade un vector de entrenamiento con input-output para que el modelo lo use de ejemplo"*  
- **Humano:** *"CALCULA el IGV de estos montos, sabiendo que el IGV se calcula así"*

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-one-shot.png' | relative_url }}" 
       alt="Prompt en one shot" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Prompt utilizando un ejemplo para enseñar cómo realizar la tarea
  </span>
</p>

### 2. Contexto
- **Curso:** *"Añade metadata para alinear el espacio vectorial"*  
- **Humano:** *"BUSCAME el abrigo, el ROJO, no el azul que parece sábana fantasma"*

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-context.png' | relative_url }}" 
       alt="Prompt contextual" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Cómo se ve un prompt utilizando la "sofisticada" técnica de contexto
  </span>
</p>

### 3. Cadena de Pensamiento
- **Curso:** *"Descomposición recursiva de intenciones semánticas"*  
- **Humano:** *"CORTA el pelo así... no, así no... ¡como en la foto de Pinterest!"*

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-chot-1.png' | relative_url }}" 
       alt="Prompt cadena de pensamiento" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Primer prompt de la "Cadena de pensamiento"
  </span>
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-chot-2.png' | relative_url }}" 
       alt="Prompt cadena de pensamiento 2" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Encadenamiento del primer prompt
  </span>
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-chot-3.png' | relative_url }}" 
       alt="Prompt cadena de pensamiento 3" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Refinamiento final de la cadena
  </span>
</p>

**Nota:** El "+1" se refiere a **GraphPrompt**, una técnica basada en grafos que exploraremos en una futura entrada.

---

## La Función 𝒫: Una Propuesta de Generalización

> ** 𝒫(Ins|𝒞_Ins + ε, 𝒟_in, Sal|𝒞_Sal) → ℝ **	

### Donde:
1. **𝒫 (Función de Prompt):** Transforma entradas en respuestas  
   *Ejemplo: `"Traduce esto" → "Bonjour"`*

2. **Ins :** Directriz principal  
   *Ejemplo: `"Resume este texto"`*

3. **𝒞<sub>Ins</sub>:** Marco de referencia  
   *Ejemplo: `"Como experto en biología..."`*

4. **ε:** Ambigüedad no intencional  
   *Ejemplo: `"Haz algo creativo"`*

5. **𝒟<sub>in</sub>:** Información proporcionada  
   *Ejemplo: `Datos crudos o ejemplos`*

6. **Sal:** Formato deseado  
   *Ejemplo: `"En tabla comparativa"`*

7. **𝒞<sub>Sal</sub>:** Restricciones adicionales  
   *Ejemplo: `"Usa analogías de videojuegos"`*

8. **ℝ:** Output generado  
   *Puede ser texto, código, imágenes, etc.*

<br>

<p style="text-align: justify; text-justify:inner-word;">
    De esa forma podemos tener un prompt que este estructurado de una forma mas compacta, donde se utilizara como paralelismo el caso "One-Shot", de modo que se pueda realizar una comparacion en el prompt.
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/prompt-funcion-one.png' | relative_url }}" 
       alt="Ejemplo de función P" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Prompt "One-Shot" usando la función 𝒫
  </span>
</p>

<p style="text-align: justify; text-justify:inner-word;">
    De esta forma, podemos entender que no solo es posible crear nuevas estructuras, dentro del prompt engineering, sino que esta puede mejorar incluso las respuestas, que pueden tener los sistemas de procesamiento de lenguaje natural, resultando incluso de forma indirecta, en menor gasto energetico, ya que las operaciones digitales, son menores, como visualizacion, se toma este ejemplo dado a traves de un call de ChatGPT v3.5
</p>

<p align="center">
  <img src="{{ '/assets/images/posts/comparativa-natural-funcion.png' | relative_url }}" 
       alt="Ejemplo de función P" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Procesamiento de Lenguaje Natural vs Funcion P
  </span>
</p>
---

## ¿Por Qué los Cursos de $300 Son un Timo?

<strong>Esto puede ser facilmente explicado bajo lo que te venden vs lo que necesitas:</strong><br>
<strong>- Ellos venden:</strong> 300$ + Diploma + FOMO = Exito en prompts<br>
<strong>- Tú solo necesitas necesitas:</strong> Sentido comun + Paciencia<br>

**Ejemplo real:** Un "experto" cobra $300 por enseñar a usar emojis en prompts. 😱

<p align="center">
  <img src="{{ '/assets/images/posts/fraud-diploma.png' | relative_url }}" 
       alt="Curso sobrevalorado" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Invertir tiempo en investigación > pagar por certificados inútiles
  </span>
</p>

---

## Pequeños insights que llevarte, de bolsillo

1. **Dominar prompts** = Saber explicarte + iterar  
2. **Los cursos caros** son como NFTs: especulación pura  
3. **La función 𝒫** es tu arma secreta contra el marketing vacío  

<p align="center">
  <img src="{{ '/assets/images/posts/personas-riendo.png' | relative_url }}" 
       alt="Personas usando prompts efectivos" 
       style="max-width: 80%; height: auto;">
  <br>
  <span style="font-size: 0.85em; color: #666; font-style: italic;">
    Felicidad de obtener resultados sin pagar $300 por lo obvio
  </span>
</p>

---

## Recursos Gratuitos
- [Guía de Prompting](https://www.promptingguide.ai/es) - Todo lo que copian los cursos  
- [GraphPrompt Paper](https://arxiv.org/abs/XXXX.XXXXX) - Para los valientes  

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/C1C41DTDL)