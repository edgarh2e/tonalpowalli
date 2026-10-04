# Tonalpowalli — revisión de textos en nawatl tlaxcalteca

Todos los textos de la interfaz. La columna **Borrador** contiene propuestas
que requieren revisión de un hablante; las filas **por traducir** se muestran
hoy en español. 20 de 48 claves tienen borrador.

**Cómo aplicar las correcciones:** edita o agrega las claves en
`site/i18n/nah.js`. Las variables entre llaves (`{d}`, `{n}`, `{p}`,
`{m}`) deben conservarse: la página las sustituye por números. Cuando la
traducción esté revisada, cambia `window.BORRADOR_NAWATL = true` a `false` (en el mismo archivo) para
quitar el aviso.

Los nombres de signos, veintenas y portadores no están aquí: ya usan la
ortografía del proyecto y no cambian con el idioma.

| Clave | Español | Borrador nawatl                                                      | Estado |
|---|---|----------------------------------------------------------------------|---|
| `lede` | Convierte fechas entre el calendario gregoriano y el tonalpowalli: el tonalli del día, su lugar en la veintena y el xiwitl que lo contiene. | Mokawipoalkwepas notonalpowaltsitsiwan wan gregoriano tonaltsitsiwan | borrador — revisar |
| `fechaGreg` | Fecha gregoriana | Tonalli (gregoriano)                                                 | borrador — revisar |
| `prev` | Día anterior | Yalwatsintko tonalli                                                 | borrador — revisar |
| `next` | Día siguiente | Mostlatsinko tonalli                                                 | borrador — revisar |
| `hoy` | Ver hoy | Axan                                                                 | borrador — revisar |
| `veintena` | Veintena | Senpowalli                                                           | borrador — revisar |
| `diaDe` | Día {d} de {n} | Tonalli {d} in {n}                                                   | borrador — revisar |
| `nemNota` |  — días sobrantes del xiwitl | Tonalli mokawa in xiwitl                                             | por traducir |
| `xiwitl` | Xiwitl | Xiwitl                                                               | borrador — revisar |
| `diaAnio` | Día del xiwitl | Tonalli ipan xiwitl                                                  | borrador — revisar |
| `diaAnioVal` | {p} de 365 | {p} ipan 365                                                         | borrador — revisar |
| `portador` | Portador | Xiwtonalli                                                           | borrador — revisar |
| `bisiesto` | Día bisiesto: repite el tonalli del día anterior y no avanza la cuenta. |                                                                      | por traducir |
| `puntos` | numeral {n} de 13 |                                                                      | por traducir |
| `invH` | Del tonalpowalli al gregoriano |                                                                      | por traducir |
| `invP` | Elige lo que sepas de la fecha. Con sólo el tonalli, la fecha se repite cada 260 días; con tonalli y posición en la veintena, una vez cada 52 años. |                                                                      | por traducir |
| `grpTonalli` | Tonalli | Tonalli                                                              | borrador — revisar |
| `grpVeintena` | Veintena | Sempowalli                                                           | borrador — revisar |
| `grpXiwitl` | Xiwitl | Xiwitl                                                               | borrador — revisar |
| `grpRango` | Buscar entre |                                                                      | por traducir |
| `numeral` | Numeral | Tlapowalli                                                           | borrador — revisar |
| `signoL` | Signo | Itoka                                                                | borrador — revisar |
| `diaVein` | Día | Tonalli                                                              | borrador — revisar |
| `desdeAnio` | Desde el año |                                                                      | por traducir |
| `hastaAnio` | Hasta el año |                                                                      | por traducir |
| `buscar` | Buscar fechas | Xiktemo                                                              | borrador — revisar |
| `limpiar` | Limpiar | Xikpopowa                                                            | borrador — revisar |
| `faltaDato` | Elige al menos un dato. |                                                                      | por traducir |
| `rangoMal` | El rango debe ir de 1583 a 2400, con el año final después del inicial y no más de 500 años. |                                                                      | por traducir |
| `diaNem` | Nemontemi sólo tiene 5 días. |                                                                      | por traducir |
| `hallados` | {n} fechas encontradas. |                                                                      | por traducir |
| `halladosMas` | {n} fechas encontradas; se muestran las {m} más cercanas a hoy. |                                                                      | por traducir |
| `uno` | 1 fecha encontrada. |                                                                      | por traducir |
| `ninguna` | Ninguna fecha cumple esa combinación en el rango. Algunas combinaciones no existen: el signo del día queda fijado por la posición en la veintena y el portador del xiwitl. Si la combinación es posible, amplía el rango. |                                                                      | por traducir |
| `tagBis` | bisiesto |                                                                      | por traducir |
| `expH` | Exportar un rango |                                                                      | por traducir |
| `expP` | Genera la correlación día por día entre dos fechas y descárgala como CSV. |                                                                      | por traducir |
| `desde` | Desde | Kampa pewa                                                           | borrador — revisar |
| `hasta` | Hasta | Kampa tlami                                                          | borrador — revisar |
| `descargar` | Descargar CSV |                                                                      | por traducir |
| `expDos` | Elige las dos fechas. |                                                                      | por traducir |
| `expOrden` | La fecha final es anterior a la inicial. |                                                                      | por traducir |
| `expGrande` | El rango excede 200 000 días. |                                                                      | por traducir |
| `expListo` | {n} días exportados. |                                                                      | por traducir |
| `sigH` | Los veinte signos |                                                                      | por traducir |
| `sigP` | La cuenta avanza un signo cada día y vuelve al principio cada veinte. El signo del día elegido aparece resaltado. |                                                                      | por traducir |
| `pie1` | La correlación usada aquí fija el 12 de marzo de 2026 como 1 Tochtli, con el xiwitl comenzando siempre el 12 de marzo y el 29 de febrero repitiendo el tonalli anterior. Existen otras correlaciones —Caso, Jiménez Moreno, Tena— y cuentas vivas en Tlaxcala y Milpa Alta que no coinciden entre sí. Esta página reproduce una de ellas; no zanja cuál es la correcta. |                                                                      | por traducir |
| `pie2` | Las fechas se calculan en calendario gregoriano; por eso el rango empieza en 1583. |                                                                      | por traducir |
| `creditoLabel` | Investigación, reconstrucción de la cuenta y corrección: | Tlapoaltemolistli wan  Tlapoalchiwaltia                              | borrador — revisar|
