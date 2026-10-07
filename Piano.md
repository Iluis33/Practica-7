# Código del piano
PIANO: //PROGRAMA ESCRITO POR EQUIPO 5 LAB DE ELECTRONICA FACULTAD DE CIENCIAS UNAM
//ESTE PROGRAMA PRORAMA UN PIANO DE 8 TONOS

int pinBuzz=2;          // Pin del buzzer
float Base=554.37;  // FRECUENCIA EN HTZ DEL BUZZER LA CENTRAL
float SEMITONO1 = Base * pow(2.0,1 / 12.0);
float SEMITONO2 = Base * pow(2.0,2 / 12.0);
float SEMITONO3 = Base * pow(2.0,3 / 12.0);
float SEMITONO4 = Base * pow(2.0,4 / 12.0);
float SEMITONO5 = Base * pow(2.0,5 / 12.0);
float SEMITONO6 = Base * pow(2.0,6 / 12.0);
float SEMITONO7 = Base * pow(2.0,7 / 12.0);
float SEMITONO8 = Base * pow(2.0,8 / 12.0);
float SEMITONO9 = Base * pow(2.0,9 / 12.0);
float SEMITONO10 = Base * pow(2.0,10 / 12.0);
float SEMITONO11 = Base * pow(2.0,11 / 12.0);
float SEMITONO12 = Base * pow(2.0,12 / 12.0);

int Octavador = A0;

int NoOctava=0;
int Led=1;

int Tecla1=10;          // Pin para Tecla1
int Tecla2=9;           // Pin para Tecla2
int Tecla3=8;           // Pin para Tecla3
int Tecla4=7;           // Pin para Tecla4
int Tecla5=6;           // Pin para Tecla5
int Tecla6=5;           // Pin para Tecla6
int Tecla7=4;           // Pin para Tecla7
int Tecla8=3;           // Pin para Tecla8

int Rojo=11;            // Pin para LedRojo
int Amarillo=12;        // Pin para LedAmarillo
int Verde=13;           // Pin para LedVerde


int duracion=50;       //Duración del tono

int espera = 1000;      //Tiempo de espera




void setup() {
  //PARAMETROS QUE CORREN UNA VEZ
  
//Configuraciones para el buzzer

pinMode(pinBuzz,OUTPUT);  //Pin del buzzer

//Configuraciones para las teclas
pinMode(Tecla1,INPUT);    //Pin de Tecla 1
pinMode(Tecla2,INPUT);    //Pin de Tecla 2
pinMode(Tecla3,INPUT);    //Pin de Tecla 3
pinMode(Tecla4,INPUT);    //Pin de Tecla 4
pinMode(Tecla5,INPUT);    //Pin de Tecla 5
pinMode(Tecla6,INPUT);    //Pin de Tecla 6
pinMode(Tecla7,INPUT);    //Pin de Tecla 7
pinMode(Tecla8,INPUT);    //Pin de Tecla 8

pinMode(Octavador,INPUT); // Pin para octavador

//Leds

pinMode(Rojo,OUTPUT);        //Pin de LedRojo
pinMode(Amarillo,OUTPUT);    //Pin de LedAmarillo
pinMode(Verde,OUTPUT);    //Pin de LedVerde

//Inicia comunicación serial
Serial.begin(9600); //COMUNICACION SERIAL
  

}

void loop() {
  //PARAMETROS QUE CORREN EN BUCLE
  
int ValorTecla1=digitalRead(Tecla1);
int ValorTecla2=digitalRead(Tecla2);
int ValorTecla3=digitalRead(Tecla3);
int ValorTecla4=digitalRead(Tecla4);
int ValorTecla5=digitalRead(Tecla5);
int ValorTecla6=digitalRead(Tecla6);
int ValorTecla7=digitalRead(Tecla7);
int ValorTecla8=digitalRead(Tecla8);

int ValorOctavador=digitalRead(Octavador);


//Prueba de Octavador y contador
//
//Serial.print("Octavador = ");
//Serial.println(ValorOctavador);
//Serial.print("No de Octava = ");
//Serial.println(NoOctava);

//Serial.print("Led = ");
//Serial.println(Led);



if (ValorOctavador == 1 && NoOctava == 0){
  Led =Led + 1;
}
if (Led>3){
    Led=1;
  }

NoOctava=ValorOctavador;

delay(10);

if (Led==1){
  digitalWrite(Verde, HIGH);
} else {
  digitalWrite(Verde, LOW);
}

if (Led==2){
  digitalWrite(Amarillo, HIGH);
} else {
  digitalWrite(Amarillo, LOW);
}

if (Led==3){
  digitalWrite(Rojo, HIGH);
}else {
  digitalWrite(Rojo, LOW);
}

//Prueba de cada boton

//Serial.print("Tecla 1 = ");
//Serial.println(ValorTecla1);
//
//Serial.print("Tecla 2 = ");
//Serial.println(ValorTecla2);
//
//Serial.print("Tecla 3 = ");
//Serial.println(ValorTecla3);
//
//Serial.print("Tecla 4 = ");
//Serial.println(ValorTecla4);
//
//Serial.print("Tecla 5 = ");
//Serial.println(ValorTecla5);
//
//Serial.print("Tecla 6 = ");
//Serial.println(ValorTecla6);
//
//Serial.print("Tecla 7 = ");
//Serial.println(ValorTecla7);
//
//Serial.print("Tecla 8 = ");
//Serial.println(ValorTecla8);
//
//Serial.print("\n \n \n \n \n \n \n \n"); 
//delay(500);



//// buzzer
//tone(pinBuzz,frecuenciaLAC,duracion);
//delay(espera);
//tone(pinBuzz,frecuenciaLAG,duracion);
//delay(espera);


//Situacion en led=1 OCTAVA ORIGINAL


if (ValorTecla1 == 1 && Led == 1){
  tone(pinBuzz,Base,duracion);
  Serial.println(Base);
}

if (ValorTecla2 == 1 && Led == 1){
  tone(pinBuzz,SEMITONO2,duracion);
    Serial.println(SEMITONO2);
}

if (ValorTecla3 == 1 && Led == 1){
  tone(pinBuzz,SEMITONO4,duracion);
    Serial.println(SEMITONO4);
}

if (ValorTecla4 == 1 && Led == 1){
  tone(pinBuzz,SEMITONO5,duracion);
    Serial.println(SEMITONO5);
}

if (ValorTecla5 == 1 && Led == 1){
  tone(pinBuzz,SEMITONO7,duracion);
    Serial.println(SEMITONO7);
}

if (ValorTecla6 == 1 && Led == 1){
  tone(pinBuzz,SEMITONO9,duracion);
    Serial.println(SEMITONO9);
}

if (ValorTecla7 == 1 && Led == 1){
  tone(pinBuzz,SEMITONO11,duracion);
    Serial.println(SEMITONO11);
}

if (ValorTecla8 == 1 && Led == 1){
  tone(pinBuzz,SEMITONO12,duracion);
    Serial.println(SEMITONO12);
}


//Situacion en 2=led 1 OCTAVA MAS

if (ValorTecla1 == 1 && Led == 2){
  tone(pinBuzz,Base*2,duracion);
  Serial.println(Base);
}

if (ValorTecla2 == 1 && Led == 2){
  tone(pinBuzz,SEMITONO2*2,duracion);
    Serial.println(SEMITONO2);
}

if (ValorTecla3 == 1 && Led == 2){
  tone(pinBuzz,SEMITONO4*2,duracion);
    Serial.println(SEMITONO4);
}

if (ValorTecla4 == 1 && Led == 2){
  tone(pinBuzz,SEMITONO5*2,duracion);
    Serial.println(SEMITONO5);
}

if (ValorTecla5 == 1 && Led == 2){
  tone(pinBuzz,SEMITONO7*2,duracion);
    Serial.println(SEMITONO7);
}

if (ValorTecla6 == 1 && Led == 2){
  tone(pinBuzz,SEMITONO9,duracion);
    Serial.println(SEMITONO9);
}

if (ValorTecla7 == 1 && Led == 2){
  tone(pinBuzz,SEMITONO11*2,duracion);
    Serial.println(SEMITONO11);
}

if (ValorTecla8 == 1 && Led == 2){
  tone(pinBuzz,SEMITONO12*2,duracion);
    Serial.println(SEMITONO12);
}




//Situacion en 3=led 2 OCTAVA MAS

if (ValorTecla1 == 1 && Led == 3){
  tone(pinBuzz,Base*4,duracion);
  Serial.println(Base);
}

if (ValorTecla2 == 1 && Led == 3){
  tone(pinBuzz,SEMITONO2*4,duracion);
    Serial.println(SEMITONO2);
}

if (ValorTecla3 == 1 && Led == 3){
  tone(pinBuzz,SEMITONO4*4,duracion);
    Serial.println(SEMITONO4);
}

if (ValorTecla4 == 1 && Led == 3){
  tone(pinBuzz,SEMITONO5*4,duracion);
    Serial.println(SEMITONO5);
}

if (ValorTecla5 == 1 && Led == 3){
  tone(pinBuzz,SEMITONO7*4,duracion);
    Serial.println(SEMITONO7);
}

if (ValorTecla6 == 1 && Led == 3){
  tone(pinBuzz,SEMITONO9*4,duracion);
    Serial.println(SEMITONO9);
}

if (ValorTecla7 == 1 && Led == 3){
  tone(pinBuzz,SEMITONO11*4,duracion);
    Serial.println(SEMITONO11);
}

if (ValorTecla8 == 1 && Led == 3){
  tone(pinBuzz,SEMITONO12*4,duracion);
    Serial.println(SEMITONO12);
}


}

   // Fin del programa: Programa escrito por Equipo 5 Fac de Ciencias UNAM