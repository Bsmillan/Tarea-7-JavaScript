# JAVASCRIPT

## Tarea 7
### Brahiam Steven Millan Arias - Luis Fernando Mazo Canas

## Ejercicio 1
Crear un método constructor llamada persona. Sus atributos son: nombre, edad y cedula. Construye los siguientes métodos para la clase:
### 1.1
mostrar(): Muestra los datos de la persona.
### 1.2
es_mayor_de_edad(): Devuelve un valor lógico indicando si es mayor de edad.

### Código
```javascript
class Persona{
    constructor(nombre_ingresado, edad_ingresada, cedula_ingresada){
        this.nombre = nombre_ingresado;
        this.edad = edad_ingresada;
        this.cedula = cedula_ingresada;
    }
    mostrar(){
        console.log(this.nombre, this.edad, this.cedula);
    }
    es_mayor_de_edad(){
        if(this.edad>=18){
            return `verdadero`;
        }
        else{
            return `falso`
        }
    }
}
let persona1 = new Persona("Brahiam", 29, 1053820080);
const persona2 = new Persona("Steven", 15, 1053820080);

persona1.mostrar();
persona2.mostrar();
persona1.es_mayor_de_edad();
persona2.es_mayor_de_edad();
```

## Ejercicio 2
Crea un método constructor llamado cuenta que tendrá los siguientes atributos: titular (que es nombre de la persona) y cantidad.
El titular será obligatorio y la cantidad es opcional. Construye los siguientes métodos para el método:

### 2.1
mostrar(): Muestra los datos de la cuenta.
### 2.2
ingresar(cantidad): se ingresa una cantidad a la cuenta, si la cantidad introducida es negativa, no se hará nada.
### 2.3
retirar(cantidad): se retira una cantidad a la cuenta. La cuenta puede estar en números rojos.

### Código
```javascript
class Cuenta{
    constructor(titular, cantidad){
        this.titular = titular;
        this.cantidad = cantidad;
    }
    mostrar(){
        console.log(this.titular, this.cantidad);
    }
    ingresar(cantidadi){
        if(cantidadi>0){
            this.cantidad = this.cantidad + cantidadi;
        }
    }
    retirar(cantidadr){
        this.cantidad = this.cantidad-cantidadr;
    }
}

let cuenta1 = new Cuenta("Brahiam",0);
let cuenta2 = new Cuenta("Luis", 10000);

cuenta1.mostrar();
cuenta2.mostrar();
cuenta1.ingresar(10000);
cuenta1.mostrar();
cuenta2.retirar(5000);
cuenta2.mostrar();
```

## Ejercicio 3
Crear un método constructor llamado formulas. Construye los siguiente métodos para la clase:

### 3.1
 sumar(entero, entero)
### 3.2
 fibonacci(cantidad) a partir de una entero sacar los números
### 3.3
 operacion_modulo(cantidad) a partir de una cantidad mostrar cuales dan residuo 0
### 3.4
 primos(cantidad) a partir de una cantidad mostrar cuales son numeros primos

### Código
```javascript
class Formulas{
    constructor(suma, fibonacci, modulo, primo){
        this.suma = suma;
        this.fibonacci = fibonacci;
        this.modulo = modulo;
        this.primo = primo;
    }
    sumar(ent1, ent2){
        this.suma = "El resultado de la suma es: " + (ent1 + ent2);
        console.log(this.suma);
    }

    fibonaccii(ent1){
        let resultado=[0,1];
        for(let i = 2; i < ent1; i++){
            resultado[i] = resultado[i - 2] + resultado[i - 1];
            this.fibonacci = "El resultado es: " + resultado;
        }
        console.log(this.fibonacci);
    }

    modulos(ent1, ent2){
        this.modulo = ent1 % ent2;
        console.log(this.modulo);
    }

    primos(ent1){
        let primos = [];
        let hayPrimo = [];

        for(let i = 1; i <= ent1 + 1; i++){
            hayPrimo.push(true);
        }

        for(let i = 2; i <= ent1; i++){
            if(hayPrimo[i]){
                primos.push(i);
                for(let j = 1; j * i <= ent1; j++){
                    hayPrimo[i * j] = false;
                }
            }
        }
        console.log("El resultado es: " + primos);
    }
}

let suma1 = new Formulas();
let fibonacci1 = new Formulas();
let mod1 = new Formulas();
let primos1 = new Formulas();

suma1.sumar(5,10);
fibonacci1.fibonaccii(10);
mod1.modulos(10,2);
primos1.primos(11);
```

## Ejercicio 4
Crear un método constructor llamado persona. Sus atributos son: nombre, edad, DNI, sexo (H hombre, M mujer), peso y altura Construye los siguiente métodos para la clase:

### 4.1
 calcularIMC(): calculara si la persona esta en su peso ideal (peso en kg/(altura^2 en m)), si esta fórmula devuelve un valor menor que 20, la función devuelve un -1, si devuelve un número entre 20 y 25 (incluidos), significa que esta por debajo de su peso ideal la función devuelve un 0 y si devuelve un valor mayor que 25 significa que tiene sobrepeso, la función devuelve un 1. Te recomiendo que uses constantes para devolver estos valores.
### 4.2
 esMayorDeEdad(): indica si es mayor de edad, devuelve un booleano.
### 4.3
 comprobarSexo(char sexo): comprueba que el sexo introducido es correcto. Si no es correcto, será H.

### Código
```javascript
class Persona{
    constructor(imc,edad,sexo){
        this.imc = imc;
        this.edad = edad;
        this.sexo = sexo;
    }
    calcularImc(peso_ingresado,altura_ingresada){
        this.imc = (peso_ingresado/(altura_ingresada*altura_ingresada));
        console.log(this.imc );
        if(this.imc > 20 && this.imc < 25){
            console.log("0");
        }else if(this.imc >= 25){
            console.log("1");
        }else if(this.imc < 20){
            console.log("-1");
        }
    }
    esMayorDeEdad(edad){
        if(edad>= 18){
            return `verdadero`;
        }else{
            return `Falso`;
        }
    }
    comprobarSexo(sexo){
        if(sexo = "M"){
            return console.log("Sexo Masculino");
        }else{
            return console.log("Sexo Femenino");
        }
    }
}

let persona1 = new Persona();
persona1.calcularImc(150,1.65);
persona1.esMayorDeEdad(18);
persona1.comprobarSexo("M");
```

## Ejercicio 5
Crear un método constructor llamado contraseña. Sus atributos longitud y contraseña Construye los siguiente métodos para la clase:

### 5.1
 esFuerte(): devuelve un booleano si es fuerte o no, para que sea fuerte debe tener mas de 2 mayúsculas, mas de 1 minúscula y mas de 5 números.
### 5.2
 generarPassword(): genera la contraseña del objeto con la longitud que tenga.
### 5.3
 seguridadPaswword(); indicar si la contraseña es débil contiene entre 1 a 6 caracteres (caracteres números y letras), media (7 a 10 caracteres números y letras) o fuerte (11 a 20 caracteres letras y caracteres especiales)

### Código
```javascript
class Contraseña {
	constructor(longitud, password) {
		this.longitud = longitud;
		this.password = password;
	}

	esFuerte() {
		var space = false;
		var cont = 0;
		var numeros = [0,1,2,3,4,5,6,7,8,9];
		var letraMinus = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'];
		var letraMayus = ['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'];
		var caracterEsp = ['-','_','*','/'];

		while (!space && (cont<this.password.length)) {
			if (this.password.charAt(cont) == ' ') {
				space = true;
				cont++
			}
			break;
		}
		if (space) {
			console.log('La contraseña no puede tener espacios vacios ' + false);
			return false
		}
		else if (this.password.length == 0) {
			console.log('No puede estar en blanco ' + false);
			return false
		}
		else if (this.password.charAt() != numeros) {
			return console.log(false)
		}
		else if (this.password.charAt() != letraMinus) {
			return console.log(false)
		}
		else if (this.password.charAt() != letraMayus) {
			return console.log(false)
		}
		else if (this.password.charAt() != caracterEsp) {
			return console.log(false)
		}
		else {
			return console.log(true)
		}
	}

	generarPassword(longitud, tipo) {
		switch(tipo) {
			case '':
				break;
			default:
				characters = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
				break;
		}
		var pass = "";
		for (var i=0;i<longitud;i++) {
			if(tipo == '') {
				pass += String.fromCharCode((Math.floor((Math.random() * 100)) % 94) + 33);
        	}
        	else {
            	pass += characters.charAt(Math.floor(Math.random()*characters.length));
        	}
		}
		return pass
	}

	seguridadPassword() {
		if (this.password.length >= 0 && this.password.length <= 5) {
			console.log('Contraseña debil');
		}
		else if (this.password.length >= 7 && this.password.length <= 10) {
			console.log('Contraseña media');
		}
		else if (this.password.length >= 11 && this.password.length <= 20) {
			console.log('Contraseña fuerte');
		}
		else {
			console.log('No puede tan grande');
		}
	}
}

const contra = new Contraseña;

var contraseñaNueva = 'Juan1256/*/';
var longitudNueva = 15;
contra.password = contraseñaNueva;
contra.longitud = longitudNueva;

contra.esFuerte();
contra.generarPassword(longitudNueva, '');
contra.seguridadPassword();
```

## Ejercicio 6
Implementar un objeto que modele un contador. Un contador se puede incrementar o decrementar, recordando el valor actual. Al resetear un contador, se pone en cero.
Además es posible indicar directamente cual es el valor actual. Este objeto debe entender los siguientes mensajes:

### 6.1
 reset()
### 6.2
 inc()
### 6.3
 dec()
### 6.4
 valorActual()
### 6.5
 valorActual(nuevoValor) P.ej. si se evalúa la siguiente secuencia contador.valorActual(10) contador.inc() contador.inc() contador.dec() contador.inc() contador.valorActual() el resultado debe ser 12.

### Código
```javascript
class Contador{
    reset(){
        this.numero = 0;
    }
    inc(){
        this.numero ++;
    }
    dec(){
        this.numero --;
    }
    valorActual(ent1){
        if(ent1 != null) {
            this.numero = ent1;
        }else{
            console.log(this.numero);
        }
    }
}

let contador1 = new Contador();
contador1.reset();
contador1.valorActual(20);
contador1.inc();
contador1.inc();
contador1.dec();
contador1.inc();
contador1.valorActual();
```

## Ejercicio 7
Agregar al contador del ejercicio 6, la capacidad de recordar un String que representa el último comando que se le dio. Los Strings posibles son "reset", "incremento", "decremento" o "actualización" (para el caso de que se invoque valorActual con un parámetro). Para saber el último comando, se le envía al contador el mensaje ultimoComando().
En el ejemplo del ejercicio 3, si luego de la secuencia indicada se evalúa contador.ultimoComando() el resultado debe ser "incremento"

### Código
```javascript
class Contador{
    constructor(id){
        this.id = id;
    }
    reset(){
        this.numero = 0;
        this.id=0;
    }
    inc(){
        this.numero ++;
        this.id=1;
    }
    dec(){
        this.numero --;
        this.id=2;
    }
    valorActual(ent1){
        this.id=3;
        if(ent1 != null) {
            this.numero = ent1;
        }else{
            console.log(this.numero);
        }
    }
    ultimoComando(){
        let day;
        switch(this.id){
            case 0:
                day = "Reset";
                break;
            case 1:
                day = "Incremento";
                break;
            case 2:
                day = "Decremento";
                break;
            case 3:
                day = "Actualizacion";
                break;
        }
        console.log(day);
    }
}

let contador1 = new Contador();
contador1.reset();
contador1.valorActual(20);
contador1.inc();
contador1.inc();
contador1.dec();
contador1.inc();
contador1.valorActual();
contador1.inc();
contador1.ultimoComando();
```

## Ejercicio 8
Implementar un objeto que modele a Chimuela, una dragona de la que nos interesa saber qué energía tiene en cada momento, medida en Joules. En el método constructor simpli�cado que nos piden implementar, las únicas acciones que vamos a contemplar son: cuando Chimuela come una cantidad de comida especi�cada en gramos, en este caso adquiere 4 joules por cada gramo, y cuando Chimuela vuela una cantidad de kilómetros, en este caso gasta un joule por cada kilómetro, más 10 joules de �costo �jo� de despegue y aterrizaje. La energía de Chimuela nace en 0. El objeto que implementa este metodo constructor de Chimuela, debe entender los siguientes mensajes:

### 8.1
 comer(gramos)
### 8.2
 volar(kilómetros)
### 8.3
 energia() P.ej. si sobre un REPL(Read-Eval-Print-Loop)(Lectura-Evaluación-Impresión) recién lanzado se evalúa la siguiente secuencia 
 Chimuela.comer(100)
 Chimuela.volar(10)
 Chimuela.volar(20)
 Chimuela.energia() el resultado debe ser 350.

### Código
```javascript
class Dragon {
	constructor(energia) {
		this.energia = energia;
	}

	comer(comida) {
		var resulEnergia = comida*4
		this.energia = resulEnergia;
		return this.energia
	}

	volar(distancia) {
		var resulDist = 0;
		if (distancia > this.energia) {
			console.log('Chimuela no puede volar');
		}
		else {
			resulDist = this.energia-distancia-10;
			this.energia = resulDist;
		}
		return this.energia
	}

	energy() {
		console.log('La energia de Chimuela es: ' + this.energia);
	}
}

const chimuela = new Dragon(0)

chimuela.comer(100);
chimuela.volar(10);
chimuela.volar(20);
chimuela.energy();

```

## Ejercicio 9
Agregar al método constructor de Chimuela del ejercicio 8, la capacidad de entender estos mensajes:

### 9.1
estaDebil(), Chimuela está débil si su energía es menos de 50.
### 9.2
estaFeliz(), Chimuela está feliz si su energía está entre 500 y 1000.
### 9.3
cuantoQuiereVolar(), que es el resultado de la siguiente cuenta. De base, quiere volar (energía / 5) kilómetros, p.ej., si tiene 120 de energía, quiere volar 24 kilómetros. Si la energía está entre 300 y 400, entonces hay que sumar 10 a este valor, y si es múltiplo de 20, otros 15. Entonces, si Chimuela tiene 340 de energía, quiere volar 68 + 10 + 15 = 93 kilómetros. Para probar esto, sobre un REPL recién lanzado darle de comer 85 a Chimuela, así la energía queda en

### Código
```javascript
class Dragon {
	constructor(energia) {
		this.energia = energia;
	}

	comer(comida) {
		var resulEnergia = comida*4
		this.energia = resulEnergia;
		return this.energia
	}

	volar(distancia) {
		var resulDist = 0;
		if (distancia > this.energia) {
			console.log('Chimuela no puede volar');
		}
		else {
			resulDist = this.energia-distancia-10;
			this.energia = resulDist;
		}
		return this.energia
	}

	energy() {
		console.log('La energia de Chimuela es: ' + this.energia + ' Joules');
	}

	estaDebil() {
		if (this.energia < 50) {
			console.log('Chimuela esta debil');
		}
		else {
			console.log('Chimuela esta bien');
		}
	}

	estaFeliz() {
		if (this.energia >= 500 && this.energia <= 1000) {
			console.log('Chimuela esta feliz');
		}
		else {
			console.log('Chimuela esta bien');
		}
	}

	cuantoQuiereVolar() {
		var resulCuenta = this.energia/5;
		if (this.energia >= 300 && this.energia <= 400) {
			resulCuenta = resulCuenta + 10;
		}
		if (this.energia%20 == 0) {
			resulCuenta = resulCuenta + 15;
		}
		console.log('Quiere volar '+ resulCuenta + ' Km')
	}
}

const chimuela = new Dragon(0)

chimuela.comer(162);
chimuela.volar(20);
chimuela.volar(50);
chimuela.energy();
chimuela.estaDebil();
chimuela.estaFeliz();
chimuela.cuantoQuiereVolar();
```

## Ejercicio 10
Para saber si n es múltiplo de 20 hacer: n % 20 == 0. Probarlo en el REPL(Read-Eval-Print-Loop)(Lectura-Evaluación-Impresión)
Implementar un objeto que represente una calculadora sencilla, que permita sumar, restar y multiplicar. Este objeto debe entender los siguientes mensajes:

### 10.1
cargar(numero)
### 10.2
sumar(numero)
### 10.3
restar(numero)
### 10.4
multiplicar(numero)
### 10.5
valorActual()
P.ej. si se evalúa la siguiente secuencia
calculadora.cargar(0)
calculadora.sumar(4)
calculadora.multiplicar(5)
calculadora.restar(8)
calculadora.multiplicar(2)
alculadora.valorActual() el resultado debe ser 24.

### Código
```javascript
class calculadora{
    constructor(carga,suma,resta,multiplicacion,valorActual){
        this.carga=carga;
        this.suma=suma;
        this.resta=resta;
        this.multiplicacion=multiplicacion;
        this.valorActual=valorActual;
    }
    cargar(ent1){
        this.resultado = ent1;
    }
    sumar(ent2){
        this.resultado = this.resultado + ent2;
    }
    restar(ent2){
        this.resultado =this.resultado - ent2;
    }
    multiplicar(ent2){
        this.resultado = this.resultado* ent2;
    }
    valorActuali(){
        console.log(this.resultado);
    }
}

calc = new calculadora();
calc.cargar(0);
calc.sumar(4);
calc.multiplicar(5);
calc.restar(8);
calc.multiplicar(2);
calc.valorActuali();
```

## Ejercicio 11
Crear un método constructor llamado Libro. Sus atributos título del libro, autor, número de ejemplares del libro y número de ejemplares prestados los siguiente métodos para la clase:

### 11.1
prestamo() que incremente el atributo correspondiente cada vez que se realice un préstamo del libro. No se podrán prestar libros de los que no queden ejemplares disponibles para prestar. Devuelve true si se ha podido realizar la operación y false en caso contrario.
### 11.2
devolucion() que decremente el atributo correspondiente cuando se produzca la devolución de un libro. No se podrán devolver libros que no se hayan prestado. Devuelve true si se ha podido realizar la operación y false en caso contrario.
### 11.3
toString() para mostrar los datos de los libros.

### Código
```javascript
class Libro{
    constructor(tituloLibro, autorLibro, numEjemplares, numEjemplaresPrestamo){
        this.titulo = tituloLibro;
        this.autor = autorLibro;
        this.ejemplares = numEjemplares;
        this.ejemplaresPrestamo = numEjemplaresPrestamo;
    }
    prestamo(){
        if(this.ejemplares>=1){
            this.ejemplaresPrestamo ++;
            this.ejemplares --;
            console.log(true);
        }else{
            console.log(false);
        }
    }
    devolucion(){
        if(this.ejemplares>=1 || this.ejemplaresPrestamo>=1){
            this.ejemplaresPrestamo --;
            this.ejemplares ++;
        }
    }
    toString(){
        console.log(
            this.titulo,
            this.autor,
            this.ejemplares,
            this.ejemplaresPrestamo
        );
    }
}

let libro1 = new Libro("Jasperucita", "Luis Mazo", 1, 0);
libro1.prestamo();
libro1.prestamo();
libro1.devolucion();
libro1.toString();
```

## Ejercicio 12
Se está pensando en el diseño de un juego que incluye la nave espacial Enterprise. En el juego, esta nave tiene un nivel de potencia de 0 a 100, y un nivel de coraza de 0 a 20. La Enterprise puede encontrarse con una pila atómica, en cuyo caso su potencia aumenta en 25. encontrarse con un escudo, en cuyo caso su nivel de coraza aumenta en 10. recibir un ataque, en este caso se especifican los puntos de fuerza del ataque recibido. La Enterprise �para� el ataque con la coraza, y si la coraza no alcanza, el resto se descuenta de la potencia. P.ej. si la Enterprise con 80 de potencia y 12 de coraza recibe un ataque de 20 puntos de fuerza, puede parar solamente 12 con la coraza, los otros 8 se descuentan de la potencia. La nave debe quedar con 72 de potencia y 0 de coraza. Si la Enterprise no tiene nada de coraza al momento de recibir el ataque, entonces todos los puntos de fuerza del ataque se descuentan de la potencia. La potencia y la coraza tienen que mantenerse en los rangos indicados, p.ej. si la Enterprise tiene 16 puntos de coraza y se encuentra con un escudo, entonces queda en 20 puntos de coraza, no en 26. Tampoco puede quedar negativa la potencia, a lo sumo queda en 0. La Enterprise nace con 50 de potencia y 5 de coraza. Implementar este método constructor de la Enterprise, que tiene que entender los siguientes mensajes:

### 12.1
potencia()
### 12.2
coraza()
### 12.3
encontrarPilaAtomica()
### 12.4
encontrarEscudo()
### 12.5
recibirAtaque(puntos)

P.ej. sobre un REPL recién lanzado, después de esta secuencia enterprise.encontrarPilaAtomica() enterprise.recibirAtaque(14) enterprise.encontrarEscudo() la potencia de la Enterprise debe ser 66, y su coraza debe ser 10.

### Código
```javascript
class Juego {
	constructor(potencia, coraza) {
		this.potencia = potencia;
		this.coraza = coraza;
	}

	potencia() {
		if (this.potencia < 0 && this.potencia > 100) {
			console.log('La potencia no es un valor accesible');
		}
	}

	coraza() {
		if (this.coraza < 0 && this.coraza > 20) {
			console.log('La coraza no es un valor accesible');
		}
	}

	pilaAtomica() {
		var aumento = this.potencia + 25;
		if (aumento > 100) {
			aumento = 100;
		}
		this.potencia = aumento;
		return this.potencia
	}

	encontrarEscudo() {
		var corazaAumento = this.coraza + 10;
		if (corazaAumento > 20) {
			corazaAumento = 20;
		}
		this.coraza = corazaAumento;
		return this.coraza
	}

	recibirAtaque(daño) {
		var descuento;
		if (this.coraza < daño) {
			var bajo = this.coraza - daño;
			descuento = this.potencia + bajo;
			if (this.potencia == 0) {
				console.log('Game Over');
			}
			this.coraza = 0;
			this.potencia = descuento;
			return this.coraza
			return this.potencia
		}
		else {
			bajo = this.coraza - daño;
			this.coraza = bajo;
			return this.coraza
		}
	}

	mostrar() {
		console.log('La potencia actual es: ' + this.potencia);
		console.log('La coraza actual es: ' + this.coraza);
	}

}

const enterprice = new Juego(50,5);

enterprice.pilaAtomica();
enterprice.encontrarEscudo();
enterprice.pilaAtomica();
enterprice.recibirAtaque(35);
enterprice.mostrar();
```

## Ejercicio 13
Agregar al método constructor de la Enterprise del ejercicio 12, la capacidad de entender estos mensajes.

### 13.1
fortalezaDefensiva(), que es el máximo nivel de ataque que puede resistir, o sea, coraza más potencia.
### 13.2
necesitaFortalecerse(), tiene que ser true si su coraza es 0 y su potencia es menos de 20.
### 13.3
fortalezaOfensiva(), que corresponde a cuántos puntos de fuerza tendría un ataque de la Enterprise. Se calcula así: si tiene menos de 20 puntos de potencia entonces es 0, si no es (puntos de potencia - 20) / 2.

### Código
```javascript
class Juego {
	constructor(potencia, coraza) {
		this.potencia = potencia;
		this.coraza = coraza;
	}

	potencia() {
		if (this.potencia < 0 && this.potencia > 100) {
			console.log('La potencia no es un valor accesible');
		}
	}

	coraza() {
		if (this.coraza < 0 && this.coraza > 20) {
			console.log('La coraza no es un valor accesible');
		}
	}

	pilaAtomica() {
		var aumento = this.potencia + 25;
		if (aumento > 100) {
			aumento = 100;
		}
		this.potencia = aumento;
		return this.potencia
	}

	encontrarEscudo() {
		var corazaAumento = this.coraza + 10;
		if (corazaAumento > 20) {
			corazaAumento = 20;
		}
		this.coraza = corazaAumento;
		return this.coraza
	}

	recibirAtaque(daño) {
		var descuento;
		if (this.coraza < daño) {
			var bajo = this.coraza - daño;
			descuento = this.potencia + bajo;
			if (this.potencia == 0) {
				console.log('Game Over');
			}
			this.coraza = 0;
			this.potencia = descuento;
			return this.coraza
			return this.potencia
		}
		else {
			bajo = this.coraza - daño;
			this.coraza = bajo;
			return this.coraza
		}
	}

	mostrar() {
		console.log('La potencia actual es: ' + this.potencia);
		console.log('La coraza actual es: ' + this.coraza);
	}

	fortalezaDefensiva() {
		var maximo = this.potencia + this.coraza;
		console.log('La fortaleza defensiva maxima es ' + maximo);
	}

	necesitaFortalecerse() {
		if (this.potencia < 20 && this.coraza == 0) {
			console.log(true);
		}
		else {
			console.log(false);
		}
	}

	fortalezaOfensiva() {
		if (this.potencia < 20) {
			console.log('Su fortaleza ofensiva es 0');
		}
		else {
			var fuerza = (this.potencia-20)/2;
			console.log('Su fortaleza ofensiva es '+ fuerza);
		}
	}

}

const enterprice = new Juego(50,5);

enterprice.pilaAtomica();
enterprice.encontrarEscudo();
enterprice.pilaAtomica();
enterprice.recibirAtaque(35);
enterprice.mostrar();
enterprice.fortalezaDefensiva();
enterprice.necesitaFortalecerse();
enterprice.fortalezaOfensiva();
```

## Ejercicio 14
Un taller de diseño de autos quiere estudiar un nuevo prototipo. Para eso, nos piden hacer un método constructor concentrado en las características del motor. El prototipo de motor tiene 5 cambios (de primera a quinta), y soporta hasta 5000 RPM. La velocidad del auto se calcula así: (rpm / 100) * (0.5 + (cambio / 2)). P.ej. en tercera a 2000 rpm, la velocidad es 20 * (0.5 + 1.5) = 40. También nos interesa controlar el consumo. Se parte de una base de 0.05 litros por kilómetro. A este valor se le aplican los siguientes ajustes: Si el motor está a más de 3000 rpm, entonces se multiplica por (rpm - 2500) / 500. P.ej., a 3500 rpm hay que multiplicar por 2, a 4000 rpm por 3, etc. Si el motor está en primera, entonces se multiplica por 3. Si el motor está en segunda, entonces se multiplica por 2. Los efectos por revoluciones y por cambio se acumulan. P.ej. si el motor está en primera y a 5000 rpm, entonces el consumo es 0.05 * 5 * 3 = 0.75 litros/km. El método constructor debe entender estos mensajes:

### 14.1
arrancar(), se pone en primera con 500 rpm.
### 14.2
subirCambio()
### 14.3
bajarCambio()
### 14.4
subirRPM(cuantos)
### 14.5
bajarRPM(cuantos)
### 14.6
velocidad()
### 14.7
consumoActualPorKm()

### Código
```javascript
class Taller {
	constructor(cambios, revoluciones) {
		this.cambios = cambios;
		this.revoluciones = revoluciones;
	}

	arrancar() {
		var marchas = 1;
		var rev = 500;
		this.cambios = marchas;
		this.revoluciones = rev;
		console.log('El coche esta en '+ marchas + ' cambio');
		console.log('El coche esta a '+ rev +' RPM');
		return this.cambios
		return this.revoluciones
	}

	subirCambio() {
		var subirMarcha = this.cambios + 1;
		if (this.cambios > 5) {
			this.cambios = 5;
			console.log('No hay mas cambios');
		}
		else {
			this.cambios = subirMarcha;
		}
		this.revoluciones = 2000;
		return this.cambios
		return this.revoluciones
	}

	bajarCambio() {
		var bajarMarcha = this.cambios - 1;
		if (this.cambios < 0) {
			this.cambios = 0;
			console.log('No hay mas cambios');
		}
		else {
			this.cambios = bajarMarcha;
		}
		this.revoluciones = 3500;
		return this.cambios
		return this.revoluciones
	}

	subirRPM(rpmS) {
		var subirRpm = this.revoluciones + (100*rpmS);
		if(this.revoluciones > 5000) {
			this.revoluciones = 5000;
			console.log('No puede subir mas las revoluciones');
		}
		else {
			this.revoluciones = subirRpm;
		}
		return this.revoluciones
	}

	bajarRPM(rpmB) {
		var bajarRpm = this.revoluciones - (100*rpmB);
		if (this.revoluciones < 0) {
			this.revoluciones = 500;
			console.log('El coche se mantiene encendido');
		}
		else {
			this.revoluciones = bajarRpm;
		}
		return this.revoluciones
	}

	velocidad() {
		var vel = (this.revoluciones/100)*(0.5 +(this.cambios/2));
		console.log('La velocidad es '+ vel +' Km/h');
	}

	consumoActualPorKm() {
		var consumo = 0.05;
		var consumoActual;
		if (this.revoluciones >= 3000) {
			consumoActual = consumo*((this.revoluciones - 2500)/500);
			if (this.revoluciones < 4000) {
				consumoActual = consumoActual*2;
			}
			else {
				consumoActual = consumoActual*3;
			}
			console.log('El consumo actual es de '+ consumoActual +' L/Km');
		}
		else {
			console.log('El consumo actual es de '+ consumo +' L/Km');
		}
		console.log('El coche esta en '+ this.cambios);
		console.log('El coche esta a '+ this.revoluciones);
		return consumoActual
	}
}

const coche = new Taller(0,0);

coche.arrancar();
coche.subirRPM(30);
coche.subirCambio();
coche.subirRPM(30);
coche.subirCambio();
coche.subirRPM(30);
coche.subirCambio();

coche.bajarRPM(20);
coche.bajarCambio();

coche.velocidad();
coche.consumoActualPorKm();
```