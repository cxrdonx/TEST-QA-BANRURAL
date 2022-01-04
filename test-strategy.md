## Objeto de prueba
Se recibe un index.html que contiene html y un script.
## Comprobación de funcionalidad
Se comprueba si el programa está funcionando correctamente ejecutando el index.html abriendolo en el navegador
predeterminado.
## Resultado esperado
Que el script se ejecute de manera correcta solicitandole el número a ingresar al usuario y que funcione el juego 
conforme a los requerimientos.
## Resultado actual
Se muestra el contenido del html en el navegador sin embargo el script no se ejecuta.
## Plan de ataque
Mediante la consola del navegador se verifica si el código está devolviendo algún dato que nos proporcione mayor información
y se puede visualizar un error "guessSubmit.addeventListener is not a function, se efectúa una prueba en consola llamando la función 
principal y efectivamente, el script se ejecuta, a partir de aquí se corregiran los errores que vayan surgiendo ejecutando pequeños test unitarios
para saber si las funciones retornan el valor deseado, constantes o variables estén bien definidas etc.
## guessSubmit.addeventListener is not a function
Reemplazar en la líneas 86 y 94 por .addEventListenner, error sintactico.
## lowOrHi is null
Para poder obtener el div lowOrHi por medio del DOM, es necesario definirlo de la manera correcta, en la línea 50 reemplazar por  const guessSubmit = document.querySelector('.guessSubmit');
## randomNumber error
la linea 44 devuelve un número random con punto décimal, reemplazar por: let randomNumber =  Math.floor(Math.random() * (100 - 1)) + 1.
## Falta validar si el usuario ingresa un numero entero
agregar la alerta para el usuario en caso de no ingresar un numero entero sin incrementar el contador de intentos: if(guess%1 == 0 ){ //resto de la funcionlaidad de checkGuess()  }else{
        alert("no permitido ingrese un numero entero ");
      }
## variable let guessCount = 1
cambiar la inicialización de la variable let guessCount =1 de la línea 54 a guessCount =0 para que empieze a contar los turnos correctamente.
## Constante ATTEMPS
constante de la línea 47 debe de ser inicializada a 10 y no a 5 para cumplir con los requerimientos.
## Condicional if cuando se acierta el numero
Línea 65 si se comparan 2 elementos con el operador "===" estos deben de ser del mismo tipo de dato, cambiar por "==" o convertir userGuess a number.
corregir lastResult.textContent = "Felicitaciones! adivinaste el número!"  y lastResult.style.backgroundColor = 'green'.
## Condicional if cuando se supera el número de oportunidades
Cambiar la línea 71 por lastResult.textContent = '!!!Pérdistes!!!', ya que no es la condición que indica que hemos ganado.
## Números incorrectos
En caso de que el usuario ingrese un número incorrecto se debe de mostrar Incorrecto y si el número ingresado es mayor o menor al número random.
Cambiar la línea 82 y 83 por  lastResult.style.backgroundColor = 'black' lowOrHi.style.backgroundColor = 'black' respectivamente.
# Si el número es mayor o menor
Para evitar contar el doble turno, se debe de agregar guessCount--; en las líneas 87 y 90. Caso contrario modularizar en otra función.
## Funcion resetGame()
A la hora de volver a empezar el juego randomNumber no se reinicia como número entero de entre 1 al 100, cambiar la línea 116 por randomNumber =  Math.floor(Math.random() * (100 - 1)) + 1.
## Resultado actual
Script funcionando correctamente, cumpliendo con todos los requerimientos.





