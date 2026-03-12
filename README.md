# Pre-entrega-2-Fast-prompting-POC

**Introducción**

**Nombre del proyecto**: Optimización de UX Conversacional


**Presentación del problema a abordar**:  Las Fintech en Colombia enfrentan una alta demanda de consultas sobre productos financieros (créditos, billeteras digitales, transferencias) que saturan los canales de atención humana, generando tiempos de espera prolongados y fricción en la experiencia de usuario (enfocado en el diseño de contenido).Es necesario implementar un agente de servicio al cliente basado en modelos de lenguaje (LLM) que actúe como primer nivel de soporte. Este agente no solo responderá dudas técnicas, sino que mantendrá el tono de voz de la marca (cercano pero profesional) y asistirá en la resolución de problemas comunes mediante el uso de prompts estructurados.


**Desarrollo de la solución**: Implementar los prompts que podrán usar los agentes de servicio, para agilizar sus respuestas a estas solicitudes basado en modelos de lenguaje (LLM) que actúen como primer nivel de soporte. 

**Justificación de la viabilidad del proyecto**: La implementación de este sistema de asistencia basado en IA puede ser escalable porque: 


Con la actualización del prompt, en esta segunda entrega, el sistema utiliza una estructura de 5 niveles (contexto, objetivo, reglas, formato y ejemplo) lo que garantiza menos alucinaciones con un formato predefinido de respuesta. Además de la alineación de marca.
El tiempo de implementación es más rápido y las iteraciones requieren de menos equipo técnico al tener cambios directamente en el prompt, permitiendo además una actualización en tiempo real.
La validación de su efectividad puede ser darse de manera continua y con diferentes KPI, por ejemplo:
Reducción de un 20-30% en escalamientos para intents con resolución en primer contacto.  
A través de un test A/B podremos hacer validaciones de tiempos y satisfacción de respuesta, incluso medir la eficiencia de dos tipos de prompt: uno con un lenguaje coloquial y otro más técnico. 
Respecto al prompt de imagen a texto: reducir la carga cognitiva puede disminuir los errores humanos en las transacciones.

**Objetivos**

General: Optimizar la experiencia de usuario (UX) en los canales de atención de una Fintech en Colombia mediante la implementación de un agente conversacional basado en LLM que reduzca la fricción en consultas financieras recurrentes.


**Específicos**:
Diseñar un prompt maestro estructurado que mantenga la consistencia en el tono de voz de la marca (cercano y profesional).
Reducir la carga operativa del soporte humano en un 20-30% mediante la resolución automatizada de primer nivel.
Implementar guías visuales (maquetas de imagen) para mejorar la comprensión de procesos transaccionales complejos.


**Metodología**: El proyecto se desarrollará bajo un enfoque iterativo de UX Content Design, siguiendo estos procedimientos:
Auditoría de conversaciones: Identificación de los intents o dudas más frecuentes (saldos, transferencias, seguridad).
Diseño de la arquitectura del prompt: Aplicación de un marco de trabajo de 5 niveles para asegurar que la IA no se desvíe del contexto financiero colombiano.
Prototipado y Simulación: Creación de un entorno controlado en Jupyter Notebook para validar que las respuestas sigan el orden lógico: Empatía > Explicación > Acción.
Validación mediante Test A/B: Se implementarán dos variantes de tono para medir cuál genera menor tasa de escalamiento a humanos, optimizando la solidez operativa del sistema.

**Herramientas y tecnología**
Para asegurar que el asistente hable el mismo lenguaje que nuestros usuarios, iteré el prompt para darle un rol y personalidad más detallada: experto en UX Content que entiende perfectamente el contexto de nuestra FinTech. A esto también sumé la metodología de few shoot prompting, dándole ejemplos reales de interacciones para que aprenda a responder con la estructura exacta que buscamos sin errores. Finalmente, apliqué una estructuración de salida muy clara; así, las respuestas no son párrafos densos, sino mensajes fáciles de escanear y realmente útiles para el cliente.

**Implementación**:

<Context_and_Persona> Actúa como un experto en UX Content Design para una fintech líder en Colombia.

<Goal_and_Personality> Tu objetivo es resolver dudas de forma servicial y profesional.

<Completion_Rules> Si mencionan fraude o robo, escala a un humano. No pidas claves.

<Output_Format> Toda respuesta debe seguir estrictamente este orden:
Una frase breve validando la emoción o situación del usuario (cuando sea necesario), los pasos concretos o respuesta directa a la duda, y una instrucción clara de qué debe hacer el usuario ahora.

<Few_shot_examples>
Usuario: "No veo mi plata".
IA: Entiendo que no ver tu saldo sea estresante. El sistema se está actualizando ahora mismo. Por favor, refresca la app en 5 minutos.
