CSS
## Hallazgos: El Modelo de Caja

1. **Diferencia práctica entre Margin y Padding:**
   - El **Padding** es el relleno interno que se encuentra dentro de los límites del borde de la caja; sirve para separar el contenido de los bordes y darle "oxígeno" visual.
   - El **Margin** es el espacio exterior que se encuentra fuera del borde; sirve para separar la caja completa respecto a los elementos hermanos que la rodean en la pantalla.

2. **Por qué es obligatorio usar `box-sizing: border-box`:**
   - Por defecto, el navegador suma el padding y el borde al ancho total del elemento, haciendo que la caja crezca y rompa el diseño. Al configurar `box-sizing: border-box;` en el selector universal (`*`), logramos que los rellenos y bordes crezcan *hacia adentro*, manteniendo el ancho exacto que le programamos y evitando deformaciones en la estructura.

3. **Cómo se ven afectados los elementos hermanos cuando le aplicas un margen grande a uno de ellos:**
   - El elemento se desplaza empujando a los demás hacia abajo o hacia los lados según su flujo, generando mayor distancia visual (espacio en blanco) entre ellos. Además, en el eje vertical los márgenes adyacentes pueden fusionarse o colapsar en uno solo (colapso de márgenes), adoptando el valor del margen más grande en lugar de sumar ambos.

   ## Hallazgos: Arquitectura BEM y Modularidad

1. **Qué significa la sigla BEM y cómo se escribe visualmente:**
   - Corresponde a **Block, Element, Modifier** (Bloque, Elemento, Modificador). Se estructura empleando guion bajo doble para los elementos (`bloque__elemento`) y guion medio doble para los modificadores (`bloque--modificador`).

2. **Por qué dividir el CSS en varios archivos facilita el trabajo colaborativo:**
   - Permite aislar responsabilidades por componentes independientes (`tarjeta.css`, `botones.css`, etc.), evitando que varios desarrolladores escriban sobre un único archivo gigante y reduciendo drásticamente los conflictos de fusión (merge conflicts) en Git.

3. **Cómo esta metodología evita la guerra de especificidad (Cascada):**
   - Mantiene una especificidad plana y predecible basada en clases individuales (peso 10), eliminando selectores anidados complejos y previniendo que una regla suprima a otra de forma accidental a medida que el proyecto crece.