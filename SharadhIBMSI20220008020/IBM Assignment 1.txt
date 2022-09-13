float temp;
int tempPin = 5;

void setup() {
   Serial.begin(9600);
}

void loop() {
   temp = analogRead(tempPin);
  
   // read analog volt from sensor and save to variable temp
   temp = temp * 0.48828125;
  
   // convert the analog volt to its temperature equivalent
   Serial.print("TEMPERATURE = ");
   Serial.print(temp-50.8); // display temperature value
   Serial.print("*C");
   Serial.println();
   delay(1000); // update sensor reading each one second
  
  
 if (temp > 25) { //high temp
  digitalWrite(13, HIGH);//R
  digitalWrite(12, LOW);//B
   digitalWrite(11, LOW);//G
 }
if (temp < 20) {  //low temp
  digitalWrite(13, LOW);//R
  digitalWrite(12, HIGH);//B
   digitalWrite(11, LOW);//G
}
 }
