# Registro de discrepancias externas del SD4

Este archivo es una nota de trabajo separada del SD4, sus anexos y el Formulario T-11. No debe incorporarse al PDF de la oferta.

## Jerarquía aplicada

1. Figuras vigentes del SD4.
2. Cuerpo principal del SD4.
3. Anexos del SD4.
4. Formulario T-11, subordinado al SD4.
5. SD1 y SD3 como antecedentes externos. Una contradicción externa se revisa antes de modificar el SD4.

## Decisiones aplicadas en esta corrección

- Identidad: Amazon Cognito. Keycloak queda descartado.
- Nube: Región AWS Chile como principal condicionada a G-REG y AWS São Paulo como recuperación `warm standby`.
- WAN: fibra empresarial GTD/Telsur como principal y Starlink Fixed Site/Priority como respaldo LEO.
- Medición: 640 medidores iniciales, 320 de agua y 320 de energía.
- Móviles: 14 terminales operacionales y 2 reservas, total 16.
- Wi-Fi de terreno: 12 AP instalados, 10 en pantalanes y 2 en varadero, conforme a la figura 4.5.
- Ocupación: la función obligatoria se sustenta en bitácora operacional y ronda física registrada. El piloto opcional queda limitado a 20 posiciones y no autoriza despliegue masivo.

## Discrepancias externas para revisión posterior

### Cantidad de medidores

- SD1/T-6 declara 1.900 puntos o medidores telemétricos.
- SD3 y SD4 definen 640 medidores: 320 de agua y 320 de energía.
- Criterio temporal: se mantienen 640 porque es la cifra detallada y repetida en SD3/SD4. SD1 debe revisarse por separado.

### Localización cloud

- SD3 contiene referencias a AWS Santiago y a una Local Zone de Santiago.
- El SD4 exige una Región AWS Chile con dos AZ físicas y prohíbe sustituirla por una Local Zone.
- Criterio temporal: manda el SD4. G-REG debe acreditar disponibilidad general, código real, dos AZ, catálogo, cuotas y contratación antes de habilitar la región.

### Sensores de ocupación

- SD3 establece que la ocupación de las amarras no depende de sensores inalámbricos.
- El SD4 conserva un piloto opcional para evaluar señales auxiliares.
- Criterio temporal: la bitácora y la ronda física son la autoridad operacional; el piloto no participa en la asignación exclusiva ni en cobros.

### Selecciones tecnológicas no cerradas

- La pasarela de pagos permanece genérica porque no existe una selección respaldada de Transbank, Webpay, Mercado Pago u otro proveedor.
- Los modelos definitivos de gateway de terreno, medidores de agua y energía, sensores del piloto y determinados accesorios deben quedar individualizados en la BOM y aceptados mediante ficha y ensayo.
- Las figuras lógicas mantienen denominaciones funcionales; los proveedores o productos concretos corresponden al T-11 o a la BOM cuando exista evidencia de selección.

## Figuras

Las figuras no fueron editadas en esta etapa. Los rótulos internos que indiquen validación o ingeniería posterior se revisarán únicamente cuando se autorice una etapa específica de actualización gráfica.
