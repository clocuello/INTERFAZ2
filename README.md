# INTERFAZ II

1.["Hola, Mundo!"](#ejercicio-n-1-arduino-hola-mundo) <br>
2.[Semaforo Arduino](#ejercicio-n-2-semaforo-arduino) <br>
3.[Led Parpadeante](#ejercicio-n-3-led-parpadeante) <br>
4.[Led Pulsador](#ejercicio-n-4-led-pulsador) <br>
5.[Led Potenciometro](#ejercicio-n-5-led-potenciometro) <br>
6.[Arduino Processing](#ejercicio-n-6-arduino-processing) <br>
7.[Arduino + Boton + Processing](#ejercicio-n-7-arduino--bot%C3%B3n--processing) <br>
8.[Arduino + Boton + Potenciometro + Processing](#ejercicio-n-8-arduino--bot%C3%B3n--potenciometro--processing) <br>
9.[If + Else](#ejercicio-n-9-if--else) <br>
10.[Botonera](#ejercicio-n-10-botonera) <br>
--.[Idea Personal](#ejercicio-idea-personal-led-parpadeante--potenciometro) <br>
11.[Sensor Sharp](#ejercicio-n-11-sensor-sharp) <br>
12.[Sensor Humedad](#ejercicio-n-12-sensor-de-humedad) <br>
13.[Cuerpo, Video, Sensor Sharp](#ejercicio-n-13-cuerpo-video-sensor-sharp) <br>
14.[Promedio de Imagenes](#ejercicio-n-14-promedio-de-imagenes) <br>
15.[Promedio de imágenes llamando una carpeta + potenciometro](#ejercicio-n-15-promedio-de-imagenes-llamado-una-carpeta--potenciometro) <br>
--.[Idea Grupal](#idea-grupal) <br>
--.[Entrega Final Grupal]() <br>


### EJERCICIO N° 1: ARDUINO: "Hola Mundo:)"

```js
void setup() {
  Serial.begin(9600); // Inicia la comunicación serie a 9600 bps
  Serial.println("Hola, Mundo!"); // Envía "Hola, Mundo!" al monitor serie
}

void loop() {
  // No es necesario poner nada en el loop para este ejemplo
}
```

### EJERCICIO N° 2: SEMAFORO ARDUINO

```js
// C++ code - Semáforo Autos y Peatones

// Definición de pines
int LED_1 = 6;  // Luz roja autos
int LED_2 = 7;  // Luz amarilla autos
int LED_3 = 8;  // Luz verde autos
int LED_4 = 9;  // Luz verde peatones
int LED_5 = 10; // Luz roja peatones

void setup() {
  // Configuramos todos los pines como salida
  pinMode(LED_1, OUTPUT);
  pinMode(LED_2, OUTPUT);
  pinMode(LED_3, OUTPUT);
  pinMode(LED_4, OUTPUT);
  pinMode(LED_5, OUTPUT);
}

void loop() {
  // 🚦 Fase 1: Autos en verde, peatones en rojo
  digitalWrite(LED_1, LOW);   // Rojo autos apagado
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado
  digitalWrite(LED_3, HIGH);  // Verde autos encendido
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 2: Amarillo autos, peatones siguen en rojo
  digitalWrite(LED_3, LOW);   // Verde autos apagado
  digitalWrite(LED_2, HIGH);  // Amarillo autos encendido
  delay(2000); // 2 segundos
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado

  // 🚦 Fase 3: Rojo autos, verde peatones
  digitalWrite(LED_1, HIGH);  // Rojo autos encendido
  digitalWrite(LED_5, LOW);   // Rojo peatones apagado
  digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(5000); // 5 segundos
  digitalWrite(LED_4, LOW);  // Encender LED
  delay(500);             // Esperar 1 segundo
  digitalWrite(LED_4, HIGH);   // Apagar LED
  delay(500);             // Esperar 1 segundo
  digitalWrite(LED_4, LOW);  // Encender LED
  delay(500);             // Esperar 1 segundo
  digitalWrite(LED_4, HIGH);   // Apagar LED
  delay(500);             // Esperar 1 segundo
   digitalWrite(LED_4, LOW);  // Encender LED
  delay(500);             // Esperar 1 segundo
  digitalWrite(LED_4, HIGH);   // Apagar LED
  delay(500);

  // 🚦 Fase 4: Rojo autos, rojo peatones (tiempo intermedio)
  digitalWrite(LED_1, LOW);   // Rojo autos apagado
  digitalWrite(LED_3, HIGH);  // Verde autos encendido
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(2000); // 2 segundos
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/img/SEMAFORO.png" width="1024" height="550" />

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/SEMAFORO.jpeg" width="1024" height="550" />

### EJERCICIO N° 3: LED PARPADEANTE

```js
void setup() {  // Configuración inicial (ej: pines como entrada/salida)
  pinMode(13, OUTPUT);  // Pin 13 como salida
  pinMode(8, OUTPUT);  // Pin 8 como salida
}

void loop() {   // Se repite infinitamente
  digitalWrite(13, HIGH);  // Encender LED
  delay(1000);             // Esperar 1 segundo
  digitalWrite(13, LOW);   // Apagar LED
  //delay(1000);             // Esperar 1 segundo
  digitalWrite(8, HIGH);  // Encender LED
  delay(1000);             // Esperar 1 segundo
  digitalWrite(8, LOW);   // Apagar LED
  //delay(1000);             // Esperar 1 segundo
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/img/LED_PARPADEANTE.png" width="1024" height="550" />

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/LED_PARPADEANTE.jpeg" width="1024" height="550" />

### EJERCICIO N° 4: LED PULSADOR

```js
void setup() {
  pinMode(2, INPUT);  // Botón como entrada
  pinMode(13, OUTPUT);
}
void loop() {
  if (digitalRead(2) == HIGH) {  // Si se presiona el botón
    digitalWrite(13, HIGH);
  } else {
    digitalWrite(13, LOW);
  }
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/img/LED_PULSADOR.png" width="1024" height="550" />

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/LED_PULSADOR.jpeg" width="1024" height="550" />

### EJERCICIO N° 5: LED POTENCIOMETRO

```js
void setup() {
  pinMode(9, OUTPUT);  // Pin PWM (símbolo ~)
}
void loop() {
  int valor = analogRead(A0);           // Leer potenciómetro (0-1023)
  int brillo = map(valor, 0, 1023, 0, 255);  // Convertir a rango PWM
  analogWrite(9, brillo);               // Ajustar brillo
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/img/LED_POTENCIOMETRO.png" width="1024" height="550" />

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/POTENCIOMETRO.jpeg" width="1024" height="550" />

### EJERCICIO N° 6: ARDUINO PROCESSING

```js
import processing.serial.*;

Serial myPort;  // Crear objeto de la clase Serial
static String val;    // Datos recibidos desde el puerto serial
int sensorVal = 0;

void setup()
{
  background(0); 
  //fullScreen(P3D);
   size(1080, 720);
   noStroke();
  noFill();
  String portName = "COM3";// Cambia el número (en este caso) para que coincida con el puerto correspondiente conectado a tu Arduino. 

  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);

}

void draw()
{
  if ( myPort.available() > 0) {  // Si hay datos disponibles,
  val = myPort.readStringUntil('\n'); 
  try {
   sensorVal = Integer.valueOf(val.trim());
  }
  catch(Exception e) {
  ;
  }
  println(sensorVal); // léelos y guárdalos en vals!
  }  
// background(0);
  // Escala el valor de mouseX de 0 a 640 a un rango entre 0 y 175
  float c = map(sensorVal, 0, width, 0, 400);
  // Escala el valor de mouseX de 0 a 640 a un rango entre 40 y 300
  float d = map(sensorVal, 0, width, 40,500);
  fill(255, c, 0);
  ellipse(width/2, height/2, d, d);   
    fill(255, c, 0);
  ellipse(width/4, height/4, d, d);
    fill(255, c, 0);
  ellipse(width/4.5, height/4.5, d, d);   
    fill(255, c, 0);
  ellipse(width/6, height/6, d, d); 
  
    fill(255, c, 0);
  ellipse(width/1.2, height/1.2, d, d); 
    fill(255, c, 0);
  ellipse(width/1.5, height/1.5, d, d);   
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/img/Captura%20de%20pantalla%202025-08-26%20134316.png" width="1024" height="550" />

### EJERCICIO N° 7: ARDUINO + BOTÓN + PROCESSING

```js
ARDUINO: int buttonPin = 2;  // Pin del botón
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Botón con resistencia interna
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {   // Botón presionado
    Serial.println(1);        // Enviar un "1" a Processing
    delay(200);               // Evitar rebotes
  }
}

PROCESSING: import processing.serial.*;

Serial myPort;
ArrayList<PVector> circles; 

void setup() {
  size(1920, 1080);
  background(0);
  
  // Ajusta el nombre del puerto según tu Arduino
  println(Serial.list());
  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  //myPort = new Serial(this, Serial.list()[0], 9600);
  
  circles = new ArrayList<PVector>();
}

void draw() {
  //background(0);
  
  // Dibujar círculos almacenados
  fill(0, 0, 0);
  //noStroke();
  stroke(255, 0, 0);
  for (PVector c : circles) {
    ellipse(c.x, c.y, 30, 30);
  }
  
  // Revisar si llega algo de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.equals("1")) {
        // Cada vez que se aprieta el botón, agregar un círculo en posición aleatoria
        circles.add(new PVector(random(width), random(height)));
      }
    }
  }
}
```

### EJERCICIO N° 8: ARDUINO + BOTÓN + POTENCIOMETRO + PROCESSING

```js
ARDUINO: int buttonPin = 2;       // Pin del botón
int potPin = A0;         // Pin del potenciómetro
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Botón con resistencia interna
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {   // Botón presionado
    int potValue = analogRead(potPin);   // 0 - 1023
    Serial.print("BTN,");     // etiqueta para Processing
    Serial.println(potValue); // mando el valor junto con el evento
    delay(200);               // debounce simple
  }
}

PROCESSING: import processing.serial.*;

Serial myPort;
ArrayList<CircleData> circles; 

void setup() {
  size(1200, 720);
  background(0);
  
  // Ajusta el puerto según tu Arduino
  println(Serial.list());
  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  //myPort = new Serial(this, Serial.list()[0], 9600);
  
  circles = new ArrayList<CircleData>();
}

void draw() {
  //background(0);
  
  // Dibujar todos los círculos guardados
  //fill(0, 150, 255);
  //noStroke();
  fill(0, 0, 0);
  stroke(255, 0, 0);
  for (CircleData c : circles) {
    ellipse(c.x, c.y, c.size, c.size);
  }
  
  // Leer datos de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.startsWith("BTN")) {
        // Extraer el valor del potenciómetro
        String[] parts = split(val, ',');
        if (parts.length == 2) {
          float potVal = float(parts[1]);
          float circleSize = map(potVal, 0, 1023, 10, 100); // tamaño 10-100 px
          circles.add(new CircleData(random(width), random(height), circleSize));
        }
      }
    }
  }
}

// Clase para guardar datos de cada círculo
class CircleData {
  float x, y, size;
  CircleData(float x, float y, float size) {
    this.x = x;

    this.y = y;
    this.size = size;
  }
}
```

### EJERCICIO N° 9: IF + ELSE

```js

int leds[] = {2, 3, 4, 5}; // Creamos un arreglo con los pines donde van conectados los LEDs

void setup() {
  // Esta función corre solo una vez al iniciar Arduino
  for (int i = 0; i < 4; i++) {         // Recorre el arreglo desde i = 0 hasta i = 3
    pinMode(leds[i], OUTPUT);           // Configura cada pin del arreglo como salida (para controlar LEDs)
  }
}

void loop() {
  // Esta función corre en bucle infinito
  for (int i = 0; i < 4; i++) {         // Recorre los 4 LEDs, uno por uno
    if (i % 2 == 0) {                   // Si el índice es par (0, 2)...
      digitalWrite(leds[i], HIGH);      // Enciende el LED correspondiente
    } else {                            // Si el índice es impar (1, 3)...
      digitalWrite(leds[i], LOW);       // Apaga el LED correspondiente
    }
    delay(500);                         // Espera 0,5 segundos antes de pasar al siguiente
  }
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/IF%20ELSE.png" width="1024" height="550" />

### EJERCICIO N° 10: BOTONERA

```js

ARDUINO:
// --- Configuración de botones ---
const int numButtons = 3;
const int buttonPins[numButtons] = {2, 4, 7};
const int ledButtonPins[numButtons] = {9, 10, 11}; // LEDs botones

// --- Configuración de potenciómetros ---
const int numPots = 2;
const int potPins[numPots] = {A0, A1};
const int ledPotPins[numPots] = {3, 5}; // LEDs PWM

// Variables de estados previos
int lastButtonState[numButtons];
int lastPotValue[numPots];

void setup() {
  Serial.begin(9600);

  // Configurar botones y LEDs
  for (int i = 0; i < numButtons; i++) {
    pinMode(buttonPins[i], INPUT_PULLUP);
    pinMode(ledButtonPins[i], OUTPUT);
    lastButtonState[i] = digitalRead(buttonPins[i]);
  }

  // Configurar LEDs de potenciómetros
  for (int i = 0; i < numPots; i++) {
    pinMode(ledPotPins[i], OUTPUT);
    lastPotValue[i] = analogRead(potPins[i]);
  }
}

void loop() {
  // Leer y enviar botones
  for (int i = 0; i < numButtons; i++) {
    int buttonState = digitalRead(buttonPins[i]);

    // LED se enciende cuando botón está presionado
    digitalWrite(ledButtonPins[i], buttonState == LOW ? HIGH : LOW);

    if (buttonState != lastButtonState[i]) {  // enviar cambios
      Serial.print("B");
      Serial.print(i); 
      Serial.print(":");
      Serial.println(buttonState);
      lastButtonState[i] = buttonState;
    }
  }

  // Leer y enviar potenciómetros
  for (int i = 0; i < numPots; i++) {
    int potValue = analogRead(potPins[i]); // 0–1023
    int pwmValue = potValue / 4;           // 0–255

    // Ajustar LED según valor
    analogWrite(ledPotPins[i], pwmValue);

    if (abs(pwmValue - lastPotValue[i]) > 2) { // evitar ruido
      Serial.print("P");
      Serial.print(i);
      Serial.print(":");
      Serial.println(pwmValue);
      lastPotValue[i] = pwmValue;
    }
  }

  delay(10);
}

PROCESSING:
// Importamos librería para comunicación serial
import processing.serial.*;
// Importamos librería Minim para manejar audio
import ddf.minim.*;

// Declaramos el objeto serial para comunicarnos con Arduino
Serial myPort;
// Objeto principal de Minim
Minim minim;
// Array de reproductores de audio (3 pistas)
AudioPlayer[] players;
// Variable para guardar el índice de la pista que está sonando
int currentTrack = -1;  // -1 significa que no hay pista activa al inicio

void setup() {
  size(400, 200); // Ventana de 400x200 píxeles
  
  // --- Configuración del puerto serial ---
  printArray(Serial.list()); // Muestra en consola la lista de puertos disponibles
  myPort = new Serial(this, Serial.list()[0], 9600); // Abrimos el primer puerto de la lista a 9600 baudios
  
  // --- Configuración de audio ---
  minim = new Minim(this); // Inicializamos Minim
  players = new AudioPlayer[3]; // Creamos un array de 3 reproductores
  
  // Cargamos los 3 archivos de audio desde la carpeta "data"
  players[0] = minim.loadFile("audio1.mp3", 2048); 
  players[1] = minim.loadFile("audio2.mp3", 2048); 
  players[2] = minim.loadFile("audio3.mp3", 2048); 
}

void draw() {
  background(0); // Fondo negro
  fill(255);     // Color blanco para el texto
  textSize(16);  // Tamaño del texto
  
  // Mostramos en pantalla qué botón está activo
  text("Botón actual: " + (currentTrack == -1 ? "ninguno" : currentTrack), 20, 40);
}

void serialEvent(Serial myPort) {
  // Leemos la cadena que llega desde Arduino hasta el salto de línea
  String inString = trim(myPort.readStringUntil('\n'));
  
  // Si no llega nada, salimos
  if (inString == null) return;

  // --- Si el mensaje recibido empieza con "B" significa que es un botón ---
  if (inString.startsWith("B")) {
    // Quitamos la letra "B" y separamos el mensaje en partes (ejemplo "0:0")
    String[] parts = split(inString.substring(1), ':');
    
    // Si realmente recibimos dos partes (índice y estado)
    if (parts.length == 2) {
      int buttonIndex = int(parts[0]); // Número del botón (0,1,2)
      int state = int(parts[1]);       // Estado del botón (0 = presionado, 1 = suelto)
      
      // Si el botón fue presionado (LOW = 0 en Arduino)
      if (state == 0) { 
        playTrack(buttonIndex); // Llamamos a la función para reproducir la pista correspondiente
      }
    }
  }
}

// --- Función que reproduce una pista según el botón ---
void playTrack(int index) {
  // Si ya había una pista sonando, la pausamos y la rebobinamos al inicio
  if (currentTrack != -1 && players[currentTrack].isPlaying()) {
    players[currentTrack].pause();
    players[currentTrack].rewind();
  }
  
  // Reproducimos en bucle la pista seleccionada
  players[index].loop();
  
  // Actualizamos la variable para saber cuál es la pista activa
  currentTrack = index;
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/Botonera.png" width="1024" height="550" />

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/BOTONERA.jpeg" width="1024" height="550" />

### EJERCICIO IDEA PERSONAL: LED PARPADEANTE + POTENCIOMETRO 

Este ejercicio hace que dos LEDs (rojo y verde) parpadeen uno después del otro, pero ahora la velocidad del parpadeo se puede controlar girando un potenciómetro.

El codigo solo de los LEDs parpadeantes es:

```js
void setup() {  // Configuración inicial (ej: pines como entrada/salida)
  pinMode(13, OUTPUT);  // Pin 13 como salida
  pinMode(8, OUTPUT);  // Pin 8 como salida
}

void loop() {   // Se repite infinitamente
  digitalWrite(13, HIGH);  // Encender LED
  delay(1000);             // Esperar 1 segundo
  digitalWrite(13, LOW);   // Apagar LED
  //delay(1000);             // Esperar 1 segundo
  digitalWrite(8, HIGH);  // Encender LED
  delay(1000);             // Esperar 1 segundo
  digitalWrite(8, LOW);   // Apagar LED
  //delay(1000);             // Esperar 1 segundo
}
```

Luego agregamos a este codigo la nueva funcion del Potenciómetro:

```js
int pot = A0;
```
*Esto indica que el Potenciómetro esta conectado al pin analógico A0.

```js
pinMode(pot, INPUT);
```
*Esto indicar al Arduino que se agrego la entrada del Potenciómetro.

```js
int valorPot = analogRead(pot);
int tiempo = map(valorPot, 0, 1023, 100, 2000);
```
*Esto hace que el Potenciómetro controle la velocidad del parpadeo (siendo 0 y 1023 los dos extremos del Potenciómetro).

```js
delay(tiempo);
```
*Los delay(1000) del código original se cambiaron por delay(tiempo), para  que el tiempo dependa solo del Potenciómetro.


Cómo funciona paso a paso:

*Arduino lee el valor del potenciómetro.
*Calcula el tiempo de espera según esa lectura.
*Enciende el LED del pin 13, espera ese tiempo, y lo apaga.
*Luego enciende el LED del pin 8, espera el mismo tiempo, y lo apaga.
*Repite todo infinitamente.


Codigo Final:

```js
int pot = A0;  // Pin analógico donde conectamos el potenciómetro

void setup() {  // Configuración inicial
  pinMode(13, OUTPUT);  // Pin 13 como salida
  pinMode(8, OUTPUT);   // Pin 8 como salida
  pinMode(pot, INPUT);  // Pin del potenciómetro como entrada
}

void loop() {   // Se repite infinitamente
  int valorPot = analogRead(pot);  // Leer el potenciómetro (0 a 1023)
  int tiempo = map(valorPot, 0, 1023, 100, 2000);  
  // Convierte el valor a un rango de tiempo (100 ms a 2000 ms)

  digitalWrite(13, HIGH);  // Encender LED 1
  delay(tiempo);           // Esperar según el potenciómetro
  digitalWrite(13, LOW);   // Apagar LED 1

  digitalWrite(8, HIGH);   // Encender LED 2
  delay(tiempo);           // Esperar según el potenciómetro
  digitalWrite(8, LOW);    // Apagar LED 2
}
```

En resumen:

*El programa sigue igual, solo que ahora el potenciómetro controla qué tan rápido parpadean los LEDs, en lugar de tener un tiempo fijo.

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/led.parpadeante_potenciometro.png" width="1024" height="550" />

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/LedParpadeante%2BPotenciometro.jpg" width="1024" height="550" />

### Ejercicio N° 11: SENSOR SHARP

Codigo arduino:
```js
// Definir el pin del sensor Sharp
int sharpPin = A0;

void setup() {
  Serial.begin(9600); // Iniciar comunicación serial
}

void loop() {
  int sensorValue = analogRead(sharpPin); // Leer valor del sensor
  Serial.println(sensorValue); // Enviar valor a Processing
  delay(100); // Esperar un momento
}
```

Codigo Processing:
```js
import processing.serial.*;

Serial myPort;  // Create object from Serial class
static String val;    // Data received from the serial port
int sensorVal = 0;

void setup()
{
  background(0); 
  //fullScreen(P3D);
   size(1080, 720);
   noStroke();
  noFill();
  String portName = "COM5";// Change the number (in this case ) to match the corresponding port number connected to your Arduino. 

  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
}

void draw()
{
  if ( myPort.available() > 0) {  // If data is available,
  val = myPort.readStringUntil('\n'); 
  try {
   sensorVal = Integer.valueOf(val.trim());
  }
  catch(Exception e) {
  ;
  }
  println(sensorVal); // read it and store it in vals!
  }  
 //background(0);
  // Scale the mouseX value from 0 to 640 to a range between 0 and 175
  float c = map(sensorVal, 0, width, 0, 400);
  // Scale the mouseX value from 0 to 640 to a range between 40 and 300
  float d = map(sensorVal, 0, width, 40,500);
  fill(255, c, 0);
  ellipse(width/2, height/2, d, d);   

}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/sensorsharp.jpg" width="1024" height="550" />

### Ejercicio N° 12: SENSOR DE HUMEDAD

```js
void setup()
{
  Serial.begin(9600);// abre el puerto serial y Establece la velocidad en baudios a 9600 bps
}
void loop()
{
  int sensorValue;
  sensorValue = analogRead(0);   //conectar el sensor de humedad al pin analogo 0
  Serial.println(sensorValue); //imprime el valor a serial.
  delay(200);
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/sensorhumedad.jpg" width="1024" height="550" />

### Ejercicio N° 13: CUERPO, VIDEO, SENSOR SHARP

Codigo Arduino:
```js
// --- Sensor Sharp conectado al pin A0 ---
int sensorPin = A0;
int valor;

void setup() {
  Serial.begin(9600);
}

void loop() {
  valor = analogRead(sensorPin);
  Serial.println(valor);
  delay(50); // envío cada 50 ms
}
```
Codigo Processing:
```js
// --- Librerías necesarias ---
import processing.serial.*;
import processing.video.*;

// --- Variables de cámara y serial ---
Capture cam;
Serial myPort;

// --- Variables del sensor ---
float sensorValue = 0;
float suavizado = 0;

// --- Parámetros para detección de silueta ---
float umbral = 100; // controla el contraste para definir la silueta

void setup() {
  size(1280, 720);
  background(0);
  
  // --- Inicializar cámara ---
  String[] cameras = Capture.list();
  if (cameras.length == 0) {
    println("No se encontró cámara.");
    exit();
  } else {
    println("Cámara encontrada: " + cameras[0]);
    cam = new Capture(this, cameras[0]);
    cam.start();
  }
  
  // --- Inicializar puerto serie (Arduino) ---
  // Puedes ver la lista de puertos con println(Serial.list());
  String portName = Serial.list()[0]; 
  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  //myPort = new Serial(this, portName, 9600);
}

void draw() {
  background(0);
  
  // --- Leer datos del sensor ---
  while (myPort.available() > 0) {
    String inString = trim(myPort.readStringUntil('\n'));
    if (inString != null) {
      sensorValue = float(inString);
      suavizado = lerp(suavizado, sensorValue, 0.1);
    }
  }
  
  // --- Mapear los valores del sensor ---
  float escala = map(suavizado, 0, 1023, 1.5, 0.5); // tamaño de la silueta
  float alpha = map(suavizado, 0, 1023, 255, 80);   // opacidad según distancia
  
  // --- Captura de video ---
  if (cam.available()) {
    cam.read();
  }

  // --- Dibujar silueta desde la cámara ---
  cam.loadPixels();
  loadPixels();
  
  for (int y = 0; y < cam.height; y++) {
    for (int x = 0; x < cam.width; x++) {
      int loc = x + y * cam.width;
      color c = cam.pixels[loc];
      float brillo = brightness(c);
      
      // Si el brillo es menor que el umbral, dibujamos píxel blanco (silueta)
      if (brillo < umbral) {
        int px = int(x * escala);
        int py = int(y * escala);
        if (px < width && py < height) {
          stroke(255, alpha);
          point(px, py);
        }
      }
    }
  }
}
```
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/cvss.jpg" width="1024" height="550" />
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/ssp.png" width="1024" height="550" />

### Ejercicio N° 14: PROMEDIO DE IMAGENES

Codigo Arduino:
```js
void setup() {
  Serial.begin(9600);
}

void loop() {
  int potValue = analogRead(A0);
  Serial.println(potValue);
  delay(20);
}
```

Codigo Processing:
```js
import processing.serial.*;

Serial myPort;
PImage[] imgs;
int numImages = 7;
PImage avgImg;
float mixAmount = 0;

void setup() {
  size(1800, 1600);
  println(Serial.list());
 
  //Cambia el índice según tu puerto (0, 1, 2, etc.)
  myPort = new Serial(this, Serial.list()[0], 9600);
  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort.bufferUntil('\n');

  // Cargar imágenes
  imgs = new PImage[numImages];
  imgs[0] = loadImage("img1.jpg");
  imgs[1] = loadImage("img2.jpg");
  imgs[2] = loadImage("img3.jpg");
  imgs[3] = loadImage("img4.jpg");
  imgs[4] = loadImage("img5.jpg");
  imgs[5] = loadImage("img6.jpg");
  imgs[6] = loadImage("img7.jpg");

  avgImg = createImage(imgs[0].width, imgs[0].height, RGB);
}

void draw() {
  // Dibujar la imagen promedio según el valor del potenciómetro
  background(0);
  calcAverage(mixAmount);
  image(avgImg, 0, 0, width, height);
 
  fill(255);
  textSize(20);
  text("Mezcla: " + nf(mixAmount, 1, 2), 20, height - 20);
}

void serialEvent(Serial p) {
  String val = p.readStringUntil('\n');
  if (val != null) {
    val = trim(val);
    float sensor = float(val);
    mixAmount = map(sensor, 0, 1023, 0, 7); // 0 a 1
  }
}

void calcAverage(float t) {
  avgImg.loadPixels();

  for (int i = 0; i < avgImg.pixels.length; i++) {
    color c1 = imgs[0].pixels[i];
    color c2 = imgs[1].pixels[i];
    color c3 = imgs[2].pixels[i];

    // Promedio ponderado según el potenciómetro
    float r = red(c1)*(1-t) + red(c2)*t*0.5 + red(c3)*t*0.5;
    float g = green(c1)*(1-t) + green(c2)*t*0.5 + green(c3)*t*0.5;
    float b = blue(c1)*(1-t) + blue(c2)*t*0.5 + blue(c3)*t*0.5;

    avgImg.pixels[i] = color(r, g, b);
  }
  avgImg.updatePixels();
}
```

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/pi.jpg" width="1024" height="550" />
<img src="https://github.com/clocuello/INTERFAZ2/blob/main/pip.png" width="1024" height="550" />

### Ejercicio N° 15 PROMEDIO DE IMAGENES LLAMADO UNA CARPETA + POTENCIOMETRO

Codigo arduino:
```js
void setup() {
  Serial.begin(9600);
}

void loop() {
  int potValue = analogRead(A0);
  Serial.println(potValue);
  delay(20);
}
```

Codigo Processing:
```js
// --- Librerías necesarias ---
// Importa la librería de comunicación serial para conectar con Arduino
import processing.serial.*;
// Importa la clase File de Java para listar archivos y carpetas
import java.io.File;

// --- Comunicación serial con Arduino ---
// Variable que contendrá el objeto de puerto serial (conexión con Arduino)
Serial myPort;
// Variable que guarda el valor leído del potenciómetro (0..1023)
float potValue = 0;

// --- Variables de imágenes ---
// Arreglo dinámico que contendrá todas las imágenes cargadas desde la carpeta
PImage[] imgs;
// Imagen donde se almacenará el resultado del promedio/interpolación
PImage avgImg;

// --- Configuración inicial ---
void setup() {
  // Define el tamaño de la ventana de Processing (ancho, alto)
  size(745, 1024);
  
  // Cargar imágenes desde carpeta "data/imagenes"
  // Llama a la función que busca todas las imágenes dentro de esa carpeta
  imgs = loadImagesFromFolder("imagenes");
  // Imprime en la consola cuántas imágenes se cargaron (útil para debug)
  println("Imágenes cargadas: " + imgs.length);
  
  // Redimensionar todas las imágenes al tamaño del lienzo para que coincidan pixel a pixel
  for (int i = 0; i < imgs.length; i++) {
    imgs[i].resize(width, height); // redimensiona cada imagen al ancho y alto de la ventana
  }
  
  // Crea una imagen vacía del tamaño del lienzo donde guardaremos el promedio
  avgImg = createImage(width, height, RGB);
  
  // Conectar con Arduino (ver lista de puertos)
  // Muestra en consola la lista de puertos seriales disponibles (para identificar cuál usar)
  printArray(Serial.list());
  // Alternativa automática (comentada): abrir el primer puerto disponible a 9600 baudios
  // myPort = new Serial(this, Serial.list()[0], 9600);
  // Abrir un puerto específico (ejemplo para macOS). Ajusta según el puerto real en tu sistema.
  myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  // Nota: si no funciona el puerto, revisa la salida de printArray(Serial.list()) y usa el nombre correcto.
}

// --- Bucle principal ---
// draw() se ejecuta continuamente (aprox. 60 veces por segundo)
void draw() {
  // Pinta el fondo de negro en cada frame
  background(0);
  // Llama a la función que lee datos desde el puerto serial (actualiza potValue)
  readSerial();
  
  // Si no hay imágenes o sólo hay una, no hacemos nada (necesitamos al menos 2 para interpolar)
  if (imgs == null || imgs.length < 2) return;
  
  // Mapear el valor del potenciómetro (0..1023) al rango de índices entre 0 y imgs.length-1
  // Esto permite moverse a lo largo de la secuencia de imágenes
  float mixValue = map(potValue, 0, 1023, 0, imgs.length - 1);
  
  // Calcular el promedio/interpolación entre las dos imágenes vecinas según mixValue
  avgImagesWeighted(mixValue);
  
  // Mostrar la imagen promedio resultante en la pantalla, en la posición (0,0)
  image(avgImg, 0, 0);
  
  // Mostrar texto con el valor actual del potenciómetro en la esquina inferior izquierda
  fill(255); // color blanco para el texto
  text("Valor pot: " + nf(potValue, 1, 0), 10, height - 10); // nf para formatear el número
}

// --- Función que calcula el promedio ponderado entre imágenes ---
// mix es un valor flotante que indica la posición entre imágenes (ej. 2.3 -> entre img2 e img3)
void avgImagesWeighted(float mix) {
  // Accede al arreglo de píxeles de avgImg para poder modificarlos directamente
  avgImg.loadPixels();
  
  // Asegura que mix esté dentro del rango válido [0, imgs.length - 1]
  mix = constrain(mix, 0, imgs.length - 1);
  
  // i1 es el índice de la imagen "inferior" (por ejemplo 2 en 2.3)
  int i1 = floor(mix);
  // i2 es la imagen siguiente (i1 + 1), pero sin pasarse del último índice
  int i2 = min(i1 + 1, imgs.length - 1);
  // t es la fracción entre i1 e i2 (por ejemplo, 0.3 si mix es 2.3)
  float t = mix - i1;
  
  // Cargar los píxeles de las dos imágenes que vamos a mezclar
  imgs[i1].loadPixels();
  imgs[i2].loadPixels();
  
  // Recorre todos los píxeles de la imagen objetivo
  for (int i = 0; i < avgImg.pixels.length; i++) {
    // Coge el color del píxel i de la imagen i1
    color c1 = imgs[i1].pixels[i];
    // Coge el color del píxel i de la imagen i2
    color c2 = imgs[i2].pixels[i];
    
    // Interpola por separado cada componente de color (rojo, verde, azul)
    // red(c1) obtiene la componente roja del color c1
    float r = lerp(red(c1), red(c2), t);
    // green(c1) obtiene la componente verde del color c1
    float g = lerp(green(c1), green(c2), t);
    // blue(c1) obtiene la componente azul del color c1
    float b = lerp(blue(c1), blue(c2), t);
    
    // Crea un nuevo color a partir de las componentes interpoladas y lo asigna al píxel i
    avgImg.pixels[i] = color(r, g, b);
  }
  
  // Aplica los cambios realizados en el arreglo de píxeles a la imagen avgImg
  avgImg.updatePixels();
}

// --- Leer valor del potenciómetro desde Arduino ---
// Lee datos desde el puerto serial hasta encontrar saltos de línea y los convierte a número
void readSerial() {
  // Mientras el puerto exista y tenga bytes disponibles para leer...
  while (myPort != null && myPort.available() > 0) {
    // Lee una línea completa hasta '\n' (salto de línea)
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      // Elimina espacios y caracteres de control al inicio/final
      val = trim(val);
      // Si la cadena no está vacía, la convierte a float y la asigna a potValue
      if (val.length() > 0) {
        potValue = float(val);
      }
    }
  }
}

// --- Cargar todas las imágenes desde una carpeta ---
// Devuelve un arreglo PImage[] con todas las imágenes JPG/PNG encontradas en data/folderName
PImage[] loadImagesFromFolder(String folderName) {
  // Construye la ruta absoluta a la carpeta dentro de la carpeta data del sketch
  String path = sketchPath("data/" + folderName);
  // Crea un objeto File apuntando a esa carpeta
  File folder = new File(path);
  // Lista todos los archivos dentro de la carpeta (puede devolver null si no existe)
  File[] files = folder.listFiles();
  
  // Si files es null, la carpeta no existe o no tiene permisos -> avisar y devolver null
  if (files == null) {
    println("Carpeta no encontrada: " + path);
    return null;
  }
  
  // Crea una lista dinámica para almacenar las PImage cargadas
  ArrayList<PImage> loaded = new ArrayList<PImage>();
  // Recorre cada archivo encontrado en la carpeta
  for (File f : files) {
    // Obtiene el nombre del archivo y lo convierte a minúsculas para comparar extensiones
    String fname = f.getName().toLowerCase();
    // Si termina en .jpg o .png, lo cargamos
    if (fname.endsWith(".jpg") || fname.endsWith(".png")) {
      // loadImage busca en data/folderName el archivo y devuelve un PImage
      PImage img = loadImage(folderName + "/" + f.getName());
      // Si la imagen se cargó correctamente, la agregamos a la lista
      if (img != null) loaded.add(img);
    }
  }
  
  // Convierte la ArrayList a un arreglo PImage[] y lo retorna
  return loaded.toArray(new PImage[loaded.size()]);
}
```

### Idea Grupal

Esta proyecto nace desde la idea de hacer desorden en el orden, la intencion de querer ser ordenado pero que se vuelve imposible ser este completamente, por lo que pensamos en crear en Processing una linea de color blanco en la que se vean las letras de la palabra "ORDEN" de forma seguida y que esta palabra se moviera por la pantalla a partir del uso de Arduino y Potenciometro.

Codigo arduino:
```js
int potPin = A0; // Pin del potenciómetro
int potValue = 0;

void setup() {
Serial.begin(9600);
}

void loop() {
potValue = analogRead(potPin); // Lee valor (0 a 1023)
Serial.println(potValue); // Envia a Processing
delay(30); // Pequeño retardo
}
```

Codigo Processing:
```js
import processing.serial.*;

Serial myPort;
String textToShow = "ANY FURTHER QUESTIONS";
ArrayList<PVector> trail = new ArrayList<PVector>();

float potValue = 0; // valor leído del Arduino
float mappedX = 0; // posición mapeada

void setup() {
size(800, 400);
background(0);
textAlign(CENTER, CENTER);
textSize(24);
fill(255);

// Abrir el puerto serie correcto (ver cuál aparece en la consola)
println(Serial.list());
myPort = new Serial(this, Serial.list()[0], 9600);
}

void draw() {
background(0);

// Leer valor desde Arduino si hay datos
while (myPort.available() > 0) {
String val = myPort.readStringUntil('\n');
if (val != null) {
potValue = float(trim(val));
}
}

// Mapeo del potenciómetro a posición X en pantalla
mappedX = map(potValue, 0, 1023, 0, width);

// Crear una trayectoria con ruido vertical (como si fuera una línea viva)
float yPos = height/2 + sin(frameCount * 0.05) * 50;
trail.add(new PVector(mappedX, yPos));

// Mantener máximo 100 puntos
if (trail.size() > 100) trail.remove(0);

// Dibujar línea blanca del trazo
stroke(255);
strokeWeight(2);
noFill();
beginShape();
for (PVector p : trail) {
curveVertex(p.x, p.y);
}
endShape();

// Mostrar texto sobre la línea
for (int i = 0; i < trail.size(); i++) {
float t = map(i, 0, trail.size(), 0, textToShow.length());
int index = int(t);
if (index < textToShow.length()) {
char c = textToShow.charAt(index);
PVector p = trail.get(i);
pushMatrix();
translate(p.x, p.y);
rotate(noise(i * 0.1, frameCount * 0.01) * TWO_PI);
text(c, 0, 0);
popMatrix();
}
}
}
```

El codigo de processing lo sacamos de chat gpt, usando el prompt: al momento de mover el potenciómetro, se crea una línea blanca donde aparece un texto, código para processing y arduino uno. 
import processing.serial.*;
```js
Serial myPort;
String textToShow = "ANY FURTHER QUESTIONS";
ArrayList<PVector> trail = new ArrayList<PVector>();

float potValue = 0; // valor leído del Arduino
float mappedX = 0; // posición mapeada

void setup() {
size(800, 400);
background(0);
textAlign(CENTER, CENTER);
textSize(24);
fill(255);

// Abrir el puerto serie correcto (ver cuál aparece en la consola)
println(Serial.list());
myPort = new Serial(this, Serial.list()[0], 9600);
}

void draw() {
background(0);

// Leer valor desde Arduino si hay datos
while (myPort.available() > 0) {
String val = myPort.readStringUntil('\n');
if (val != null) {
potValue = float(trim(val));
}
}

// Mapeo del potenciómetro a posición X en pantalla
mappedX = map(potValue, 0, 1023, 0, width);

// Crear una trayectoria con ruido vertical (como si fuera una línea viva)
float yPos = height/2 + sin(frameCount * 0.05) * 50;
trail.add(new PVector(mappedX, yPos));

// Mantener máximo 100 puntos
if (trail.size() > 100) trail.remove(0);

// Dibujar línea blanca del trazo
stroke(255);
strokeWeight(2);
noFill();
beginShape();
for (PVector p : trail) {
curveVertex(p.x, p.y);
}
endShape();

// Mostrar texto sobre la línea
for (int i = 0; i < trail.size(); i++) {
float t = map(i, 0, trail.size(), 0, textToShow.length());
int index = int(t);
if (index < textToShow.length()) {
char c = textToShow.charAt(index);
PVector p = trail.get(i);
pushMatrix();
translate(p.x, p.y);
rotate(noise(i * 0.1, frameCount * 0.01) * TWO_PI);
text(c, 0, 0);
popMatrix();
}
}
}
```
Con este resultado:

<img src="https://github.com/clocuello/INTERFAZ2/blob/main/Captura%20de%20pantalla%202025-11-03%20101530.png" width="1024" height="550" />


despues cambiamos la frase String textToShow = "ANY FURTHER QUESTIONS";
por “ORDEN”


despues modificamos el tamaño de la letra en la parte del código: 

textSize(24);
donde el vez de 24 le pusimos 50


luego modificamos el espacio que había entre cada letra, en la parte del código:

for (int i = 0; i < trail.size(); i++) {

eliminamos el segundo signo + y lo cambiamos por un signo = y despues de eso se agrego un numero, fuimos probando tamaños y llegamos a el 10


despues modificamos el grosor de la linea blanca que guia las letras en la parte del código: 


strokeWeight(2);
donde pusimos 50 en vez de 20

y luego cambiamos el color de las letras de blanco: fill(255);
a negro: fill(0);



despues cambiamos el largo de la línea en la parte:
 if (trail.size() > 100) trail.remove(0);
y cambiamos el 100 por 600


Hicimos varias modificaciones dentro del código, incluyendo intentar agregar un segundo potenciómetro, agregar varias veces la misma frase, cambiar los colores del texto, línea y fondo, y cambiar los tamaños de las letras, fuera de los cambios que quedaron dentro del código. 

Este es el código final y modificado, las zonas subrayadas en verde son las zonas modificadas: 
```js
import processing.serial.*;

Serial myPort;
String textToShow = "NEDRO NEDRO NEDRO";
ArrayList<PVector> trail = new ArrayList<PVector>();

float potValue = 0; // valor leído del Arduino
float mappedX = 0; // posición mapeada

void setup() {
size(800, 400);
background(0);
textAlign(CENTER, CENTER);
textSize(50);
fill(0);

// Abrir el puerto serie correcto (ver cuál aparece en la consola)
println(Serial.list());
myPort = new Serial(this, Serial.list()[0], 9600);
}

void draw() {
background(0);

// Leer valor desde Arduino si hay datos
while (myPort.available() > 0) {
String val = myPort.readStringUntil('\n');
if (val != null) {
potValue = float(trim(val));
}
}

// Mapeo del potenciómetro a posición X en pantalla
mappedX = map(potValue, 0, 1023, 0, width);

// Crear una trayectoria con ruido vertical (como si fuera una línea viva)
float yPos = height/2 + sin(frameCount * 0.05) * 50;
trail.add(new PVector(mappedX, yPos));

// Mantener máximo 100 puntos
if (trail.size() > 600) trail.remove(0);

// Dibujar línea blanca del trazo
stroke(255);
strokeWeight(40);
noFill();
beginShape();
for (PVector p : trail) {
curveVertex(p.x, p.y);
}
endShape();


// Mostrar texto sobre la línea
for (int i = 5; i < trail.size(); i+=10) {
float t = map(i, 0, trail.size(), 0, textToShow.length());
int index = int(t);
if (index < textToShow.length()) {
char c = textToShow.charAt(index);
PVector p = trail.get(i);
pushMatrix();
translate(p.x, p.y);
rotate(noise(i * 0.1, frameCount * 0.01) * TWO_PI);
text(c, 0, 0);
popMatrix();
}
}
}
```

### Entrega Final Grupal

