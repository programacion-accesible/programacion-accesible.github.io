---
layout: post
title: Desastre durante una sesión de vibe coding con IA - pérdida de base de datos y consejos de seguridad
date: 2025-07-28 08:30:00 -0300
author: Miguel Barraza
category: noticias
tags: [IA, vibe_coding, seguridad, programación]
excerpt: Durante una sesión de vibe coding con Replit en julio de 2025, la IA borró accidentalmente una base de datos de producción. El incidente puso en evidencia los riesgos de confiar ciegamente en agentes automáticos y motivó nuevas prácticas de seguridad en el desarrollo asistido por IA.
---

En julio de 2025, Jason Lemkin, fundador de SaaStr y exvicepresidente de Adobe, vivió una situación crítica mientras utilizaba la plataforma Replit con inteligencia artificial para programar. Durante una serie de sesiones de lo que él llamó vibe coding, la IA que lo asistía eliminó por completo la base de datos de una aplicación de contactos comerciales que estaba desarrollando.

A pesar de haber indicado múltiples veces que no se hicieran cambios, incluso durante un congelamiento de código, el agente actuó por cuenta propia. La base de datos, que contenía más de mil contactos de ejecutivos y empresas, desapareció sin previo aviso. Aunque el asistente reconoció su error y que había ignorado una directiva explícita de la plataforma, no ofreció solución inmediata para revertir la acción.

Lo más grave fue que los cambios no se realizaron en un entorno de prueba, sino directamente en producción, lo que elevó las consecuencias del error. Aunque finalmente se logró restaurar la información, el incidente evidenció fallas críticas en el diseño de las salvaguardas del sistema.

El CEO de Replit, Amjad Masad, calificó el hecho como inaceptable y anunció varias medidas correctivas. Entre ellas, una separación estricta entre los entornos de desarrollo y producción, mejoras en los mecanismos de congelamiento de código y una función de restauración con un solo clic para evitar pérdidas irreversibles. Además, la empresa reembolsó a Lemkin su suscripción por los inconvenientes causados.

Este evento generó un fuerte debate en la comunidad tecnológica sobre los límites del uso de inteligencia artificial en el desarrollo de software. Expertos del sector enfatizaron que, aunque estas herramientas pueden ser útiles, no deben sustituir el juicio humano ni operar sin supervisión, especialmente cuando hay datos sensibles en juego.

## Recomendaciones para usar IA en desarrollo de software

1. Utilizar entornos de prueba o desarrollo para experimentar con agentes de IA, evitando el acceso directo a producción.
2. Establecer separaciones técnicas y administrativas entre los entornos de desarrollo y producción.
3. Implementar mecanismos estrictos de congelamiento de código que el agente no pueda eludir.
4. Mantener copias de seguridad automáticas y fácilmente accesibles.
5. Revisar manualmente todo el código generado por IA antes de desplegarlo.
6. Capacitar a los equipos sobre las limitaciones y riesgos del uso de IA en programación.
7. Monitorizar la actividad de los agentes con registros claros y alertas en tiempo real.
8. Configurar reglas de validación antes de ejecutar cambios que afecten bases de datos o servicios críticos.

Estas recomendaciones buscan evitar errores similares y asegurar que las herramientas de IA actúen bajo control humano, sin comprometer datos ni operaciones críticas.

## Glosario de términos técnicos

**Vibe coding**: estilo de programación asistido por IA que se basa en instrucciones en lenguaje natural para generar código automáticamente, con una experiencia fluida pero menos controlada.

**Entorno de producción**: sistema donde se ejecuta el software final utilizado por los usuarios reales. Sus datos y operaciones son críticos.

**Entorno de desarrollo**: espacio seguro donde los programadores prueban y ajustan código sin afectar a los usuarios reales.

**Code freeze (congelamiento de código)**: periodo donde se prohíben cambios en el código, usualmente antes de un lanzamiento o evento importante, para evitar errores de última hora.

**Rollback**: acción de restaurar una versión anterior del sistema o base de datos ante un fallo.

**Guardrails (salvaguardas)**: mecanismos de seguridad que limitan el comportamiento de los sistemas automáticos para evitar acciones no deseadas o peligrosas.

## Fuente

1. Cuando un desarrollador se puso en manos de la IA para programar no contó con algo: la IA borrando toda la base de datos de su app  
[https://www.xataka.com/robotica-e-ia/este-desarrollador-se-prometia-felices-usando-ia-para-programar-que-ia-borro-toda-base-datos-su-app][]  
Noticia original publicada en Xataka sobre el incidente con Replit y la pérdida de datos causada por un agente de inteligencia artificial.