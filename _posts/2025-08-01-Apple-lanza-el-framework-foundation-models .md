---
layout: post
title: Apple lanza el framework Foundation Models para desarrolladores
date: 2025-08-01 09:30:00 -0300
author: Miguel Barraza
category: noticias
tags: [ios, ia, Swift]
excerpt: Apple presentó en junio de 2025 el framework Foundation Models, que permite a desarrolladores usar los modelos de Apple Intelligence directamente en apps iOS/macOS, con ejecución local, offline y enfoque en privacidad.
---

Apple anunció en su evento WWDC 2025, celebrado del 9 al 13 de junio, el **Foundation Models framework**, una nueva herramienta que permite a los desarrolladores integrar capacidades de Apple Intelligence en sus aplicaciones. El sistema funciona completamente **en el dispositivo**, sin depender de la nube, preservando la privacidad del usuario, con solo tres líneas de código en Swift.

La herramienta proporciona acceso directo al modelo lingüístico **on-device de aproximadamente 3 000 millones de parámetros**, optimizado para ejecutar tareas como generación de texto, resumen, extracción de entidades y diálogo simple, con **inferencia gratuita y sin conexión**. Para desarrollos que requieran especialización, Apple ofrece un kit en Python que permite entrenar adaptadores (LoRA) compatibles con el framework.

## Beneficios destacados

- **Privacidad nativa y ejecución offline**: todo el procesamiento ocurre en el dispositivo, sin enviar datos a servidores externos.
- **Sin costos de inferencia ni infraestructura**: funciona sin necesidad de utilizar APIs externas ni configurar servidores.
- **Integración minimalista en Swift**: basta incluir la librería y escribir apenas tres líneas de código para activar funciones como generación guiada y tool calling.
- **Compatible con múltiples plataformas Apple**: funciona en iOS, iPadOS, macOS, watchOS y visionOS.

## Ejemplos en aplicaciones reales

- **Day One** ya implementó este framework para ofrecer sugerencias personalizadas de escritura sin exponer datos del usuario.
- La app **AllTrails** lo utiliza para recomendar rutas de senderismo en modo offline, con búsqueda en lenguaje natural.

## Innovaciones técnicas clave

- El modelo de texto está **cuantizado con 2 bits** utilizando técnicas como QAT o ASTC, optimizando el rendimiento y el espacio.
- Soporte para generación guiada, transmisión de respuestas y tool calling con estructuras avanzadas como sesiones de estado en conversaciones.
- Apple integró principios de **IA responsable**, incluyendo filtrado de contenido y evaluaciones de seguridad según región.

## ¿Por qué importa para desarrolladores?

- Permite crear aplicaciones inteligentes sin depender de servicios externos: ideal para educación, salud, productividad o experiencias offline.
- Refuerza el enfoque de Apple en la **privacidad por diseño**, uno de los pilares del ecosistema.
- Agiliza el desarrollo de funciones de IA sin necesidad de infraestructura especializada.

## Panorama y contexto en WWDC 2025

Durante el evento, Apple también presentó el nuevo lenguaje de diseño **Liquid Glass**, actualizaciones a iOS 26 (como llamadas con traducción en vivo y gestión de llamadas desconocidas), nuevos emojis personalizados (genmoji), mejoras en Visual Intelligence y la app Workout Buddy en watchOS. Si bien algunos analistas criticaron la falta de avances radicales en inteligencia artificial, destacaron que abrir Foundation Models a desarrolladores puede ser un cambio significativo para el ecosistema Apple.

## Conclusión

El framework Foundation Models marca un paso importante en el desarrollo de inteligencia artificial local y accesible. Para los desarrolladores del ecosistema Apple, representa una oportunidad para ofrecer funciones inteligentes con mayor control, privacidad y sin depender de infraestructuras costosas. Es una apuesta estratégica que puede transformar la experiencia en apps móviles y de escritorio.

## Glosario técnico

- **Inferencia local**: ejecución del modelo de IA directamente en el dispositivo del usuario.
- **3 000 millones de parámetros (~3 B)**: tamaño del modelo de lenguaje utilizado por Apple Intelligence para tareas de texto.
- **Cuantización (2 bits, QAT/ASTC)**: técnica para reducir el tamaño del modelo manteniendo su precisión.
- **Generación guiada (guided generation)**: el modelo sigue una plantilla o estructura definida al generar texto.
- **Tool calling**: capacidad de invocar funciones integradas desde el modelo.
- **Adapter fine-tuning (LoRA)**: técnica de ajuste del modelo mediante adaptadores ligeros para tareas específicas.

## Fuentes

1. Apple Newsroom – “Apple supercharges its tools and technologies for developers”  
   [https://www.apple.com/newsroom/2025/06/apple-supercharges-its-tools-and-technologies-for-developers/][]  
   Anuncio oficial del framework y su integración en Xcode 26.

2. Apple Machine Learning Blog – “Updates to Apple’s On‑Device and Server Foundation Language Models”  
   [https://machinelearning.apple.com/research/apple-foundation-models-2025-updates][]  
   Detalles técnicos sobre los modelos y cuantización.

3. TechCrunch – “Apple lets developers tap into its offline AI models”  
   [https://techcrunch.com/2025/06/09/apple-lets-developers-tap-into-its-offline-ai-models/][]  
   Apple permite a los desarrolladores aprovechar sus modelos de IA sin conexión.

4. Wired – “Apple Is Pushing AI Into More of Its Products—but Still Lacks a State‑of‑the‑Art Model”  
   https://www.wired.com/story/apple-wwdc-ai-announcements  
   Apple está incorporando IA a más productos, pero aún carece de un modelo de vanguardia.

5. Reuters – “Here is everything Apple announced at its annual developer conference”  
   [https://www.reuters.com/business/here-is-everything-apple-announced-its-annual-developer-conference-2025-06-09/][]  
   Resumen de los anuncios más relevantes del evento.
