# **Comentarios sobre la refactorizacion de CatalagoCloud.xsd y CatalagoCloud.xml**

1. Al usar grupos conseguimos en la definicion de la estructura del documento que las líneas de código para definir los atributos y
los elementos del hardware junto a todos sus atributos y restricciones se conviertan en una simple línea cada uno en la que llamamos
a la referencia de cada grupo. Esto permite que en caso de querer volver a utilizar alguno de estos grupos definidos en otro elemento nuevo
en el futuro solo haya que volver a referenciarlo y no escribir entero toda la definición consiguiendo escabilidad.

2. Al poner dos servidores con el mismo Id, la restricción *UnicoID* de tipo unique name que se ha añadido al final del elemento padre centro_datos actúa y
se genera un error *cvc-identity-constraint.4.1: Duplicate unique value [srv-db-01] found for identity constraint "UnicoID" of element "catalogo_cloud".xml(DuplicateUnique)*
que identifica que hay dos atributos *id* con el mismo valor *srv-db-01* y que se no es posible que se dé esto en este documento.
