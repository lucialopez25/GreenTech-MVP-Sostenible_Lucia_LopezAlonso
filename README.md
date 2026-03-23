# Informe Ejecutivo: Auditoría y Refactorización GreenTech MVP

## 1. Contexto de la Auditoría: La Paradoja Digital
El código heredado para la *landing page* de GreenTech presentaba una grave ineficiencia energética. La página importaba la librería Bootstrap completa, FontAwesome para un único icono, 5 variantes de Google Fonts, y dependencias JavaScript como jQuery y Moment.js exclusivamente para calcular el año actual en el pie de página. Además, cargaba una imagen sin optimizar de 3000px de resolución. Esta "grasa digital" generaba cientos de kilobytes innecesarios por visita.

## 2. Refactorización Técnica
Se ha reescrito el producto desde cero para lograr un MVP verdaderamente sostenible:
* **Eliminación de Frameworks:** Sustitución de Bootstrap por CSS nativo (Flexbox y variables), y reemplazo de FontAwesome por un icono SVG incrustado.
* **JavaScript Nativo:** Se han eliminado jQuery y Moment.js. El cálculo dinámico del año se realiza ahora con el objeto `Date()` de JavaScript Vanilla en una sola línea de código.
* **Optimización de Recursos:** Sustitución de Google Fonts por tipografías del sistema (`system-ui`).
* **Implementación de Lazy Loading:** La imagen principal se gestiona mediante la etiqueta `<img>` con el atributo `loading="lazy"`, reduciendo la transferencia de datos si el usuario no tiene la imagen en el *viewport*.

## 3. Visión de Economía Circular y Criterios ASG
El desarrollo de software tiene impacto físico. Las decisiones de refactorización tomadas responden a criterios ASG (Ambiental, Social y Gobernanza):
* **Ahorro Energético (Carbono Operacional):** Al eliminar librerías externas pesadas, reducimos el ancho de banda necesario, lo que se traduce directamente en un menor consumo energético en los servidores, redes de transmisión y en el dispositivo del usuario final [1].
* **Lucha contra la Obsolescencia (Carbono Embebido):** Ejecutar jQuery y Moment.js para tareas triviales genera una carga de CPU innecesaria. Un software ligero evita el sobrecalentamiento y el agotamiento rápido de la batería en teléfonos móviles de gama baja. Fomentar que el *hardware* dure más años previene su descarte prematuro, reduciendo la basura electrónica (*e-waste*) y alineándose con la economía circular [2], [3].

## 4. Referencias
[1] W3C, "Web Sustainability Guidelines (WSG) 1.0," World Wide Web Consortium, 2023. [Online]. Available: https://www.w3.org/TR/wsg/
[2] Green Software Foundation, "Green Software Practitioner Course," 2024. [Online]. Available: https://learn.greensoftware.foundation/
[3] R. Verdecchia, P. Lago, I. Malavolta, y G. Procaccianti, "Green IT and Green Software Engineering: A Systematic Mapping Study," arXiv preprint arXiv:2102.04945, 2021. [Online]. Available: https://arxiv.org/abs/2102.04945