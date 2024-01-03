> [!example]
> **TIPOS DE VARIABLES**
>   ![[Pasted image 20240102193537.png]]
> *El tipo de variable es ==camelCase==*
> *El tipo de variable ==let== se puede declarar y luego asignar valor*

---

// ========= STRING ========= //

console.log(nombre.length) //cantidad de posiciones o caracteres

console.log(nombre.replace('jose','Joseignacioo'))  //remplazar

console.log(nombre.repeat(3))

console.log(`Hola mi nombre es: ${nombre}, Mi edad es: ${edad} años, Mido: ${tamaño} y soy hombre: ${sexo}`)

  

// ========= SUMAR STRING ========= //

let string1 = '1'

let string2 = '2'

let resultado = Number(string1) + Number(string2)

console.log(resultado)

  

// =========  DESPLAZAR A LA IZQUIERDA ========= //

let usuario="   Joseignacioo"

console.log(usuario)

console.log(usuario.trim())

  

// ========= OPERACIONES ========= //

let numero1 = 2

let numero2 = 5

let total = numero1 + numero2

console.log(total) // total en variable

  

console.log(numero1 + numero2) // SUMA

console.log(numero1 - numero2) // RESTA

console.log(numero1 * numero2) // MULTIPLICACION

console.log(numero1 / numero2) // DIVISION

console.log(numero1 % numero2) // MODULO

  

// =========  ========= //

console.log(numero1 > numero2) // MAYOR A

console.log(numero1 < numero2) // MENOR A

console.log(numero1 >= numero2) // MAYOR IGUAL A

console.log(numero1 <= numero2) // MENOR IGUAL A

console.log(numero1 == numero2) // IGUAL A

console.log(numero1 != numero2) // DISTINTO A

  

// ========= ARRAY ========= //

console.log(Array.from(nombre))

  

let vocales = ['a','o','i','e','u'] // == [0, 1, 2, 3, 4]

console.log(vocales) // IMPRIMIR ARRAY

console.log(vocales[2]) // BUSCAR LA POSICION

console.log(vocales.sort()) // ORDENAR DE VALOR UNICODE

console.log(vocales.forEach((elemento) => console.log(elemento))) // HACER RECORRIDOS A LA ARRAY

  

let palabras = ['Hola','Como estas', 'Bien y tu?']

console.log(palabras.some(palabra => palabra.length > 8)) // TODAS LAS PALABRAS TIENEN MENOR A 8 CARACTERES

console.log(palabras.every(palabra => palabra.length > 8)) // TODAS LAS PALABRAS TIENEN MAYOR A 8 CARACTERES

  

let numeros = [1,2,3,4,5]

console.log(numeros.map(numero => numero * 2)) // (SUMAR, RESTAR, MULTIPLICAR, DIVIDIR Y MODULO) CADA NUMERO DEL ARRAY CON 2

console.log(numeros.filter(numeros => numeros > 3)) // FILTRAR LOS NUMEROS (MAYOR, MENOR, MAYOR IGUAL, MENOR IGUAL, IGUAL A, DISTINTO) A 3

console.log(numeros.reduce((a,b)=> a+b)) // (SUMAR, RESTAR, MULTIPLICAR, DIVIDIR Y MODULO) DE TODOS LOS NUMEROS DEL ARRAY

  
  

// ========= CONDICINALES ========= //

//CONDICIONALES ANIDADAS

let a = 7

let b = 4

let c = 2

if(a > b){

    console.log("a es mayor")

}else if(a == b){

    console.log("a y b son iguales")

}else{

    console.log("b  es mayor")

}

//CONDICIONALES SWITCH

let pais = 'peru'

switch(pais){ // ES IGUAL A

    case 'peru':

        console.log("eres peruano")

        break;

    case 'Venezuela':

        console.log("eres Venezolano")

        break;

    default:

        console.log("no existe el pais")

}