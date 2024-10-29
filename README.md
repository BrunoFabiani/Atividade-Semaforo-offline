# Atividade-Semaforo-offline
Notas:
Gustavo da Costa - 10


Componentes utilizados -
Arduino Uno
Cabo USB A/b 50cm
Protoboard 400 pontos
1 led vermelho
1 led amarelo
1 led verde
5 jumper macho/fêmea
7 jumper macho/macho
2 resistores
1 buzzer

Montagem:
Para a montagem do semáforo, primeiramente foram conectados o GND e o 5V do Arduino nas filas de negativo e positivo da protoboard. Em seguida, os LEDs vermelho, amarelo e verde foram posicionados e conectados aos pinos digitais correspondentes no Arduino para controle da sequência de iluminação, e o buzzer foi ligado ao pino configurado para emitir som. Cada LED foi acompanhado de um resistor para limitar a corrente e proteger os componentes.

Código utilizado:
void setup() {  
    // define o pino do LED vermelho
    pinMode(13,OUTPUT);
    // define o pino do LED amarelo
    pinMode(12,OUTPUT);
    // define o pino do LED verde
    pinMode(11,OUTPUT);
    // define o pino do buzzer
    pinMode(10,OUTPUT);
}

void loop() {
  // faz o pino 13 ligar, o que liga o LED vermelho
  digitalWrite(13,HIGH);
  // mantém o LED vermelho ligado por 6 segundos
  delay(6000);
  // desliga o pino 13, o que desliga o LED vermelho
  digitalWrite(13,LOW);
  // liga o LED amarelo
  digitalWrite(12,HIGH);
  // mantém o LED amarelo ligado por 2 segundos
  delay(2000);
  // desliga o LED amarelo
  digitalWrite(12,LOW);
  // liga o LED verde
  digitalWrite(11,HIGH);
  // emite um som no buzzer com frequência de 150 Hz por 1 segundo
  tone(10, 150, 1000);
  // mantém o LED verde ligado por 4 segundos
  delay(4000);
  // desliga o LED verde
  digitalWrite(11,LOW);
  // liga o LED amarelo novamente
  digitalWrite(12,HIGH);
  // mantém o LED amarelo ligado por 2 segundos
  delay(2000);
  // desliga o LED amarelo
  digitalWrite(12,LOW);  
}
