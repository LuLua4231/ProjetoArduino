# Projeto 2 Medidor Ultrassônico de Nível de Tanque 

Esse projeto observa um tanque de água com um sesensor ultrassônico que identifica o quão cheio o tanque está e ao chegar no limite de água ele controla um relé para ligar uma bomba de água (representada por um LED) para esvaziar o tanque e ao sensor identificar que o tanque esvaziou ele desliga a bomba.

Código:

// C++ code

int distancia;

void setup()
{
  pinMode(6, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(3, OUTPUT);

}


long readUltrasonicDistance(int triggerPin, int echoPin)
{
  pinMode(triggerPin, OUTPUT);  // Clear the trigger
  digitalWrite(triggerPin, LOW);
  delayMicroseconds(2);
  // Sets the trigger pin to HIGH state for 10 microseconds
  digitalWrite(triggerPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(triggerPin, LOW);
  pinMode(echoPin, INPUT);
  // Reads the echo pin, and returns the sound wave travel time in microseconds
  return pulseIn(echoPin, HIGH);
}
 
void loop()
{


  distancia = 0.01723 *readUltrasonicDistance(2,2);
  
  if(distancia >= 300)
  {
  	digitalWrite(5,LOW);
    digitalWrite(4,LOW);
    digitalWrite(3,HIGH);
    digitalWrite(6, LOW);

  } else if(distancia < 300 && distancia >30)
  {
    digitalWrite(3,LOW);
    digitalWrite(5,LOW);
    digitalWrite(4,HIGH);
  }else if(distancia <= 30)
  {
    digitalWrite(3,LOW);
    digitalWrite(4,LOW);
    digitalWrite(5,HIGH);
    digitalWrite(6, HIGH);
  }
}
