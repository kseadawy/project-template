# project-template

> قالب مشروع: القوالب والبوابات والـ CI — حسب **منهجية التطوير v1.3**.
> استخدمه من زرار **Use this template** لما تبدأ أي مشروع جديد.

---

## إيه اللي جواه

| الملف | الوظيفة |
|---|---|
| `.github/workflows/ci.yml` | فحص أسرار (gitleaks) + اختبارات تلقائية حسب التقنية |
| `.github/pull_request_template.md` | تعريف الخلاص + سقف حجم الـ PR |
| `.github/ISSUE_TEMPLATE/` | نماذج مهمة وباج بحقول إجبارية |
| `docs/playbook.md` | النسخة التنفيذية المختصرة من المنهجية |
| `docs/github-project-setup.md` | إعداد الـ Project والليبلات والـ branch protection |

## المراجع

- **المنهجية (المرجع الكامل):** https://app.notion.com/p/40de20b7bf2480978f58c974da467ad9
- **قالب صفحة المشروع:** https://app.notion.com/p/40de20b7bf2480d988b8c3ef4ffcda44

## الليبلات

`bug` · `security` · `feature` · `agent` · `infra` · `docs`

## الشغل على مشروع جديد

1. **Use this template** → ريبو جديد.
2. املأ بطاقة الحالة في `README` بتاع المشروع.
3. اعدّل `ci.yml` لو التقنية مختلفة.
4. فعّل حماية `main` (المطلوب: `Secret scan` و`Tests`) — **محتاجة GitHub Pro للريبو الخاص**، وإلا اعتمد على PR + CI أخضر.
5. **Duplicate** للـ Project القالب (https://github.com/users/kseadawy/projects/9) واربطه بالريبو، وأضف Auto-add.
