# Practica-7
repositorio de los codigos de arduino usados durante la practica 7
# codigo del semáforo
Ejercicio del semaforo: 
void setup() { //Iniciamos la configuracion de pines
  pinMode(13,OUTPUT); //El pin 13 sera una salida (verde) 
  pinMode(12,OUTPUT); //El pin 12 sera una salida (amarillo)
  pinMode(11,OUTPUT); //El pin 11 sera una salida (rojo)
  
  pinMode(10,OUTPUT); //El pin 10 sera una salida (verde Peatonal)
  pinMode(9,OUTPUT); //El pin 9 sera una salida (rojo Peatonal)
 
}

void loop() { //Inicaimos la secuencia de instrucciones 
  digitalWrite(13,HIGH);//Encendemos el led verde 
  digitalWrite(12,LOW);//mantenemos apagado el led amarillo 
  digitalWrite(11,LOW);//mantenemos apagado el led rojo 
  
  digitalWrite(9,HIGH);//encendemos el led rojo peatonal 
  delay(5000);//mantenemos este sistema por 5 segundos 

  digitalWrite(13,LOW); //pasado el tiempo apagamos el led verde 
  delay(300); //esto sucede solo 300 milisegundos
  digitalWrite(13,HIGH);//lo volvemos a encender 
  delay(300); //esperamos otros 300 milisegundos
  digitalWrite(13,LOW);//Lo volvemos a apagar 
  delay(300);//tomamos en cuenta otros 300 milisegundos (aunque no es necesario)   

  digitalWrite(12,HIGH);//Con el verde apagado totalmente ahora encendemos el led amarillo
  delay(2000); //lo mantenemos asi por 2 segundos 

  digitalWrite(13,LOW);//luego mantenemos el led verde apagado 
  digitalWrite(12,LOW); //apagamos el amarillo
  digitalWrite(11,HIGH); //Finalmente encendemos el rojo 

  digitalWrite(9,LOW); //Apagamos el rojo peatonal 
  digitalWrite(10,HIGH); //encendemos el verde peatonal   
  delay(5000); //mantenemos este sistema por 5 segundos 

  digitalWrite(13,LOW); //Luego apagaremos el verde 
  digitalWrite(12,LOW); //tambien el amarillo 
  digitalWrite(11,LOW); //Tambien el rojo 

  digitalWrite(9,LOW); //Tambien el verde peatonal
  digitalWrite(10,LOW);//Tambien el rojo peatonal 
  delay(200); //Esto por 200 milisegundos para dar una pausa antes de volver a ejecutar el codigo    
 }
# semáforo con botones
