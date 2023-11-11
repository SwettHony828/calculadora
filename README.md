#include <stdio.h>

int a,b,r; //declaramos las variables de manera globar "a","b" y "r" para todas las operaciones siendo "r" el resultado y "a","b" los numeros a evaluar
int opcion; //declaramos la variable de manera "opcion" como una bandera para seguir haciendo operaciones (1) o terminar el progeama (0)
double n,d,res; //declaramos las varibles de manera global "n","d" y "res" para la divicion, siento "n" el dividendo, "d" el divisor y "res" el resutado
int operador; //declaramos una variable tipo entera "operador" para que le usuario ingrese el numero de la operacion que quiera calcular y el switch pueda leerlo
double result[100];

int main(){
    //"menu"
    printf("Elige la operacion que quieras hacer:\n\n1. + (suma)\n2. - (resta)\n3. * (multiplicacion)\n4. / (divicion)\n\n"); // Le enseñamos al usuario las operaciones que puede calcular con este programa
    printf("Escribe el numero de la operacion: "); //pedimos al usuario que ingrese el numero con el que esta indicado la operacion que quiera realizar
    scanf("%d",&operador); //guardamos el valor ingresado en la variable "operador"

    //desarrollo de operaciones
    switch (operador){ //usamos un switch para las 4 diferentes operaciones
        case 1: //el caso 1 es la suma
            suma(a,b,r); //llamamos a la funcion "suma" para que realice una suma
            printf("\nFin del programa.");
            break;
        case 2: //el caso 2 es la resta
            resta(a,b,r); //llamamos a la funcion "resta" para que realise una resta
            printf("\nFin del programa.");
            break;
        case 3: //el caso 3 es la multiplicacion
            multiplicacion(a,b,r); //llamamos a la funcion "multiplicacion" para que realice una multiplicacion
            printf("\nFin del programa.");
            break;
        case 4: //el caso 4 es para la divicion
            divicion(n,d,res); //llamamos a la funcion "divicion" para que realice una divicion
            printf("\nFin del programa.");
            break;
        default: // el default es por si ingresa algun otro numero que no salga en el "menu"
            printf("Seleciona una operacion de las antes mencionadas!"); //imprime que ingrese un numero que este dentro del menu
            break;
    }
    return 0;
}

void suma(a,b,r){ //creamos una funcion tipo void para la suma
    if(r != 0){ //creamos una restriccion la cual dice que si "r" es desigual a 0 (tiene algun valor) se hace:
        a=r, b=0, r=0; //la variable "a" toma el valor de "r", a "b" se le quita el valor que tenia al igual que a "r" para poder seguir haciendo operaciones

        printf("\nEscribe el numero que quieras sumar: "); //solicitamos al usuario que ingrese un nuevo numero a sumar al resultado anterior
        scanf("%d",&b); //guardamos el valor ingresado en la variable tipo global "b"

        r=a+b; //hacemos la operacion 

        printf("\n%d + %d = %d\n\n",a,b,r); //E imprimimos la operacion con el resultado anterior y el nuevo numero, con su resultado correspondiente
        return 0;
    } //si no se cumple continua el programa

    printf("\nEscribe dos numeros que quieras sumar: "); //pedimos al usuario que ingrese los dos numeros que quiera sumar
    scanf("%d",&a), scanf("%d",&b); //los guardamos en las variables tipo global "a" y "b" 

    r = a + b; //realizamos la operacion y el resultado lo guardamos en la variable tipo global "r"

    printf("\n%d + %d = %d\n\n",a,b,r); //imprimimos la operacion completa con su resultado

    do{ //creamos un ciclo que hace:
        printf("Preciona 1 si quieres seguir sumando, 0 si quieres terminar o 2 si quieres hacer otra operacion con el resultado dado: "); //pregunta al usuario si quiere seguir sumando o terminar el programa
        scanf("%d",&opcion); //guarda el numero seleccionado en la varible tipo global "opcion"

        if(opcion == 1){ //creamos una restriccion donde si "opcion" es desigual a 0 haga:
            a = r, b = 0 ,r = 0; //la variable "a" se le asigna el valor de "r", a "b" se le quita el valor que tenia al igual que a "r" para poder seguir sumando

            printf("\nEscribe otro numero a sumar: "); //solicitamos al usuario ingrese otro numero a sumar
            scanf("%d",&b); //guardamos el valor ingresado en la variable "b" antes restablecida

            r = a + b; //hacemos la operacion

            printf("\n%d + %d = %d\n\n",a,b,r); //E imprimimos la operacion con el resultado anterio y el numero nuevo, con su resultado correspondiente
        }

        if(opcion == 2){ //creamos una restriccion donde si "opcion" es 2 haga:
            printf("\nSelecciona la operacion que quieras hacer: "); //soliciramos al usuario seleccionar alguna operacion que quiera hacer con el resultado obtenido
            scanf("%d",&operador); //guardamos el valor en la variable "operador" para despues pasar al switch 

            switch (operador){ //usamos un switch para las 4 diferentes operaciones
                case 1: //el caso 1 es la suma
                    suma(a,b,r); //llamamos a la funcion "suma" para que realice una suma
                    break;
                case 2: //el caso 2 es la resta
                    resta(a,b,r); //llamamos a la funcion "resta" para que realise una resta
                    break;
                case 3: //el caso 3 es la multiplicacion
                    multiplicacion(a,b,r); //llamamos a la funcion "multiplicacion" para que realice una multiplicacion
                    break;
                case 4: //el caso 4 es para la divicion
                    divicion(n,d,res); //llamamos a la funcion "divicion" para que realice una divicion
                    break;
                default: // el default es por si ingresa algun otro numero que no salga en el "menu"
                    printf("\nSeleciona una operacion de las antes mencionadas!\n"); //imprime que ingrese un numero que este dentro del menu
                    break;
            }
        }
    } while (opcion == 1||opcion == 2); //el ciclo se repite mientras "opcion" sea desigual a 0, en el caso que sea igual a 0 se termina el ciclo
}

void resta(a,b,r){ //creamos una funcion tipo void para la resta
    if(r != 0){ //creamos una restriccion la cual dice que si "r" es desigual a 0 (tiene algun valor) se hace:
        a=r, b=0, r=0; //la variable "a" toma el valor de "r", a "b" se le quita el valor que tenia al igual que a "r" para poder seguir haciendo operaciones

        printf("\nEscribe el numero que quieras restar: "); //solicitamos al usuario que ingrese un nuevo numero a restar al resultado anterior
        scanf("%d",&b); //guardamos el valor ingresado en la variable tipo global "b"

        r=a-b; //hacemos la operacion 

        printf("\n%d - %d = %d\n\n",a,b,r); //E imprimimos la operacion con el resultado anterior y el nuevo numero, con su resultado correspondiente
        return 0;
    }//si no se cumple continua el programa

    printf("\nEscribe dos numeros que quieras restar: "); //solicitamos al usuario ingresar dos numeros que quiera restar
    scanf("%d",&a), scanf("%d",&b); //guardamos los valores ingresados en las variables tipo global "a" y "b"

    r = a - b; //hacemos la operacion

    printf("\n%d - %d = %d\n\n",a,b,r); //E imprimimos la operacion con su resultado

    do{ //creamos un ciclo que hace:
        printf("Preciona 1 si quieres seguir restando, 0 si quieres terminar o 2 si quieres hacer otra operacion con el resultado dado: "); //pregunta al usuario si quiere segir restando o terminar el programa
        scanf("%d",&opcion); //guardamos el numero seleccionado en la variable tipo global "opcion"

        if (opcion == 1){ //creamos una restriccion donde si "opcion" es desigual a 0 haga:
            a = r, b = 0, r = 0; //la variable "a" toma el valor de "r", a "b" se le quita el valor que tenia al igual que a "r" para poder seguir restando

            printf("\nEscribe otro numero a restar: "); //solicitamos al usuario ingresar un nuevo numero a restar
            scanf("%d",&b); //guardamos el valor ingresado en la variable tipo globarl "b"

            r = a - b; //hacemos la operacion

            printf("%d - %d = %d\n\n",a,b,r); //E imprimimos la operacion con el resultado anterior y el numero nuevo, con su resultado correspondiente
        }
        
        if(opcion==2){ //creamos una restriccion donde si "opcion" es 2 haga:
            printf("\nSelecciona la operacion que quieras hacer: "); //soliciramos al usuario seleccionar alguna operacion que quiera hacer con el resultado obtenido
            scanf("%d",&operador); //guardamos el valor en la variable "operador" para despues pasar al switch 

            switch (operador){ //usamos un switch para las 4 diferentes operaciones
                case 1: //el caso 1 es la suma
                    suma(a,b,r); //llamamos a la funcion "suma" para que realice una suma
                    break;
                case 2: //el caso 2 es la resta
                    resta(a,b,r); //llamamos a la funcion "resta" para que realise una resta
                    break;
                case 3: //el caso 3 es la multiplicacion
                    multiplicacion(a,b,r); //llamamos a la funcion "multiplicacion" para que realice una multiplicacion
                    break;
                case 4: //el caso 4 es para la divicion
                    divicion(n,d,res); //llamamos a la funcion "divicion" para que realice una divicion
                    break;
                default: // el default es por si ingresa algun otro numero que no salga en el "menu"
                    printf("Seleciona una operacion de las antes mencionadas!"); //imprime que ingrese un numero que este dentro del menu
                    break;
            }
        } 
    } while (opcion == 1||opcion ==2); //el ciclo se repite mientras "opcion" sea desigual a 0, en el casi que sea igual a 0 se termina el ciclo
}

void multiplicacion(a,b,r){ //creamos una funcon tipo void para la multiplicacion
    if(r != 0){ //creamos una restriccion la cual dice que si "r" es desigual a 0 (tiene algun valor) se hace:
        a=r, b=0, r=0; //la variable "a" toma el valor de "r", a "b" se le quita el valor que tenia al igual que a "r" para poder seguir haciendo operaciones

        printf("\nEscribe el numero que quieras multiplicar: "); //solicitamos al usuario que ingrese un nuevo numero a multiplicar al resultado anterior
        scanf("%d",&b); //guardamos el valor ingresado en la variable tipo global "b"

        r=a+b; //hacemos la operacion 

        printf("\n%d * %d = %d\n",a,b,r); //E imprimimos la operacion con el resultado anterior y el nuevo numero, con su resultado correspondiente
        return 0;
    } //si no se cumple continua el programa

    printf("\nEscribe dos numeros a multiplicar: "); //Solicitamos al usuario ingresar dos numeros que quiera multiplicar
    scanf("%d",&a), scanf("%d",&b); //guardamos los valores ingresados en las variables tipo global "a" y "b"

    r = a * b; //hacemos la operacion

    printf("\n%d * %d = %d\n\n",a,b,r); //E imprimimos la operacion con su resultado

    do{ //creamos un ciclo que hace:
        printf("Preciona 1 si quieres seguir multiplicando o 0 si quieres terminar: "); //pregunta al usuario si quiere seguir multiplicando o terminar el programa
        scanf("%d",&opcion); //guardamos el numero seleccionado en la variable tipo global "opcion"

        if(opcion !=0){ //creamos una restriccion donde si "opcion" es desigual a 0 haga:
            a = r, b = 0, r = 0; //la variable "a" toma el valor de "r", a "b" se le quita el valor que tenia al igual que a "r" para poder seguir multiplicando

            printf("\nEscribe otro numero a multiplicar: "); //solicitamos al usuario ingresar un nuevo numero a multiplicar
            scanf("%d",&b); //guardamos el valor ingresado en la variable tipo global "b"

            r = a * b; //hacemos la operacion

            printf("\n%d * %d = %d\n\n",a,b,r); //E imprimimos la operacion con el resultado anterio y el nuevo numero, con su resultado correspondiente
        }
    } while (opcion != 0); //el ciclo se repite mientras "opcion" sea desigual a 0, en el caso que sea igual a 0 se termina el ciclo
}

void divicion(n,d,res){ //creamos una funcion tipo void para la divicion
    printf("\nEscribe dos numeros a dividir de la forma a/b\n\n "); //solicitamos al usuario ingresar dos numeros que quiera dividir de la forma a/b
    printf("a: "); //Esperamos al numero a
    scanf("%d",&n); //guardamos el valor ingresado en la variable tipo global "n"
    printf("b: "); //Esperamos al numero b
    scanf("%d",&d); //guardamos el valor ingresado en la variable tipo global "d"

    if(d==0){ //creamos una concidion la cual dice que si b==0 es verdadero:
        printf("\n%d / %d = 0\n\n",n,d); //Imprime como quedaria la divicion ya que el programa por si solo explota
        printf("Fin del programa."); //finalizamos el programa
    } //si no se cumple continua el programa

    res = n / d; //hacemos la operacion

    printf("%d / %d = %d\n\n",n,d,res); //E imprimimos la operacion y su resultado

    do{ //creamos un ciclo que hace:
        printf("Preciona 1 si quieres seguir dividiendo o 0 si quieres terminar: "); //preguntamos al usuario si quiere segiur dividiendo o terminar el programa
        scanf("%d",&opcion); //guardamos el numero seleccionado en la variable tipo global "opcion"

        if(opcion != 0){ //creamos una restriccion donde si "opcion" es desigual a 0 haga:
            n = res, d = 0, res = 0; //la variable "a" toma el valor de "r", a "b" se le quita el valor que tenia al igual que a "r" para poder seguir dividiendo 

            printf("\nEscribe otro numero a dividir: "); //solicitamos al usuario ingresar un nuevo numero a dividir
            scanf("%d",&d); //guardamos el valor ingresado en la variable tipo global "b"

            res = n / d; //hacemos la operacion

            printf("%d / %d = %d\n\n",n,d,res); //E imprimimos la operacion con el resutado anterior y el nuevo numero, con su resultado correspondiente
        }
    } while(opcion != 0); //el ciclo se repite mientras "opcion" sea desigual a 0, en el caso que sea igual a 0 se termina el ciclo
}
