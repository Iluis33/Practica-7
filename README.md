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
SEMAFORO CON BOTONES: int Boton1 = 7;   // Pin para Tecla1
int Boton2 = 6;   // Pin para Tecla2

void setup() {
  // Configuración de LEDs
  pinMode(13, OUTPUT); // VERDE
  pinMode(12, OUTPUT); // amarillo
  pinMode(11, OUTPUT); // ROJO

  pinMode(10, OUTPUT); // VERDE peatonal
  pinMode(9,  OUTPUT); // amarillo peatonal
  pinMode(8,  OUTPUT); // ROJO peatonal

  // Botones con resistencia pull-up interna
  pinMode(Boton1, INPUT_PULLUP);
  pinMode(Boton2, INPUT_PULLUP);

  // Comunicación serial
  Serial.begin(9600);
  delay(200); // pequeña espera para que el monitor serial se inicialice
}

void loop() {
  bool ValorBoton1 = digitalRead(Boton1);
  bool ValorBoton2 = digitalRead(Boton2);




Serial.println(ValorBoton1);
delay(1000);

Serial.println(ValorBoton2);
delay(1000);

serie1();


//VERIFICACION DE BOTON PARA INICIAR
if (ValorBoton1 == 1) { 
serie1();
}

}

void serie1 () {


  //Inicaimos la secuencia de instrucciones 
  digitalWrite(13,HIGH);//Encendemos el rojo verde 
  digitalWrite(12,LOW);//mantenemos apagado el led amarillo 
  digitalWrite(11,LOW);//mantenemos apagado el led verde 
  
  //SEGUNDO 
  digitalWrite(10,LOW);//Encendemos el rojo verde 
  digitalWrite(9,LOW);//mantenemos apagado el led amarillo 
  digitalWrite(8,HIGH);//mantenemos apagado el led verde 
  

  delay(5000);


  delay(5000);

  digitalWrite(13,LOW);//Apagamos el verde

  delay(500);

  digitalWrite(13,HIGH);//Encendemos el verde

  delay(500); 

  digitalWrite(13,LOW);//Apagamos el verde

  delay(500);

  digitalWrite(13,HIGH);//Encendemos el verde

  delay(500); 
 
  digitalWrite(13,LOW);//Apagamos el verde

  delay(500);

  digitalWrite(12,HIGH);//Encendemos el verde

  delay(500);

  digitalWrite(13,LOW);//Apagamos el AMARILLO


  delay(4000);

  digitalWrite(12,LOW);//mantenemos apagado el led amarillo 


  digitalWrite(11,HIGH);//mantenemos apagado el led ROJO

  //SEGUNDO SEM

  digitalWrite(8,LOW); //APAGAMOS ROJO
  digitalWrite(10,HIGH);//mantenemos apagado el led VERDE


  delay(5000);  

  //SEGUNDO

 digitalWrite(10,LOW);//Apagamos el verde

  delay(500);

  digitalWrite(10,HIGH);//Encendemos el verde

  delay(500); 

  digitalWrite(10,LOW);//Apagamos el verde

  delay(500);

  digitalWrite(10,HIGH);//Encendemos el verde

  delay(500); 
 
  digitalWrite(10,LOW);//Apagamos el verde

  delay(500);

  digitalWrite(9,HIGH);//Apagamos el AMARILLO


  delay(4000);



}
