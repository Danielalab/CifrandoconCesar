## CIFRANDO CON CESAR
#### **Objetivo del programa**
##### Crear una web que pida, por medio de un prompt(), una frase al usuario y devuelva el mismo mensaje encriptado según el algoritmo de Cifrado César con el parámetro de desplazamiento de 33 espacios hacia la derecha.
##### *Cifrado de Cesar : Es un tipo de cifrado de sustitución en el que cada letra en el texto plano se sustituye por una letra un número fijo de posiciones por el alfabeto . Por ejemplo, con un desplazamiento a la izquierda de 3, D sería reemplazado por A , E se convertiría en B , y así sucesivamente. El método lleva el nombre de Julio César, que lo utilizó en su correspondencia privado.*
      Fórmula para cifrar: (x + n) % 26 || Fórmula para decifrar: (x - n) % 26
      donde : x = posición de la letra en el alfabeto.
              n = valor fijo de desplazamiento.
              26 = cantidad de letras en el abecedario.
#### **Algoritmo del programa**
##### 1. Declarar la función *'cipher'* para cifrar nuestra cadena de texto que tenga como parámetro *(myString)*.
##### 1.1. Declarar *var myStringCipher = ''* , en la cual almacenaremos el valor de nuestra cadena cifrada.
##### 1.2. Crear un bucle *For*, para recorrer nuestra cadena de texto.
         for (var i = 0 ; i < myString.length ; i++)
##### Declarar dentro del bucle *For* las siguientes variables:
+ ##### *var numberOfTheLetter = myString.charCodeAt(i)*, en la cual haremos uso del método *chardCodeAt()* para obtener el numero de la letra en el codigo AISSII.
+ ##### *var cipherFormula*, para almacenar la fórmula de cifrado que se utilizará.
+ ##### *var theNewLetter*; para almacenar el nuevo valor de letra cifrada.

##### 1.3. Luego declarar dentro del bucle la estrutura condicional *if else* , para verificar que solo cifraremos letras :
##### 1.3.1. La primera condición : *Si (numberOfTheLetter >= 65 && numberOfTheLetter <= 90)*  
##### sirve para verificar si la letra está mayúscula; si la condición es TRUE:
+ ##### El valor de *cipherFormula = ( numberOfTheLetter - 65 + 33) % 26 + 65* ; es decir la fórmula de Cifrado Cesar con la cual obtendremos el nuevo numero de letra en el codigo AISSII.
+ ##### El valor de *theNewLetter =  String.fromCharCode(cipherFormula)*, en el cual hacemos uso del método *String.fromCharCode()* para obtener el nuevo valor de la letra cifrada.
+ ##### Y al valor de *myStringCipher (inicialmente una cadena vacia (''))* se le concatena *theNewLetter* para ir formando el string cifrado.

##### 1.3.2. La segunda condición *De otra manera Si(numberOfTheLetter >= 97 && numberOfTheLetter <=122)* , sirve para verificar si la letra está en minúscula; si la condición es TRUE:
+ ##### El valor de *cipherFormula = ( numberOfTheLetter - 97 + 33) % 26 + 97*; es decir la fórmula de Cifrado Cesar con la cual obtendremos el nuevo numero de letra en el codigo AISSII.
+ ##### El valor de *theNewLetter = String.fromCharCode(cipherFormula)*, en el cual hacemos uso del método *String.fromCharCode()* para obtener el nuevo valor de la letra cifrada.
+ ##### Y el valor de *myStringCipher* será igual a su mismo valor en ese momento concatenado con *theNewLetter* para ir formando el string cifrado.

##### 1.4. Escribir *myStringCipher* como valor de retorno de la funcíón *cipher*.
##### 2. Declarar la función *'decipher'*; para decifrar nuestra cadena de texto, que tenga como parámetro *myString)*.
##### 2.1. Declarar *var myStringDechiper = ''* , en la cual almacenaramos el valor de nuestra cadena decifrada.
##### 2.2. Crear un bucle *For*, para recorrer nuestra cadena de texto.
       for (var i = 0 ; i < myString.length ; i++)
##### 2.2.1.Declarar dentro del bucle For las siguientes variables:
+ ##### *var numberOfTheLetter = myString.charCodeAt(i)*, en la cual haremos uso del método *chardCodeAt()* para obtener el numero de la letra en el codigo AISSII.
+ ##### *var decipherFormula*, para almacenar la fórmula de decifrado que se utilizará.
+ ##### *var theNewLetter*; para almacenar el nuevo valor de letra decifrada.

##### 2.3. Luego declarar dentro del bucle la estrutura condicional *if else* , para verificar que solo decifremos letras :
##### 2.3.1. La primera condición *Si (numberOfTheLetter >= 65 && numberOfTheLetter <= 90)*, sirve para verificar si la letra está mayúscula; si la condición es TRUE:
+ ##### El valor de *cipherFormula = ( numberOfTheLetter - 13 - 33) % 26 + 65*; es decir la fórmula de Decifrado Cesar con la cual obtendremos el nuevo numero de letra en el codigo AISSII.
+ ##### El valor de *theNewLetter =  String.fromCharCode(cipherFormula)*, en el cual hacemos uso del método *String.fromCharCode()* para obtener el nuevo valor de la letra decifrada.
+ ##### Y al valor de *myStringDechiper (inicialmente una cadena vacia (''))* se le concatena *theNewLetter* para ir formando el string decifrado.

##### 2.3.2. La segunda condición *De otra manera Si(numberOfTheLetter >= 97 && numberOfTheLetter <=122)* , sirve para verificar si la letra está en minúscula; si la condición es TRUE:
+ ##### El valor de *decipherFormula = ( numberOfTheLetter - 38 - 33) % 26 + 97*; es decir la fórmula de Decifrado Cesar con la cual obtendremos el nuevo numero de letra en el codigo AISSII.
+ ##### El valor de *theNewLetter = String.fromCharCode(cipherFormula)*, en el cual hacemos uso del método *String.fromCharCode()* para obtener el nuevo valor de la letra decifrada.
+ ##### Y el valor de *myStringCipher* será igual a su mismo valor en ese momento concatenado con theNewLetter para ir formando el string decifrado.

##### 2.4. Escribir *myStringDechiper* como valor de retorno de la funcíón *decipher*.

##### 3. Declarar la función *'dataUser'*; la cual servirá para ver que desea realizar el usuario , cuyo parámetro sea *(option)*.
##### 3.1. Declarar *var userText*, para almacenar el texto que el usuario ingreso.
##### 3.2. Declarar *var verification*; para verificar que no se utilicen númmeros o cadenas vacias.
##### 3.3. Crear la estructura condicional *SWITCH* que tenga como parámetro (TRUE).
##### 3.3.1. Crear el primer caso que verifique *(option === '1')*, si es TRUE :
+ ##### El valor de *userText* es igual a un *prompt*  que le pregunta al usuario *¿Qué texto desea cifrar? (Por favor ingresar un texto)*.
+ ##### El valor de *verification = parseInt(userText)*, para parsear el string (resultará NaN si es texto);
+ ##### Crear un bucle *WHILE* el cual tenga como condición *(verification >=0* || *verification <=0* || *userText === '')* , para verificar que la cadena no contenga ningún número ni un espacio vacio al inicio de la cadena.
+ ##### Si la condición es TRUE el valor de *userText = prompt('¿Qué texto desea cifrar? (Por favor ingresar un texto)')* y el valor de *verification = parseInt(userText)*;
+ ##### Si la condicón es FALSE crear un *alert* que llame a la función *cipher* y le envie como parámetro *userText*.
+ ##### Terminar el caso con la palabra clave *break*.
##### 3.3.2. Crear un segundo caso que verifique *(option === '2')*, si es TRUE :
+ ##### El valor de userText es igual a un *prompt* que le pregunta al usuario *¿Qué texto desea decifrar? (Por favor ingresar un texto)*.
+ ##### El valor de verification = parseInt(userText), para parsear el string el cual resultará NaN si es texto.
+ ##### Crear un bucle *WHILE* el cual tenga como condición *(verification >=0* || *verification <=0* || *userText === '')* , para verificar que la cadena no contenga ningún número ni un espacio vacio al inicio del string.
+ ##### Si la condición es TRUE el valor de *userText = prompt('¿Qué texto desea decifrar? (Por favor ingresar un texto)')* y el valor de *verification = parseInt(userText)*;
+ ##### Si la condicón es falsa crear un alert que llame a la función *decipher* y le envie como parámetro *userText*.
+ ##### Terminar el caso con la palabra clave *break*.

##### 3.4. Por último, cerrar la estrutura *SWITCH* , el bucle *For* y la fución *dataUser*.

##### 4. Crear un bucle *DO WHILE* , para comprobar que desea realizar el usuario.
##### 4.1. Dentro de la estructura *DO* :
+ ##### Declarar *var menu = 'Por favor escribir 1 si desea cifrar un texto \n Por favor escribir 2 si desea descifrar un texto \n Por favor escribir 3 si desea salir del sistema', almacenar la lista de tareas que el usuario podrá realizar.*
+ ##### Declarar *var option = prompt(menu)*, para preguntarle al usuario que opción del menú desea realizar.
+ ##### Llamar a la función *dataUser* y darle como parámetro *(option)*.

##### 4.2. Dentro de la estrutura *WHILE* escribir la condición *( option !== '3')*, con lo cual seguiremos preguntándole al usuario que tarea desea realizar hasta que coloque la opción 3 para salir del programa.

#### **Diagrama de flujo del programa**

<https://ibb.co/hwuMAb>

#### **Fuentes**

<https://en.wikipedia.org/wiki/Caesar_cipher>
<https://www.youtube.com/watch?v=zd8eVrXhs7Y>
<https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String/charCodeAt>
<https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String/fromCharCode>
<http://conceptodefinicion.de/ascii/>
<https://imgbb.com/>
<https://code2flow.com/>
