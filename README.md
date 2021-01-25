# Programacionr-3semana-taller
Introducción

Esta segunda asignación de programación requerirá que escriba una función R que pueda almacenar en caché cálculos que potencialmente consumen mucho tiempo. Por ejemplo, tomar la media de un vector numérico suele ser una operación rápida. Sin embargo, para un vector muy largo, puede llevar demasiado tiempo calcular la media, especialmente si tiene que calcularse repetidamente (por ejemplo, en un bucle). Si el contenido de un vector no cambia, puede tener sentido almacenar en caché el valor de la media para que cuando lo necesitemos de nuevo, se pueda buscar en la caché en lugar de volver a calcularlo. En esta asignación de programación, aprovechará las reglas de alcance del lenguaje R y cómo se pueden manipular para preservar el estado dentro de un objeto R.

Ejemplo: almacenamiento en caché de la media de un vector

En este ejemplo, presentamos el operador << - que se puede usar para asignar un valor a un objeto en un entorno que es diferente del entorno actual. A continuación se muestran dos funciones que se utilizan para crear un objeto especial que almacena un vector numérico y almacena en caché su media.

La primera función, makeVector crea un "vector" especial, que en realidad es una lista que contiene una función para

establecer el valor del vector obtener el valor del vector establecer el valor de la media obtener el valor de la media makeVector <- function (x = numeric ()) {m <- NULL set <- function (y) {x < <- ym << - NULL} get <- function () x setmean <- function (mean) m << - mean getmean <- function () m list (set = set, get = get, setmean = setmean, getmean = getmean)} La siguiente función calcula la media del "vector" especial creado con la función anterior. Sin embargo, primero verifica si la media ya se ha calculado. Si es así, obtiene la media de la caché y se salta el cálculo. De lo contrario, calcula la media de los datos y establece el valor de la media en la caché mediante la función setmean.

cachemean <- function (x, ...) {m <- x $ getmean () if (! is.null (m)) {message ("obteniendo datos en caché") return (m)} data <- x $ get () m <- mean (data, ...) x $ setmean (m) m} Asignación: Almacenamiento en caché de la inversa de una matriz

La inversión de matrices suele ser un cálculo costoso y puede haber algún beneficio de almacenar en caché la inversa de una matriz en lugar de calcularla repetidamente (también hay alternativas a la inversión de matrices que no discutiremos aquí). Su tarea es escribir un par de funciones que almacenan en caché la inversa de una matriz.

Escribe las siguientes funciones:

makeCacheMatrix: esta función crea un objeto "matriz" especial que puede almacenar en caché su inverso. cacheSolve: esta función calcula la inversa de la "matriz" especial devuelta por makeCacheMatrix anterior. Si la inversa ya se ha calculado (y la matriz no ha cambiado), cacheSolve debería recuperar la inversa de la caché. El cálculo de la inversa de una matriz cuadrada se puede hacer con la función resolver en R. Por ejemplo, si X es una matriz cuadrada invertible, resolver (X) devuelve su inversa.

Para esta asignación, suponga que la matriz suministrada siempre es invertible.

Para completar esta tarea, debe hacer lo siguiente:

Bifurque el repositorio de GitHub que contiene los archivos stub R en https://github.com/rdpeng/ProgrammingAssignment2 para crear una copia en su propia cuenta. Clone su repositorio de GitHub bifurcado en su computadora para que pueda editar los archivos localmente en su propia máquina. Edite el archivo R contenido en el repositorio de git y coloque su solución en ese archivo (no cambie el nombre del archivo). Confirme su archivo R completo en SU ​​repositorio de git y envíe su rama de git al repositorio de GitHub en su cuenta. Envía a Coursera la URL de tu repositorio de GitHub que contiene el código R completo para la tarea. Calificación

Esta tarea se calificará mediante una evaluación de pares.
