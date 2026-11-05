CSS
## Hallazgos: El Modelo de Caja

1. **Diferencia práctica entre Margin y Padding:**
   - El **Padding** es el relleno interno que se encuentra dentro de los límites del borde de la caja; sirve para separar el contenido de los bordes y darle "oxígeno" visual.
   - El **Margin** es el espacio exterior que se encuentra fuera del borde; sirve para separar la caja completa respecto a los elementos hermanos que la rodean en la pantalla.

2. **Por qué es obligatorio usar `box-sizing: border-box`:**
   - Por defecto, el navegador suma el padding y el borde al ancho total del elemento, haciendo que la caja crezca y rompa el diseño. Al configurar `box-sizing: border-box;` en el selector universal (`*`), logramos que los rellenos y bordes crezcan *hacia adentro*, manteniendo el ancho exacto que le programamos y evitando deformaciones en la estructura.

3. **Cómo se ven afectados los elementos hermanos cuando le aplicas un margen grande a uno de ellos:**
   - El elemento se desplaza empujando a los demás hacia abajo o hacia los lados según su flujo, generando mayor distancia visual (espacio en blanco) entre ellos. Además, en el eje vertical los márgenes adyacentes pueden fusionarse o colapsar en uno solo (colapso de márgenes), adoptando el valor del margen más grande en lugar de sumar ambos.

## Hallazgos: Centralización de Identidad Visual y Espaciado

El catálogo concentra sus valores de presentación en `:root` al comienzo de `estilos.css`. Las variables declaradas son:

- **Colores:** `--color-primario` (`#0d6efd`), `--color-secundario` (`#e9ecef`), `--color-fondo` (`#f8f9fa`), `--color-texto` (`#333333`), `--color-titulo` (`#1a252f`), `--color-descripcion` (`#495057`), `--color-texto-secundario` (`#6c757d`), `--color-superficie` (`#ffffff`), `--color-borde` (`#dee2e6`), `--color-borde-secundario` (`#ced4da`), `--color-fondo-footer` (`#343a40`), `--color-enlace-principal` (`blue`), `--color-enlace-secundario` (`green`), `--color-enlace-footer` (`gray`) y `--color-acento` (`orange`).
- **Tipografía:** `--fuente-principal` usa Roboto desde Google Fonts, con `sans-serif` como alternativa.
- **Espaciado:** `--espaciado-pequeno` (`8px`), `--espaciado-medio` (`16px`), `--espaciado-grande` (`24px`) y `--espaciado-extra-grande` (`32px`).

Reutilizar tokens de margen y relleno mantiene proporciones consistentes entre tarjetas y secciones y permite ajustar el aire del diseño desde una escala común, en lugar de introducir medidas ligeramente distintas en cada selector. Centralizar también la paleta hace que cada zona use roles de color reconocibles. Cuando la hoja crece, cambiar esos valores en un único punto evita que reglas nuevas y antiguas diverjan accidentalmente y generen contrastes o espaciados incompatibles.