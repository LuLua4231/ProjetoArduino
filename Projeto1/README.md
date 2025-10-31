#Projeto 1 Sequência de LEDs

Esse projeto liga um led por tres segudos e depois o apaga acendendo o próximo na sequência até que repete o ciclo ao chegar no final.

Código:

// C++ code

void setup()
{
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
}

void loop()
{
  digitalWrite(3, HIGH);
  delay(3000);
  digitalWrite(3, LOW);
  digitalWrite(4, HIGH);
  delay(3000);
  digitalWrite(4, LOW);
  digitalWrite(5, HIGH);
  delay(3000);
  digitalWrite(5, LOW);
  digitalWrite(6, HIGH);
  delay(3000);
  digitalWrite(6, LOW);
  digitalWrite(7, HIGH);
  delay(3000);
  digitalWrite(7, LOW);
}
