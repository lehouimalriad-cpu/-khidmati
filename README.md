# خدماتي — Full Stack v2
هذه النسخة تجمع:
- Frontend عربي متجاوب.
- Backend Express.
- PostgreSQL.
- JWT Auth.
- حساب عميل/محترف.
- البحث بالمحترفين والخدمات.
- إنشاء الطلبات وإدارتها.
- لوحة مستخدم.
- API للإدارة.
- Docker Compose.

## التشغيل المحلي
1. ثبّت Docker Desktop.
2. افتح الطرفية داخل مجلد المشروع.
3. شغّل:
   docker compose up --build
4. نفّذ schema.sql في PostgreSQL. مثال:
   docker compose exec -T db psql -U postgres -d khidmati < server/schema.sql
5. افتح `client/index.html` في المتصفح.

إذا كانت الواجهة تُفتح عبر `file://` وحدثت مشكلة CORS، شغّل خادم ملفات بسيط داخل client:
`python -m http.server 5173`
ثم افتح `http://localhost:5173`.

## حساب المدير
إنشاء المدير لا يتم تلقائياً لأسباب أمنية. بعد تسجيل حساب، غيّر role لذلك المستخدم إلى admin من PostgreSQL فقط.

## قبل الإطلاق
استخدم HTTPS، سر JWT قوي، PostgreSQL مُدار، نسخ احتياطية، rate limiting، تحقق من المدخلات، تخزين صور خارجي، ومزود دفع معتمد. لا تخزن بيانات البطاقات البنكية داخل قاعدة بياناتك.
