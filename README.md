# 📚 Spec-Kit Complete Guide - دليلك الشامل بالعربي

> **دليل شامل ومبسط لاستخدام GitHub Spec-Kit مع إضافات مجتمعية قيّمة**

[![Official Spec-Kit](https://img.shields.io/badge/Based%20on-github%2Fspec--kit-blue)](https://github.com/github/spec-kit)
[![Forked](https://img.shields.io/badge/Fork-amrpyt%2Fspec--kit-green)](https://github.com/amrpyt/spec-kit)
[![Arabic Guide](https://img.shields.io/badge/Language-العربية%20%2B%20English-orange)](./spec-kit-guide.md)

---

## 🎯 ليه الدليل ده مهم؟

**GitHub Spec-Kit** أداة قوية جداً، لكن التوثيق الرسمي ممكن يكون معقد للمبتدئين. 

**الدليل ده بيقدم:**

### ✨ المميزات الأساسية

1. **🚀 Quick Start في 5 دقائق** - ابدأ فوراً بدون تعقيدات
2. **📊 Visual Diagrams** - مخططات توضيحية لكل خطوة
3. **💡 أمثلة عملية** - سيناريوهات حقيقية من مشاريع واقعية
4. **🔧 Command Reference كامل** - شرح تفصيلي لكل أمر

### 🆕 الإضافة الأهم: Error Recovery Guide

**هذا القسم غير موجود في التوثيق الرسمي!**

عندما تقابل error أثناء التطوير، الدليل بيوضح لك:
- 🔍 **تحديد نوع الخطأ** - Build/Runtime/Test/Deployment
- 🔄 **Workflow للتعافي** - خطوات منهجية لحل المشكلة
- 📋 **5 سيناريوهات شائعة** مع الحلول التفصيلية
- ✅ **Best Practices** للوقاية من الأخطاء

#### مثال عملي من الدليل:

```
❌ المشكلة: Tests فشلت بعد Implementation

✅ الحل:
1. /speckit.analyze - تحليل المشكلة
2. تحديد السبب (Spec خطأ؟ Implementation خطأ؟)
3. الرجوع للخطوة المناسبة
4. إعادة التنفيذ
```

---

## 📖 الدليل الكامل

### [👉 اقرأ الدليل الكامل هنا: spec-kit-guide.md](./spec-kit-guide.md)

**الدليل يحتوي على 1500+ سطر من الشرح التفصيلي!**

#### 📚 المحتوى الأساسي
- **TL;DR** - ابدأ في 5 دقائق
- **Installation & Setup** - التثبيت خطوة بخطوة
- **Complete Workflow** - الـ Workflow الكامل بالتفصيل
- **Command Reference** - شرح كل أمر مع أمثلة
- **Constitutional Governance** - المبادئ التسعة
- **Cheatsheet** - مرجع سريع

#### 🆕 الإضافات المجتمعية
- **Error Recovery & Debugging Guide** - دليل شامل للتعامل مع الأخطاء
  - Error Type Identification
  - Recovery Workflows مع Diagrams
  - 5 Common Scenarios بالحلول
  - Prevention Best Practices

---

## 🚀 Quick Start

```bash
# 1. Install uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# 2. Install Spec-Kit
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# 3. Initialize
cd your-project
specify init --here

# 4. Start building!
/speckit.constitution
/speckit.specify "Your feature description"
/speckit.plan
/speckit.tasks
/speckit.implement
```

**لو قابلك error؟** شوف [Error Recovery Guide](./spec-kit-guide.md#error-recovery--debugging-guide) في الدليل!

---

## 🎓 مين يستخدم الدليل ده؟

### ✅ مناسب لـ:
- **المبتدئين** - شرح مبسط وواضح
- **المطورين المحترفين** - Error Recovery Workflows
- **الفرق** - Best Practices و Constitutional Governance
- **المتعلمين** - أمثلة عملية وسيناريوهات حقيقية

### 💪 هتتعلم:
- كيف تستخدم Spec-Kit بكفاءة
- كيف تتعامل مع الأخطاء بشكل منهجي
- كيف تطبق Constitutional Governance
- كيف تبني features بـ TDD

---

## 🔗 الموارد

### الريبو الأصلي
- **Official Repository:** [github/spec-kit](https://github.com/github/spec-kit)
- **Official README:** [Documentation](https://github.com/github/spec-kit/blob/main/README.md)
- **Spec-Driven Development:** [Guide](https://github.com/github/spec-kit/blob/main/spec-driven.md)

### Fork الخاص بينا
- **Forked Repository:** [amrpyt/spec-kit](https://github.com/amrpyt/spec-kit)
- مربوط بالريبو الأصلي ومتزامن معاه

---

## ⚠️ ملاحظة مهمة

هذا الدليل **مجتمعي** ومبني على الريبو الرسمي [github/spec-kit](https://github.com/github/spec-kit).

**الفرق الأساسي:**
- ✅ **الريبو الرسمي** = الأداة نفسها + التوثيق الأساسي
- ✅ **هذا الدليل** = شرح مبسط + Error Recovery + أمثلة عملية + إضافات مجتمعية

**دايماً راجع الريبو الرسمي** للتحديثات والميزات الجديدة.

---

## 🤝 المساهمة

الدليل ده مفتوح للمساهمات! 

- وجدت خطأ؟ افتح Issue
- عندك إضافة؟ اعمل Pull Request
- عايز تحسن شرح؟ ساهم معانا

شوف [CONTRIBUTING.md](./CONTRIBUTING.md) للتفاصيل.

---

## 📄 الترخيص

MIT License - متوافق مع الريبو الأصلي

---

<div align="center">

**🌟 لو الدليل ساعدك، متنساش تدي Star للريبو! 🌟**

**Made with ❤️ by the community | Based on [github/spec-kit](https://github.com/github/spec-kit)**

</div>
