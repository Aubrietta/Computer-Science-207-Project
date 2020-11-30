# Computer-Science-207-Project
//Project for Computer Science 207.

long randNumber;

int red= 11;
int green = 10;
int blue = 9;

void setup() {
  pinMode(red, OUTPUT);
  pinMode(green, OUTPUT);
  pinMode(blue, OUTPUT);
  
  Serial.begin(9600);

  // if analog input pin 0 is unconnected, random analog
  // noise will cause the call to randomSeed() to generate
  // different seed numbers each time the sketch runs.
  // randomSeed() will then shuffle the random function.
  randomSeed(analogRead(0));

  // print a random number from 0 to 299
  // randNumber = random(300);
  // Serial.println(randNumber);

  // print a random number from 10 to 19
  randNumber = random(1, 4);
  Serial.println(randNumber);

  delay(500);
}

void loop() {
  if (randNumber == 1)
  {
    RGB_color(255, 0, 0); // Red
  }
  if (randNumber == 2)
  {
    RGB_color(0, 0, 255); // Blue
  }
  if (randNumber == 3)
  {
    RGB_color(0, 255, 0); // Green
  }
  else
  {
    RGB_color(255, 100, 0); // Yellow
  }
}

void RGB_color(int red_light_value, int green_light_value, int blue_light_value)
 {
  analogWrite(red, red_light_value);
  analogWrite(green, green_light_value);
  analogWrite(blue, blue_light_value);
}
