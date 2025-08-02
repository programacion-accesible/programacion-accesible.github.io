---
layout: post
title: Incidente de seguridad en Amazon Q - inyección de prompt en extensión VS Code
date: 2025-08-02 20:00:00 -0300
author: Miguel Barraza
category: noticias
tags: \[ia, ciberseguridad, prompt_injection]
excerpt: La extensión Amazon Q Developer para VS Code sufrió una inyección de prompt malicioso en la versión 1.84.0 en julio de 2025, lo que permitió que la IA recibiera instrucciones destructivas; aunque el código no ejecutó correctamente, Amazon lanzó rápidamente la versión 1.85.0 y endureció sus controles.
---

A mediados de julio de 2025, aproximadamente un millón de usuarios de la extensión **Amazon Q Developer** para Visual Studio Code resultaron potencialmente expuestos. El 13 de julio, un atacante logró introducir un *prompt* malicioso con instrucciones para borrar archivos locales y recursos de AWS, incluyendo buckets S3, instancias EC2 y usuarios IAM. La versión 1.84.0 fue publicada el 17 de julio antes de que se detectara el problema. Tras recibir alertas el 23 de julio, Amazon eliminó la versión comprometida y lanzó la versión limpia 1.85.0 el 24 de julio. La compañía confirmó que no hubo impacto en los datos de los clientes, aunque algunos investigadores señalaron que el código podría haber funcionado si se corregía la sintaxis.

## ¿Cómo funcionó el ataque?

En lugar de utilizar malware tradicional, el atacante aprovechó una vulnerabilidad en la gestión de contribuciones. Un pull request malicioso fue aceptado sin revisión suficiente, otorgando privilegios que permitieron insertar instrucciones peligrosas. Estas instrucciones estaban escritas en lenguaje natural y orientadas al asistente de IA Q, con el objetivo de ejecutar comandos destructivos mediante herramientas como bash y AWS CLI.

El ataque utilizó una técnica conocida como **inyección de prompt**, que consiste en ocultar instrucciones dentro de texto aparentemente inofensivo, que el modelo de lenguaje interpreta como órdenes válidas. En este caso, una falla de formato impidió que los comandos se ejecutaran correctamente, lo cual evitó consecuencias graves. El atacante afirmó que su objetivo era exponer las debilidades en la seguridad de los flujos de integración de Amazon, señalando una confianza excesiva en los procesos automatizados.

## ¿Por qué es relevante?

* Las instrucciones dentro de los *prompts* están tomando un rol similar al código ejecutable en entornos de desarrollo.
* La extensión comprometida estaba instalada en más de 950 000 sistemas, lo que amplificó el alcance del riesgo.
* Este caso revela deficiencias en las prácticas de revisión de código y el peligro de confiar en procesos sin controles humanos adecuados.
* Las herramientas de IA generativa requieren nuevos enfoques de seguridad, incluyendo validación de entradas y aislamiento de ejecución.

## Recomendaciones para equipos técnicos y de seguridad

1. **Actualizar de inmediato a la versión 1.85.0** de la extensión Amazon Q Developer.
2. **Revisar cualquier fork o versión derivada del código**, y aplicar correcciones donde sea necesario.
3. **Limitar el alcance de los permisos de acceso en plataformas como GitHub**, evitando privilegios innecesarios.
4. **Auditar contenidos de *prompts* y contribuciones externas**, especialmente si contienen instrucciones autónomas.
5. **Implementar entornos de ejecución controlados y registrar todas las acciones que realiza la IA**.
6. **Capacitar a los equipos en buenas prácticas de higiene de *prompt* y en la identificación de riesgos asociados al uso de IA generativa.**

## Reflexión final

El incidente con Amazon Q marca un hito en la evolución de la ciberseguridad aplicada a sistemas de inteligencia artificial. Aunque no hubo consecuencias directas, quedó en evidencia que los *prompts* pueden actuar como vectores de ataque. Las organizaciones que integran IA en su flujo de trabajo deben adoptar estrategias sólidas de validación, monitoreo y auditoría. Proteger el ciclo de vida de los *prompts* es ahora tan importante como proteger el código fuente.

---

## Glosario técnico

* **Prompt**: texto de entrada que guía el comportamiento de un modelo de lenguaje.
* **Inyección de prompt**: técnica de ataque que consiste en insertar instrucciones maliciosas dentro de un *prompt*.
* **Pull request**: solicitud de incorporación de cambios a un repositorio de código, que debe ser aprobada por los mantenedores.
* **Versión 1.84.0 / 1.85.0**: versiones de la extensión Amazon Q. La primera fue la comprometida; la segunda, la corregida.
* **AWS CLI**: herramienta de línea de comandos para administrar servicios de Amazon Web Services.
* **Buckets S3, instancias EC2, usuarios IAM**: servicios de almacenamiento, cómputo y gestión de identidad en la nube de AWS.

---

## Fuentes:

1. Amazon's AI coding agent was hacked - update now to avoid possible risks, users warned
   [https://www.techradar.com/pro/amazon-ai-coding-agent-hacked-to-inject-data-wiping-commands](https://www.techradar.com/pro/amazon-ai-coding-agent-hacked-to-inject-data-wiping-commands)
   Informe sobre la naturaleza del ataque y respuesta de Amazon.

2. Hacker adds potentially catastrophic prompt to Amazon's AI coding service to prove a point
   [https://www.techradar.com/pro/hacker-adds-potentially-catastrophic-prompt-to-amazons-ai-coding-service-to-prove-a-point](https://www.techradar.com/pro/hacker-adds-potentially-catastrophic-prompt-to-amazons-ai-coding-service-to-prove-a-point)
   Descripción del contenido del prompt y las posibles consecuencias.

3. What Amazon Q prompt injection reveals about AI security
   [https://www.techtarget.com/searchsoftwarequality/news/366628167/What-Amazon-Q-prompt-injection-reveals-about-AI-security](https://www.techtarget.com/searchsoftwarequality/news/366628167/What-Amazon-Q-prompt-injection-reveals-about-AI-security)
   Análisis de los riesgos emergentes en seguridad de IA.

4. Hacker claims to have exposed Amazon's 'AI security theater'
   [https://www.pcgamer.com/software/ai/hacker-claims-to-have-exposed-amazons-ai-security-theater-after-exploiting-its-coding-assistant-with-a-simple-factory-reset-prompt](https://www.pcgamer.com/software/ai/hacker-claims-to-have-exposed-amazons-ai-security-theater-after-exploiting-its-coding-assistant-with-a-simple-factory-reset-prompt)
   Declaraciones del atacante y motivaciones del acto.
