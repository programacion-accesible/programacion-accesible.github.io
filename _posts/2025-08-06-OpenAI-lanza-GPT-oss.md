---
layout: post
title: OpenAI lanza GPT-oss - modelos abiertos, seguros y auditables
date: 2025-08-06 21:30:00 -0300
author: Miguel Barraza
category: noticias
tags: [gpt, ia, llm, open_source]
excerpt: OpenAI ha presentado GPT-oss, una familia de modelos de lenguaje con pesos abiertos bajo licencia Apache 2.0. Estos modelos fueron diseñados con un enfoque riguroso en seguridad y transparencia, y ya pueden ejecutarse localmente.
---

OpenAI ha lanzado oficialmente **GPT-oss**, una nueva familia de modelos de lenguaje con pesos abiertos, disponible bajo la licencia Apache 2.0. Se trata de la primera vez desde 2019, con GPT-2, que la organización libera públicamente modelos con parámetros descargables, lo que marca un regreso a sus raíces de investigación abierta.

Esta decisión permite a desarrolladores, instituciones educativas, startups y comunidades tecnológicas acceder, adaptar y auditar modelos avanzados sin depender de plataformas cerradas. La iniciativa busca reforzar un ecosistema de inteligencia artificial más inclusivo, seguro y responsable.

## ¿Qué incluye la familia GPT-oss?

La familia se compone de dos modelos principales:

- **gpt-oss-120B**: modelo con arquitectura *Mixture-of-Experts*, compuesto por 117 mil millones de parámetros, de los cuales aproximadamente 5.1 mil millones se activan por token. Puede ejecutarse en una sola GPU con 80 GB de memoria.
- **gpt-oss-20B**: versión optimizada para equipos más modestos, con cerca de 21 mil millones de parámetros y un consumo de memoria compatible con laptops de 16 GB de RAM.

Ambos modelos permiten contextos de hasta 128 000 tokens, integran mecanismos de razonamiento estructurado tipo *chain-of-thought*, y son capaces de utilizar herramientas externas para tareas como navegación web o ejecución de código. También generan salidas estructuradas, lo que los hace útiles para agentes inteligentes o aplicaciones con múltiples pasos de razonamiento.

## Evaluación de seguridad y riesgos

Antes de su publicación, OpenAI sometió a los modelos GPT-oss a pruebas de seguridad rigurosas bajo su propio marco de evaluación, conocido como *Preparedness Framework*. Este proceso incluyó:

- Análisis del comportamiento por defecto del modelo, sin afinación adicional, frente a riesgos potenciales como generación de información biológica o ciberataques.
- Pruebas adversariales mediante *fine-tuning malicioso*, con el objetivo de maximizar intencionalmente su capacidad para realizar tareas de alto riesgo.

Los resultados demostraron que, incluso tras estos ajustes extremos, los modelos **no alcanzan niveles de riesgo alto** en áreas sensibles como biotecnología, ciberseguridad o auto-mejora. La evaluación fue revisada por expertos independientes, lo que respalda la decisión de OpenAI de liberar estos modelos al público.

Este enfoque representa un precedente en cuanto a transparencia y responsabilidad en la publicación de modelos avanzados de IA, y refuerza la confianza en el uso de estas tecnologías de forma ética y controlada.

## Disponibilidad y uso

GPT-oss ya está disponible para ejecución local en múltiples plataformas. Por ejemplo, puede utilizarse directamente mediante **Ollama**, una herramienta que permite correr modelos en computadoras personales, facilitando su integración sin necesidad de servidores en la nube.

Con comandos simples, los usuarios pueden descargar y comenzar a usar tanto el modelo de 20B como el de 120B, lo que abre nuevas posibilidades para desarrolladores, educadores y científicos de datos.

Accede a los modelos aquí:  
[https://ollama.com/library/gpt-oss][]

## Casos de uso destacados

- **Asistentes sin conexión**: ejecución local del modelo gpt-oss-20B en dispositivos móviles o portátiles.
- **Aplicaciones empresariales**: agentes inteligentes capaces de tomar decisiones complejas utilizando gpt-oss-120B.
- **Investigación académica**: modelos auditables y adaptables para estudios en inteligencia artificial.
- **Sectores regulados**: despliegue de IA con control total de datos y parámetros, sin dependencia de proveedores externos.

## Conclusión

Con GPT-oss, OpenAI da un paso decisivo hacia una inteligencia artificial más abierta, segura y libre. La disponibilidad de estos modelos bajo licencia permisiva, sumada a las evaluaciones de seguridad rigurosas, permite avanzar hacia una innovación más ética y descentralizada. Esta iniciativa no solo fortalece el ecosistema técnico, sino que también promueve la colaboración y la soberanía tecnológica.

## Glosario técnico

- **Modelo de lenguaje**: sistema de inteligencia artificial diseñado para comprender y generar texto de forma coherente.
- **Pesos abiertos**: archivos que contienen los parámetros del modelo, disponibles para descarga, uso y modificación.
- **Mixture-of-Experts**: arquitectura que activa dinámicamente diferentes partes del modelo según la tarea.
- **Token**: unidad básica de texto procesada por el modelo, que puede ser una palabra o fragmento.
- **Chain-of-thought**: técnica que permite al modelo razonar paso a paso antes de dar una respuesta.
- **Fine-tuning malicioso**: ajuste del modelo con el objetivo de amplificar sus capacidades en tareas sensibles o peligrosas.
- **Preparedness Framework**: metodología de OpenAI para evaluar el riesgo de modelos avanzados antes de su publicación.
- **Ollama**: herramienta que permite ejecutar modelos de lenguaje de manera local en distintos dispositivos.

## Fuentes

1. Introducing GPT-oss  
[https://openai.com/index/introducing-gpt-oss][]  
Anuncio oficial de OpenAI sobre la nueva familia de modelos abiertos.

2. GPT-oss Model Card  
[https://openai.com/index/gpt-oss-model-card][]  
Documentación técnica detallada de los modelos gpt-oss.

3. Estimating Worst-Case Frontier Risks  
[https://arxiv.org/abs/2508.03153][]  
Estudio sobre pruebas de seguridad adversarial aplicadas a los modelos.

4. GPT-oss en Ollama  
[https://ollama.com/library/gpt-oss][]  
Acceso directo a los modelos desde la plataforma Ollama.
