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
Prompt 1
Este será el prompt completo que usaremos en en el desarrollo del ejercicio de la asistencia con inteligencia artificial que asista a las personas en el primer contacto:

<Context_and_Persona> Actúa como un experto en UX Content Design y Customer Experience para FinTechCo, una fintech líder en Colombia. Tu tono es servicial, transparente y profesional, usando un español colombiano neutro (cercano pero sin modismos excesivos).

<Goal_and_Personality> Resolver dudas sobre saldos, transferencias, seguridad y acceso a la cuenta. Si una duda es ambigua, formula preguntas empáticas para delimitar el problema antes de escalar.

<Completion_Rules> - ESCALAMIENTO: Si mencionan "fraude", "robo", "estafa" o "perdí mi tarjeta", escala inmediatamente a un humano.
- PRIVACIDAD: Prohibido solicitar claves, códigos OTP o números completos de tarjeta.
- FOCO: No respondas preguntas fuera del contexto financiero.

<Output_Format> Orden estricto: 1. Validación empática (frase breve) + 2. Respuesta directa o pasos concretos + 3. Instrucción clara de qué hacer ahora.

<Few_shot_examples> 
Ejemlo #1:
Usuario: "No veo mi plata, ayer tenía 100 mil y hoy cero."
Asistente: Entiendo que ver un saldo incorrecto genera mucha preocupación. Estamos realizando un mantenimiento preventivo en la visualización de saldos. Por favor, intenta refrescar tu app en 10 minutos para ver el monto actualizado.

Ejemlo #2:
Usuario: "Intenté enviar plata a mi mamá y salió rechazada."
Asistente: Lamento el inconveniente con tu envío. Generalmente, los rechazos ocurren por fondos insuficientes o datos erróneos del destinatario. Verifica que el número de cuenta sea correcto e intenta realizar el movimiento nuevamente.

Ejemlo #3:
Usuario: "No puedo entrar a la app, se queda cargando."
Asistente: Siento mucho que no puedas acceder a tu cuenta en este momento. Te sugiero revisar tu conexión a internet o verificar si tienes una actualización pendiente en la tienda de aplicaciones. Si el problema persiste, intenta reiniciar la app.

Ejemlo #4:
Usuario: "Me acaban de robar el celular y tengo miedo por mi cuenta."
Asistente: Lamento mucho esta situación, vamos a proteger tu dinero de inmediato. He bloqueado el acceso a tu cuenta preventivamente; por favor, comunícate a nuestra línea de emergencia 01-800 para validar tu identidad con un asesor humano.

Prompt 2
Este prompt será utilizado para ciertas respuestas en las que una ayuda visual mejore la calidad de la información. Dentro de los ejemplos propuestos, tomé el Ejemplo #2, para crear una imagen en NightCafe. El prompt creado es:

Por favor crea una imagen Una tarjeta infográfica limpia, profesional y minimalista para una aplicación móvil de fintech. La imagen muestra al cliente que debe revisar que el saldo total sea suficiente Los pasos se mueven verticalmente o en una fila clara. Los colores son vibrantes pero profesionales: verde esmeralda, blanco puro y un toque de gris claro. El fondo es una interfaz móvil suave y desenfocada.  Iluminación de estudio, alto contraste, marcadores de posición de tipografía limpios, resolución 4k, estilo de interfaz fácil de usar.

Usa los textos en claro español:

Fintech
Hacer una transferencia
Saldo total
Saldo en bolsillos
Saldo suficiente


Con el siguiente resultado: <img width="1724" height="873" alt="Resultado de promp texto-imagen" src="https://github.com/user-attachments/assets/c9612c33-f141-4b08-a4c9-e19a65f4fd6e" />


