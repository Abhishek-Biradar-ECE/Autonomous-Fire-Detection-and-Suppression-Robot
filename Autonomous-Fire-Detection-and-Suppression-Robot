#include <Servo.h>

// ================= MOTOR PINS =================
const int in1 = 7;
const int in2 = 8;
const int in3 = 9;
const int in4 = 10;
const int ena = 5;
const int enb = 6;

// ================= FLAME SENSORS ==============
const int rightFlame  = 2;
const int centerFlame = 3;
const int leftFlame   = 4;

// ================= SERVO & RELAY ==============
const int servoPin = 12;
const int relayPin = 11;

Servo myServo;

void setup() {

  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(in3, OUTPUT);
  pinMode(in4, OUTPUT);
  pinMode(ena, OUTPUT);
  pinMode(enb, OUTPUT);

  pinMode(rightFlame, INPUT);
  pinMode(centerFlame, INPUT);
  pinMode(leftFlame, INPUT);

  pinMode(relayPin, OUTPUT);
  digitalWrite(relayPin, HIGH);   // Pump OFF

  analogWrite(ena, 150);
  analogWrite(enb, 150);

  myServo.attach(servoPin);
  myServo.write(90);

  stopMotors();
}

void loop() {

  int rightValue  = digitalRead(rightFlame);
  int centerValue = digitalRead(centerFlame);
  int leftValue   = digitalRead(leftFlame);

  // 🔥 If flame on left → rotate left
  if (leftValue == LOW && centerValue == HIGH) {
    turnLeft();
  }

  // 🔥 If flame on right → rotate right
  else if (rightValue == LOW && centerValue == HIGH) {
    turnRight();
  }

  // 🔥 If flame centered → move forward
  else if (centerValue == LOW) {

    moveForward();
    delay(500);      // Move little forward
    stopMotors();
    sprayWater();    // Then spray
  }

  // ❌ No flame
  else {
    stopMotors();
    digitalWrite(relayPin, HIGH);
  }
}

// ================= MOTOR FUNCTIONS ============

void moveForward() {
  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  digitalWrite(in3, HIGH);
  digitalWrite(in4, LOW);
}

void turnLeft() {
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  digitalWrite(in3, HIGH);
  digitalWrite(in4, LOW);
}

void turnRight() {
  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  digitalWrite(in3, LOW);
  digitalWrite(in4, HIGH);
}

void stopMotors() {
  digitalWrite(in1, LOW);
  digitalWrite(in2, LOW);
  digitalWrite(in3, LOW);
  digitalWrite(in4, LOW);
}

// ================= SPRAY FUNCTION =============

void sprayWater() {

  digitalWrite(relayPin, LOW);  // Pump ON

  for (int angle = 60; angle <= 150; angle++) {
    myServo.write(angle);
    delay(15);
  }

  for (int angle = 150; angle >= 60; angle--) {
    myServo.write(angle);
    delay(15);
  }

  digitalWrite(relayPin, HIGH);  // Pump OFF
}
