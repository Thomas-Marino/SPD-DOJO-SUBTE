## Proyecto: Ejercicio Estación de subte.
![image](https://user-images.githubusercontent.com/123998550/236382774-8d0191d8-7a0f-4903-850e-6c28476cd636.png)
## Descripción
La empresa  “UTN FRA Robotics” ganó la licitación de un proyecto, y deberá Implementar un sistema que permita al usuario saber a qué estación de subte está llegando, aparte  el sistema muestra las estaciones que faltan hasta llegar a destino. 
**Para ello se utilizaron:**
- 4 LEDs los cuales indican la estación en la que se encuentra el subte.
- Un display de 7 segmentos el cual indica las estaciones que faltan para llegar al fin del recorrido.
- Un buzzer el cual emite un sonido diferente cada vez que se llegue a una estación.
- Un pulsador el cual dará inicio al sistema.

## Función principal
~~~ C (lenguaje en el que esta escrito)
void ejecutar_proceso()
{
  contador = 3;
  while(contador > -1)
  {
    encender_numero(contador);
    encender_buzzer(contador);
    encender_led(contador);
    apagar_led();
    delay(2500);
    contador -= 1;
  }
  apagar_numero();
  apagar_led();
}
~~~
"ejecutar_proceso" Es la función principal del código. Esta función engloba otras 5 funciones, las cuales se encargan de:
- Encender las luces led y mostrar un mensaje por consola.
~~~ C (lenguaje en el que esta escrito)
void encender_led(int numero_ingresado)
{
  apagar_led();
  switch(numero_ingresado)
  {
    case 0:
    digitalWrite(LED_MORENO, HIGH);
    Serial.println("\n\n\n\n\n\nUsted se encuentra en la estacion: Moreno.");
    delay(2750);
    Serial.println("\n\n\nFin del recorrido.\n\n\n");
    delay(1750);
    break;
    case 1:
    digitalWrite(LED_INDEPENDENCIA, HIGH);
    Serial.println("\n\n\n\nUsted se encuentra en la estacion: Independencia.\n\n");
    delay(2750);
    Serial.println("\nProxima estacion: Moreno.\n\n\n");
    delay(1750);
    break;
    case 2:
    digitalWrite(LED_SAN_JUAN, HIGH);
    Serial.println("\n\n\n\nUsted se encuentra en la estacion: San Juan.\n\n");
    delay(2750);
    Serial.println("\nProxima estacion: Independencia.\n\n\n");
    delay(1750);
    break;
   	case 3:
    digitalWrite(LED_CONSTITUCION, HIGH);
    Serial.println("Usted se encuentra en la estacion: Constitucion.\n\n");
    delay(2750);
    Serial.println("\nProxima estacion: San Juan.\n\n\n");
    delay(1750);
    break; 
  }
}
~~~
- Apagar las luces led.
~~~ C (lenguaje en el que esta escrito)
void apagar_led()
{
  digitalWrite(LED_CONSTITUCION, LOW);
  digitalWrite(LED_SAN_JUAN, LOW);
  digitalWrite(LED_INDEPENDENCIA, LOW);
  digitalWrite(LED_MORENO, LOW);
}
~~~
- Encender un numero del display.
~~~ C (lenguaje en el que esta escrito)
void encender_numero(int numero_ingresado)
{
  apagar_numero(); 
  delay(500);
  switch (numero_ingresado)
  {
    case 0: 
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH); 
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(F, HIGH);
    break;
    case 1:
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH); 
    break;
    case 2:
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(A, HIGH);
    break;
    case 3:
    digitalWrite(D, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(A, HIGH);
    break;
 }
}
~~~
- Apagar el display.
~~~ C (lenguaje en el que esta escrito)
void apagar_numero()
{
  digitalWrite(A, LOW);
  digitalWrite(B, LOW); 
  digitalWrite(C, LOW);
  digitalWrite(D, LOW);
  digitalWrite(E, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, LOW);
}
~~~
- Encender el buzzer.
~~~ C (lenguaje en el que esta escrito)
void encender_buzzer(int numero_ingresado)
{
  switch(numero_ingresado)
  {
    case 0:
  	tone(BUZZER, 500, 2000);
	  break;
    case 1:
    tone(BUZZER, 600, 2000);
    break;
    case 2:
    tone(BUZZER, 700, 2000);
    break;
    case 3:
    tone(BUZZER, 800, 2000);
    break;
  }
}
~~~
## Link del proyecto
- [Proyecto]([https://www.tinkercad.com/things/h1WbVGTJFAf](https://www.tinkercad.com/things/jwLanq90ugF?sharecode=qjR0xr0JkpMdTUO0G1S-HGmK9aLYQNsIB3QFb6Z5VfQ)
