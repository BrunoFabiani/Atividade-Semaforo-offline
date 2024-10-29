# Atividade-Semaforo-offline

## LINK VÍDEO:
https://youtu.be/v-Oz2OV4sKg

## Notas:
Gustavo da Costa - 10
Fernando Oliveira - 10

## Componentes utilizados
- Arduino Uno
- Cabo USB A/B 50cm
- Protoboard 400 pontos
- Montagem de madeira de um semáforo
- 1 led vermelho
- 1 led amarelo
- 1 led verde
- 5 jumper macho/fêmea
- 7 jumper macho/macho
- 2 resistores
- 1 buzzer

## Montagem:
Para a montagem do semáforo, primeiramente, o GND e o 5V do Arduino foram conectados às linhas de negativo e positivo da protoboard, respectivamente, para fornecer a alimentação aos componentes. Os LEDs vermelho, amarelo e verde foram posicionados no modelo do semáforo e conectados aos pinos digitais correspondentes do Arduino (13, 12 e 11) para permitir o controle da sequência de iluminação. A parte negativa (cátodo) de cada LED foi conectada à linha de GND na protoboard, que por sua vez estava conectada ao GND do Arduino. Um resistor foi utilizado em série com cada LED para limitar a corrente, garantindo a proteção dos componentes. O buzzer foi ligado ao pino digital 10 e conectado ao GND da protoboard, configurado para emitir som durante a ativação do LED verde.

## Código utilizado:
```cpp
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
