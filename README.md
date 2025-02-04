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

