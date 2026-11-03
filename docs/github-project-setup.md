# إعداد GitHub Project — خطوات النسخ

> الهدف: كل مشروع جديد ياخد نفس الحقول والليبلات والأتمتة، من غير أي إعداد يدوي.

## 1. اعمل الـ Project القالب مرة واحدة

على GitHub: **Projects → New project → Board**، وبعده ضبط الحقول دي:

| الحقل | النوع | القيم |
|---|---|---|
| Status | Single select | Backlog · Ready · In Progress · In Review · In QA · Blocked · Done |
| Phase | Single select | الفكرة · اكتشاف · معمارية · دورة · تشغيل |
| Cycle | Text | C1, C2, C3 … |
| Tier | Single select | 0 · 1 |
| Priority | Single select | P0 · P1 · P2 |
| Type | Single select | Feature · Bug · Chore · Security · Docs |

## 2. الليبلات (على الريبو)

`bug` · `security` · `feature` · `agent` · `infra` · `docs`

## 3. الأتمتة (Built-in workflows)

| الحدث | الحركة |
|---|---|
| Item added | Status → Backlog |
| Pull request linked | Status → In Review |
| Pull request merged | Status → Done |
| Issue closed | Status → Done |

## 4. العروض (Views)

- **النسخة الحالية:** فلتر `Cycle = C#` + ترتيب حسب Priority
- **الباجات:** فلتر `Type = Bug`
- **الأمن:** فلتر `security`
- **اللوحة:** تجميع حسب Status

## 5. نسخه لكل مشروع

`… → Duplicate project` واختار الريبو الجديد.

## 6. Branch protection على الفرع الرئيسي

**Settings → Branches → Add rule** على `master` (أو `main`):

- [ ] Require status checks to pass — اختار `Secret scan` و`Tests`
- [ ] Require pull request before merging (حتى لو إنت لوحدك — ده اللي بيمنع التجاوز)
- [ ] Require approvals: 0 لإنت لوحدك، 1 لو بقى فيه فريق
- [ ] Do not allow bypassing

## 7. تعريف «المشروع بدأ»

المشروع ما بدأش غير لما:

- [ ] الحقول والليبلات والأتمتة موجودة
- [ ] CI شغال وعدّى أول مرة
- [ ] Branch protection مفعّل
- [ ] صفحة الدورة C1 متعملة ومرتبطة