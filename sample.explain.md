# การทดลองที่ 1 เรื่อง การเขียนโปรแกรมเพื่อรันบนไมโครคอนโทรเลอร์

include <Arduino.h>

int cnt = 0;

void setup()

{

	Serial.begin(115200);
  
}

***คำอธิบายส่วน setup คือ กำหนดให้ serial port มีความเร็วเริ่มต้นที่ 115200 ms***

void loop()

{

	cnt++
  
	Serial.printf("PATTANI :%d\n",cnt);
  
	int s = cnt % 5 + 1;
  
	int d = s * 1000;
  
	delay(d);
  
}

***คำอธิบายส่วน void loop คือ ให้มีการวนลูปเพิ่มตัวแปร cnt ไปเรื่อยๆ และกำหนดให้มีความหน่วง 1 วินาที***

# การทดลองที่ 2 เรื่อง การเขียนโปรแกรมเพื่อค้นหาไวไฟ

include <Arduino.h>

include <ESP8266WiFi.h>

int cnt = 0;

void setup()

{

	Serial.begin(115200);
  
	WiFi.mode(WIFI_STA);
  
	WiFi.disconnect();
  
	delay(100);
  
	Serial.println("\n\n\n");
  
}

***คำอธิบายส่วน setup คือ กำหนดให้ตัวไวไฟพร้อมทำงานโดยมีความหน่วงเวลาเท่ากับ 100 ms ***

void loop()

{

	Serial.println("========== เริ่มต้นแสกนหา Wifi ===========");
  
	int n = WiFi.scanNetworks();
  
	if(n == 0) {
  
		Serial.println("NO NETWORK FOUND");
    
	} else {
  
		for(int i=0; i<n; i++) {
    
			Serial.print(i + 1);
      
			Serial.print(": ");
      
			Serial.print(WiFi.SSID(i));
      
			Serial.print(" (");
      
			Serial.print(WiFi.RSSI(i));
      
			Serial.println(")");
      
			Serial.print(WiFi.channel(i));
      
			delay(10);
      
		}
    
	}
  
	Serial.println("\n\n");
  
	delay(10 * 1000);
  
}

***คำอธิบายส่วน void loop คือ ให้มีการวนลูปค้นหาไวไฟรอบตัวไปเรื่อยๆ และกำหนดให้แสดงผลลัพธ์เป็นชื่อไวไฟรอบตัว***

# การทดลองที่ 3 เรื่อง การเขียนโปรแกรมเอ้าพุทสัญญาณดิจิทัล

include <Arduino.h>
include <ESP8266WiFi.h>

int cnt = 0;

***คำอธิบาย คือ กำหนดให้ตัวแปร cnt มีค่าเริ่มต้นที่ 0 ***

void setup()

{

	Serial.begin(115200);
  
	pinMode(0, OUTPUT);
  
	Serial.println("\n\n\n");
  
  ***คำอธิบายส่วน setup คือ กำหนดให้port 0 เป็น output และserial port มีความเร็ว 115200 ms ***
  
}

void loop()

{
	cnt++;
  
	if(cnt % 2) {
  
		Serial.println("========== ON ===========");
    
		digitalWrite(0, HIGH);
    
	} else {
  
		Serial.println("========== OFF ===========");
    
		digitalWrite(0, LOW);
    
	}
  
	delay(500);
  
}

***คำอธิบายส่วน void loop คือ มีการวนลูปโปรแกรมทุก 500 ms และกำหนดตัวแปร cnt หาร 2 ลงตัว นั้นหมายความว่า เมื่อตัวแปรเป็นเลขคู่ ตัวโปรแกรมจะแสดงค่าว่า HIGH ทำให้ไฟติด ส่วนเมื่อ cnt เป็นเลขคี่ โปรแกรมก็จะอ่านค่าได้ว่า LOW ทำให้ไฟนั้นดับ***

# การทดลองที่ 4 เรื่อง การเขียนโปรแกรมเชื่อต่อไวไฟและเว็บเซอร์เวอร์

include <Arduino.h>

include <ESP8266WiFi.h>

int cnt = 0;

**คำอธิบาย คือ กำหนดให้ตัวแปร cnt มีค่าเริ่มต้นที่ 0 ***

void setup()

{

	Serial.begin(115200);
  
  pinMode(0, INPUT);
  
	pinMode(2, OUTPUT);
  
	Serial.println("\n\n\n");
  
}

 ***คำอธิบายส่วน setup คือ กำหนดให้port 0 เป็น input,port 2 ให้เป็น output และserial port มีความเร็ว 115200 ms ***
  
void loop()

{
	int val = digitalRead(0);
  
	Serial.printf("======= read %d\n", val);
  
	if(val==1) {
  
		digitalWrite(2, LOW);
    
	} else {
  
		digitalWrite(2, HIGH);
    
	}
  
	delay(100);
  
}

***คำอธิบายส่วน void loop คือ เริ่มต้นให้digital read อ่านค่าที่ port 0 ถ้าค่าที่อ่านได้เท่ากับ 1 โปรแกรมจะแสดงผลลัพธ์ที่ port 2 เท่ากับ LOW ทำให้ไฟดับ* แล้วถ้าหากค่าที่อ่านได้เท่ากับ 0 โปรแกรมจะแสดงผลลัพธ์ที่ port 2 เท่ากับ HiGH ทำให้ไฟเปิด โดยโปรแกรมจะวนลูปทุกๆ 100 ms***


# การทดลองที่ 5 เรื่อง การเขียนโปรแกรมสร้างไวไฟแอคเซสพ้อยท์
## สร้างไวไฟผ่านเว็ฐเซิร์ฟเวอร์
#include <ESP8266WiFi.h>
//#include <WiFiClient.h>
#include <ESP8266WebServer.h>

const char* ssid = "HI_BMFWIFI_2.4G";
const char* password = "0819110933";

ESP8266WebServer server(80);

int cnt = 0;

void setup(void){
	Serial.begin(115200);

	WiFi.mode(WIFI_STA);
	WiFi.begin(ssid, password);
	while (WiFi.status() != WL_CONNECTED) {
		delay(500);
		Serial.print(".");
	}
	Serial.print("\n\nIP address: ");
	Serial.println(WiFi.localIP());

	server.onNotFound([]() {
		server.send(404, "text/plain", "Path Not Found");
	});

	/// http://192.0.0.1/ = Hello cnt: ???
	server.on("/", []() {
		cnt++;
		String msg = "Hello cnt: ";
		msg += cnt;
		server.send(200, "text/plain", msg);
	});
	/// http://192.0.0.1/on = Hello cnt: ???
	server.on("/on", []() {
		cnt++;
		String msg = "Switch on ";
		msg += cnt;
		server.send(200, "text/plain", msg);
	});
	/// http://192.0.0.1/off = Switch off: ???
	server.on("/off", []() {
		cnt++;
		String msg = "Hello cnt: ";
		msg += cnt;
		server.send(200, "text/plain", msg);
	});

	server.begin();
	Serial.println("HTTP server started");
}

void loop(void){
  server.handleClient();
}
