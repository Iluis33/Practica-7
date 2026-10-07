# código del Dac
// Simulación de lestados lógicos para el DAC R/2R de 4 bits

const int pinSW1 = 2; // LSB (Bit 0) conectado a SW1
const int pinSW2 = 3; // (Bit 1) conectado a SW2
const int pinSW3 = 4; // (Bit 2) conectado a SW3
const int pinSW4 = 5; // MSB (Bit 3) conectado a SW4

void setup() {
  pinMode(pinSW1, OUTPUT);
  pinMode(pinSW2, OUTPUT);
  pinMode(pinSW3, OUTPUT);
  pinMode(pinSW4, OUTPUT);
}

void loop() {
  // Iterar a través de las 16 combinaciones binarias (0 a 15)
  for (int i = 0; i < 16; i++) {
    
    // bitRead() extrae el bit específico del número entero 'i'
    digitalWrite(pinSW1, bitRead(i, 0)); 
    digitalWrite(pinSW2, bitRead(i, 1)); 
    digitalWrite(pinSW3, bitRead(i, 2)); 
    digitalWrite(pinSW4, bitRead(i, 3)); 

    // Retardo de 1 segundo para observar cada escalón en el osciloscopio
    delay(1000); 
  }
}
