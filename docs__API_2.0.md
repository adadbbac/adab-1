# API 2.0 — الأدب العربي في البكالوريا

## الصحة
`GET /api/health`

## حساب التلميذ
- `POST /api/signup`
- `POST /api/login`
- `GET /api/me`

## الأستاذ
- `POST /api/teacher/login`
- `GET /api/teacher/students`
- `PATCH /api/teacher/students/:id`

## المحتوى
- `GET /api/content?axis=1&kind=lesson`
- `GET /api/teacher/content`
- `POST /api/teacher/content`
- `PATCH /api/teacher/content/:id`
- `DELETE /api/teacher/content/:id` (أرشفة لا حذف فعلي)

## التفاعل
### التلميذ
- `GET/POST /api/student/messages`
- `GET /api/student/missions`
- `POST /api/student/missions/:id/submit`
- `GET /api/student/tests`
- `POST /api/student/answers`
- `GET /api/student/notes`
- `POST /api/student/notes/:id/reply`
- `GET /api/student/announcements`
- `GET/POST /api/student/progress`

### الأستاذ
- `GET/POST /api/teacher/missions`
- `POST /api/teacher/missions/:id/review`
- `GET/POST /api/teacher/messages`
- `GET/POST /api/teacher/notes`
- `GET/POST /api/teacher/announcements`
- `GET/POST /api/teacher/media`
- `GET/POST /api/teacher/tests`
- `GET/POST /api/teacher/settings`
- `GET /api/teacher/activity`

## المصادقة
التوكن في رأس الطلب:
`Authorization: Bearer <token>`

الجلسات موقعة HMAC، وحسابات التلاميذ تستخدم PBKDF2-SHA-256.

## ملاحظة
هذه المرحلة تجهز القلب المشترك. الواجهة الحالية محفوظة، وسيتم في المرحلة التالية تحويل student.js وteacher.js بالكامل من localStorage إلى هذه الـAPI مع إبقاء الواجهة والسلوك البصري.
