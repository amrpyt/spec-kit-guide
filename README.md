<div align="center">

# 📚 Spec-Kit Complete Guide

### Making GitHub Spec-Kit simple. Really simple.

[![Official Spec-Kit](https://img.shields.io/badge/Based%20on-github%2Fspec--kit-blue?style=for-the-badge)](https://github.com/github/spec-kit)
[![Forked](https://img.shields.io/badge/Documentation-amrpyt%2Fspec--kit-guide-green?style=for-the-badge)](https://github.com/amrpyt/spec-kit-guide)
[![Arabic Version](https://img.shields.io/badge/العربية-README--AR-orange?style=for-the-badge)](./README-AR.md)

**[📖 Quick Guide](./spec-kit-quick-guide.md)** • **[📚 Comprehensive Guide](./spec-kit-comprehensive-guide.md)** • **[🐛 Error Recovery](./spec-kit-comprehensive-guide.md#error-recovery--debugging)**

</div>

---

## 🎯 The Problem

You want to build software. The official Spec-Kit docs are good, but they're **dense**. 

You read them → You get confused → You make mistakes → **You don't know what to do when things break.**

### This guide fixes that.

---

## ✨ What Makes This Guide Different?

<table>
<tr>
<td width="50%">

### 📚 **Complete Coverage**
- ✅ Quick Start (5 minutes)
- ✅ Visual diagrams for every step
- ✅ Real-world examples
- ✅ Every command explained

</td>
<td width="50%">

### 🆕 **Unique Addition**
- 🔥 **Error Recovery Guide**
- 🎯 Not in official docs!
- 💡 5 common scenarios + solutions
- 🛠️ Step-by-step fixes

</td>
</tr>
</table>

---

## 🚨 The Game Changer: Error Recovery Guide

**This is what you won't find anywhere else.**

### The Reality:
```
You run: /speckit.implement
Something breaks: ❌ Error!
You think: "Now what?" 😰
```

### This Guide Answers:

| Question | Answer |
|----------|--------|
| 🔍 **What type of error?** | Build / Runtime / Test / Deployment |
| 🎯 **What caused it?** | Bad spec? Bad plan? Bad code? |
| ↩️ **Where to go back?** | Exact command to fix it |
| 🛠️ **How to fix it?** | Step-by-step recovery |

### Real Example:

```diff
❌ Problem: Tests fail after implementation

✅ Solution:
1. Run /speckit.analyze
2. Find the mismatch (spec vs code)
3. Fix at the source
4. Re-run from there

Simple. Clear. Done.
```

---

## 📖 Guide Structure

### **📚 Documentation Files**

| Guide | Purpose | Size | Audience |
|-------|---------|------|----------|
| **[📖 Quick Guide](./spec-kit-quick-guide.md)** | Get started in minutes with visual workflows | ⚡ **Fast** | Beginners, Rapid start |
| **[📚 Comprehensive Guide](./spec-kit-comprehensive-guide.md)** | Complete technical reference with all details | 🔍 **Deep** | Advanced users, Teams |

<details>
<summary><b>📖 Quick Guide Contents (Click to expand)</b></summary>

- **5-Minute Quick Start** - Install and build your first feature
- **Visual Workflows** - Mermaid diagrams for every process
- **Core Commands** - What each command does and when to use it
- **Brownfield Integration** - Easy steps for existing projects
- **Checklist Usage** - When and how to use quality checklists
- **Error Recovery** - What to do when things break
- **Common Scenarios** - Real-world examples and patterns
- **Quick Reference** - Cheat sheets and file locations

</details>

<details>
<summary><b>📚 Comprehensive Guide Contents (Click to expand)</b></summary>

- **System Architecture** - Detailed technical architecture
- **Advanced Installation** - All configuration options
- **Command Deep Dive** - Exhaustive command documentation
- **Brownfield Project Integration** - Complete integration strategies
- **Constitutional Governance** - Nine Articles framework
- **Advanced Workflow Patterns** - Multi-feature, iterative development
- **Template Customization** - Create your own templates
- **Error Recovery & Debugging** - Systematic troubleshooting
- **Multi-Agent Strategies** - Using different AI agents effectively
- **CI/CD Integration** - Pipeline automation and quality gates
- **Performance & Optimization** - Making Spec-Kit faster
- **Troubleshooting Reference** - Complete error reference
- **Best Practices & Patterns** - Team collaboration patterns

</details>

---

## ⚡ Quick Start

```bash
# 1. Install uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# 2. Install Spec-Kit
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# 3. Initialize
cd your-project
specify init --here

# 4. Build your feature
/speckit.constitution
/speckit.specify "Your feature description"
/speckit.plan
/speckit.tasks
/speckit.implement
```

### 🐛 Hit an error?
**→ [Error Recovery Guide](./spec-kit-guide.md#error-recovery--debugging-guide)**

---

## 👥 Who Is This For?

<table>
<tr>
<td width="50%">

### 🎓 **Beginners**
You'll understand **what's happening** and **why**.

No confusion. No guessing.

</td>
<td width="50%">

### 💼 **Experienced Developers**
You'll fix errors **faster** with recovery workflows.

No wasted time. No frustration.

</td>
</tr>
<tr>
<td width="50%">

### 👥 **Teams**
You'll have **consistent practices** with Constitutional Governance.

No conflicts. No technical debt.

</td>
<td width="50%">

### 📚 **Learners**
You'll see **real examples**, not abstract theory.

No confusion. No gaps.

</td>
</tr>
</table>

---

## 🎯 Why This Guide Exists

> **The official Spec-Kit is powerful. But power without clarity is frustrating.**

### The Split:

| Official Docs | This Guide |
|--------------|------------|
| ✅ What the tool does | ✅ How to actually use it |
| ✅ Technical reference | ✅ What to do when it breaks |
| ✅ Core features | ✅ Real-world examples |

**Both are needed. Use both.**

Always check the [official repository](https://github.com/github/spec-kit) for updates.

---

## 🔗 Resources

### 📘 Official Resources
- **[github/spec-kit](https://github.com/github/spec-kit)** - Main repository
- **[Official README](https://github.com/github/spec-kit/blob/main/README.md)** - Core docs
- **[Spec-Driven Development](https://github.com/github/spec-kit/blob/main/spec-driven.md)** - Philosophy

### 📗 This Project
- **[amrpyt/spec-kit-guide](https://github.com/amrpyt/spec-kit-guide)** - Documentation repository
- **[📖 Quick Guide](./spec-kit-quick-guide.md)** - Get started in minutes
- **[📚 Comprehensive Guide](./spec-kit-comprehensive-guide.md)** - Complete technical reference
- **[README-AR.md](./README-AR.md)** - Arabic version (Al-Hariri style)

---

## 🤝 Contributing

<table>
<tr>
<td width="33%">

### 🐛 Found an Error?
Open an issue

</td>
<td width="33%">

### 💡 Better Explanation?
Submit a pull request

</td>
<td width="33%">

### 📝 Add Examples?
We'll review it

</td>
</tr>
</table>

See **[CONTRIBUTING.md](./CONTRIBUTING.md)** for details.

---

## 📄 License

**MIT License** - Same as the original Spec-Kit project.

---

<div align="center">

### ⭐ If this guide helped you, give it a star!

**It helps others find it.**

---

**Made with ❤️ by the community**

Based on **[github/spec-kit](https://github.com/github/spec-kit)**

---

**[📖 Quick Guide](./spec-kit-quick-guide.md)** • **[📚 Comprehensive Guide](./spec-kit-comprehensive-guide.md)** • **[🇸🇦 النسخة العربية](./README-AR.md)**

</div>
