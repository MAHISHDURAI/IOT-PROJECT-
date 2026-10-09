# IOT-PROJECT-
const int leds[] = {D2, D5};

unsigned long previousMillis = 0;
const unsigned long interval = 500;

int state = 0;

void setup() {
  for (int i = 0; i < 2; i++) {
    pinMode(leds[i], OUTPUT);
    digitalWrite(leds[i], LOW);
  }
}

void loop() {
  if (millis() - previousMillis >= interval) {
    previousMillis = millis();

    for (int i = 0; i < 2; i++) {
      digitalWrite(leds[i], LOW);
    }

    digitalWrite(leds[state], HIGH);

    state++;

    if (state >= 2) {
      state = 0;
    }
  }
}
