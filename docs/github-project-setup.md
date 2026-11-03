# إعداد GitHub Project — خطوات النسخ

> الهدف: كل مشروع جديد ياخد نفس الحقول والليبلات والأتمتة، من غير أي إعداد يدوي.

## 1. الـ Project القالب — جاهز

**القالب:** https://github.com/users/kseadawy/projects/9

الحقول والعروض (اللوحة + الجدول) مضبوطة فيه بالفعل. اللي تحت ده مرجع لو حبيت تعيد بناءه من الصفر.

| الحقل | النوع | القيم |
|---|---|---|
| Status | Single select | Backlog · Ready · In Progress · In Review · In QA · Blocked · Done |
| Phase | Single select | الفكرة · اكتشاف · معمارية · دورة · تشغيل |
| Cycle | Text | C1, C2, C3 … |
| Tier | Single select | 0 · 1 |
| Priority | Single select | P0 · P1 · P2 |
| Kind | Single select | Feature · Bug · Chore · Security · Docs |

> اسم `Type` محجوز في GitHub (Issue types)، فبنستخدم `Kind`.

## 2. الليبلات (على الريبو)

`bug` · `security` · `feature` · `agent` · `infra` · `docs`

## 3. الأتمتة (Built-in workflows) — يدوي في الواجهة

الـ API بيسمح بالحذف بس، مش بالتفعيل. فعّلهم مرة واحدة من **Project → ⋯ → Workflows**:

| الحدث | الحركة |
|---|---|
| Item added to project | Status → Backlog |
| Pull request linked to issue | Status → In Review |
| Pull request merged | Status → Done |
| Item closed | Status → Done |

> **مهم:** الـ Auto-add مش بيتنسخ مع Duplicate — لازم تضيفه في كل مشروع.

## 4. العروض (Views)

- **اللوحة:** تجميع حسب Status
- **الجدول:** كل العناصر
- **النسخة الحالية** (لكل مشروع): فلتر `Cycle = C#` + ترتيب حسب Priority
- **الباجات:** فلتر `Kind = Bug`
- **الأمن:** فلتر ليبل `security`

## 5. نسخه لكل مشروع

**حساب شخصي:** `⋯ → Duplicate project` → اسم المشروع → اربطه بالريبو.

**Organization:** ممكن تعمل **Make a template** رسمي، وساعتها «Use template» بضغطة.

> Duplicate بينقل: الحقول، العروض، الـ workflows المضبوطة، والـ draft issues. **مش** بينقل الـ Auto-add.

## 6. Branch protection على الفرع الرئيسي

**Settings → Branches → Add rule** على `main`:

- [ ] Require status checks to pass — اختار `Secret scan` و`Tests`
- [ ] Require pull request before merging (حتى لو إنت لوحدك — ده اللي بيمنع التجاوز)
- [ ] Require approvals: 0 لإنت لوحدك، 1 لو بقى فيه فريق
- [ ] Do not allow bypassing

## 7. تعريف «المشروع بدأ»

المشروع ما بدأش غير لما:

- [ ] الحقول والليبلات والأتمتة موجودة
- [ ] CI شغال وعدّى أول مرة
- [ ] Branch protection مفعّل
- [ ] صفحة الدورة C1 معمولة ومرتبطة
