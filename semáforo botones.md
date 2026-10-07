# codigo del semáforo con botones
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