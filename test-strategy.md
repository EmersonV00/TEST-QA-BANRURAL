Registro de Errores

Tipo de error:
    caught TypeError: guessSubmit.addeventListener is not a function
        at index.html:87:15

    El código encontrado en esta linea es: guessSubmit.addeventListener('click', checkGuess); 
    
Solución:
    Se utiliza el método addEventListener por lo cual la "E" de Event debe de ir en mayúscula y no en minúscula.

Tipo de error:
    caught TypeError: Cannot set properties of null (setting 'textContent')
        at HTMLInputElement.checkGuess (index.html:79:29)

    El error lo muestra en la linea 79 pero en realidad el error está en la linea 49, lo cual el código es: const lowOrHi = document.querySelector('lowOrHi'); el error se deriva ya que querySelector esta buscando una etiqueta cuando debería de buscar un elemento que tenga la clase 'lowOrHi'

Solución:
    Agregar el punto antes de lowOrHi, quedando así el código: const lowOrHi = document.querySelector('.lowOrHi');

Tipo de error:
    dex.html:95 Uncaught TypeError: resetButton.addeventListener is not a function
    at setGameOver (index.html:95:16)
    at HTMLInputElement.checkGuess (index.html:72:7)

   El código encontrado en esta linea es: resetButton.addEventListener('click', resetGame);

Solución:
    Se utiliza el método addEventListener por lo cual la "E" de Event debe de ir en mayúscula y no en minúscula.

Tipo de error:
    Actualmente se tiene el código randomNumber = Math.floor(Math.random()) + 1;, lo cual no genera un número entero entre 1 y 100 sino un número decimal.

Solución:
    let randomNumber = Math.floor(Math.random() * 100) + 1; con este nuevo código si generará un valor entre 1 y 100. Además se eliminó El código en la linea 114 ya que nuevamente se repetía el generador de número random.


Tipo de error:
    No se realiza ninguna validación sobre el número ingresado por el jugador, por ende no se valida si el número ingresado es entero o no.

Solución:
    Se utiliza la siguiente expresión regular: '/^\d+$/' para verificar que userGuess solo tenga valores enteros y en caso contrario entonces que muestre una alerta. 


Tipo de error:
    En la quinta vez que se ingresa un valor, ya sea repetido o no, muestra la alerta de "Felicitaciones! adivinaste el número!" y no se cumple las condicionales:
        *Sí el número que ingresó el jugador es mayor al número a adivinar, se debe mostrar el siguiente mensaje en color negro:"Incorrecto! El número es mayor!", en caso que sea menor, se debe mostrar: "Incorrecto! El número es menor!".
        *Si después de 10 intentos, el usuario no adivina el número, se debe mostrarse el mensaje de color rojo: "!!!Pérdistes!!!"
        *Si el usuario adivina el número antes de los 10 intentos, se debe mostrar el mensaje de color verde: "Felicitaciones! adivinaste el número!".

Solución:
    Modificar los ATTEMPTS, ya que actualmente tiene 5 y deben de ser 10 las oportunidades.
    En la validación de si el valor ingresado no coincide con el número aleatorio, cambiar el mensaje de color verde a negro.
    En la validación de si guessCount === ATTEMPS, cambiar el mensaje de "Felicitaciones! adivinaste el número!" por "!!!Pérdistes!!!"
    En la validación de userGuess === randomNumber, se cambió el mensaje de "!!!Pérdistes!!!" por "Felicitaciones! adivinaste el número!" además se cambió el color de mensaje de negro a verde.
