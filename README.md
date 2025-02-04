# مشروع روبوت بشري - التحكم في محركات السيرفو

## نظرة عامة على المشروع
يهدف هذا المشروع إلى التحكم في **6 محركات سيرفو** لمحاكاة حركة المشي في الروبوت البشري باستخدام **Arduino**.

## آلية عمل الكود:
1. **حركة المسح (Sweep) لمدة ثانيتين**  
   - تتحرك جميع محركات السيرفو من **0° إلى 180°** بسلاسة.  
2. **تثبيت المحركات عند 90°**  
   - بعد ثانيتين، تتوقف جميع المحركات عند **90°**.

## كود الأردوينو:
- الكود موجود في ملف `servo_control.ino`.  
- يستخدم مكتبة `Servo.h` للتحكم في المحركات.

## **خوارزمية المشي في الروبوت البشري**:
1. رفع الساق اليمنى (تحريك الزوايا لتغيير توزيع الوزن).  
2. تحريك الساق اليمنى للأمام.  
3. خفض الساق اليمنى على الأرض ونقل الوزن إليها.  
4. رفع الساق اليسرى.  
5. تحريك الساق اليسرى للأمام.  
6. تكرار العملية للحصول على حركة مشي مستمرة.

## **طريقة التشغيل:**
1. قم برفع ملف `servo_control.ino` إلى لوحة **Arduino Uno**.  
2. وصل 6 محركات سيرفو بالمنافذ الرقمية **D3, D5, D6, D9, D10, D11**.  
3. شغل الأردوينو وشاهد حركة المحركات.

   الكود(بدون موضوع)
رهف عادل
​
أنت​
https://www.tinkercad.com/things/lcpyjNqpXiL/editel?sharecode=_W-_rWX3pix6sgdvzj6P3nirFDF2opc6EZ0xXh-aMkE
	
Login - Tinkercad
www.tinkercad.com
#include <Servo.h> // استدعاء مكتبة السيرفو

Servo servo1, servo2, servo3, servo4, servo5, servo6; // تعريف 6 محركات سيرفو

void setup() {
  // ربط المحركات بالمنافذ المناسبة
  servo1.attach(9);   // محرك 1 إلى D9
  servo2.attach(10);  // محرك 2 إلى D10
  servo3.attach(11);  // محرك 3 إلى D11
  servo4.attach(3);   // محرك 4 إلى D3
  servo5.attach(5);   // محرك 5 إلى D5
  servo6.attach(6);   // محرك 6 إلى D6

  // تحريك جميع المحركات من 0 إلى 180 درجة ثم العودة
  for (int pos = 0; pos <= 180; pos++) {
    servo1.write(pos); // تحريك المحرك 1
    servo2.write(pos); // تحريك المحرك 2
    servo3.write(pos); // تحريك المحرك 3
    servo4.write(pos); // تحريك المحرك 4
    servo5.write(pos); // تحريك المحرك 5
    servo6.write(pos); // تحريك المحرك 6
    delay(15); // تأخير للحصول على حركة سلسة
  }

  for (int pos = 180; pos >= 0; pos--) {
    servo1.write(pos); // العودة للمحرك 1
    servo2.write(pos); // العودة للمحرك 2
    servo3.write(pos); // العودة للمحرك 3
    servo4.write(pos); // العودة للمحرك 4
    servo5.write(pos); // العودة للمحرك 5
    servo6.write(pos); // العودة للمحرك 6
    delay(15); // تأخير للحصول على حركة سلسة
  }
}

void loop() {
  // تثبيت جميع المحركات عند 90 درجة
  servo1.write(90);
  servo2.write(90);
  servo3.write(90);
  servo4.write(90);
  servo5.write(90);
  servo6.write(90);
  delay(1000); // الانتظار لمدة ثانية
}


