# CRCODUI

![Version](https://img.shields.io/badge/version-2.0.3-blue.svg)
![Python](https://img.shields.io/badge/python-3.6%2B-green.svg)
![License](https://img.shields.io/badge/license-MIT-purple.svg)

مكتبة Python متخصصة لتسهيل عمليات التنسيق والإخراج والتلوين والإدخال، مما يجعل الكود أقصر وأسهل في الاستخدام.

---

## 📦 التثبيت

يمكنك تثبيت المكتبة بسهولة باستخدام pip:

```bash
pip install CRCODUI
```

أو الطريقة اليدوية:

```bash
apt install git -y
git clone https://github.com/cr-dex/CRCODUI
cd CRCODUI/dist
pip install crcodui*.whl
```

---

## 🔧 الدوال الرئيسية

### 1. COLOR() - تطبيق التدرجات اللونية

**الوظيفة:**
تطبق تدرجات لونية احترافية على النصوص في المحطة الطرفية.

**الاستخدام:**
```python
from CRCODUI import COLOR

# مثال بسيط
print(COLOR("Welcome to CRCODUI", " - ", "Powered by @cr_dex"))

# تطبيق تدرج لوني على نص
result = COLOR("Hello World")
print(result)
```

**الفائدة:**
- إضافة تأثيرات بصرية احترافية للمخرجات
- تحسين قراءة وتنسيق النصوص في المحطة الطرفية
- دعم الألوان المتقدمة والتدرجات

---

### 2. CONSOLE() - عرض محتوى الملفات

**الوظيفة:**
تعرض محتوى ملفات Python أو النصوص العادية مع ترقيم الأسطر وإبراز الصيغة (Syntax Highlighting).

**الاستخدام:**
```python
from CRCODUI import CONSOLE

# عرض محتوى ملف Python
CONSOLE("my_script.py")

# سيعرض الكود مع ترقيم الأسطر والألوان
```

**الفائدة:**
- عرض الأكواد بشكل منسق وسهل القراءة
- ترقيم تلقائي للأسطر
- تمييز العناصر البرمجية بالألوان

---

### 3. CONSOLT() - عرض النصوص البرمجية مباشرة

**الوظيفة:**
تعرض نصاً برمجياً مباشرة دون الحاجة لملف، مع ترقيم الأسطر والصيغة البصرية.

**الاستخدام:**
```python
from CRCODUI import CONSOLT

code_snippet = """def fetch_data():
    data = {'status': 200, 'msg': 'Success'}
    return data

print(fetch_data())"""

CONSOLT(code_snippet)
# سيعرض الكود مع التنسيق والألوان
```

**الفائدة:**
- عرض مقاطع أكواد صغيرة بشكل احترافي
- مفيدة للتوثيق والشروحات
- توضيح الأكواد بسهولة دون إنشاء ملفات

---

### 4. AST() - تنسيق وتنظيف الأكواد

**الوظيفة:**
تعيد بناء وتنسيق ملفات Python باستخدام Abstract Syntax Tree، لتصحيح المسافات والتنسيق.

**الاستخدام:**
```python
from CRCODUI import AST

# ملف بكود غير منسق
messy_code = """def   messy_function  ( a ,  b ) : 
 return   a+b 

print ( messy_function ( 5 ,  10 ) )"""

# حفظ الكود غير المنسق
with open("messy_script.py", "w") as f:
    f.write(messy_code)

# تنسيق الملف
AST("messy_script.py")

# الآن الملف منسق بشكل صحيح
```

**الفائدة:**
- تنسيق تلقائي للأكواس الفوضوية
- إصلاح المسافات والمحاذاة
- ضمان اتباع معايير PEP 8
- توحيد أسلوب الكود

---

### 5. IN_OUT() - معالجة وسائط سطر الأوامر

**الوظيفة:**
تعالج وسائط سطر الأوامر بمرونة لتحديد ملفات الإدخال والإخراج والإصدار وأوضاع التشغيل.

**الاستخدام:**
```python
from CRCODUI import IN_OUT

# محاكاة وسائط سطر الأوامر
import sys
sys.argv = ['main.py', 'input.py', '-o', 'output.py', '-v', '1.0.0', '-m', 'CLI_MODE']

# الحصول على الوسائط
in_file, out_file, version, mode = IN_OUT(VERSION="1.0.0")

print(f"Input File: {in_file}")
print(f"Output File: {out_file}")
print(f"Version: {version}")
print(f"Mode: {mode}")
```

**الفائدة:**
- معالجة وسائط سطر الأوامر بسهولة
- تحديد الملفات والإعدادات تلقائياً
- دعم أوضاع تشغيل متعددة

---

### 6. IMPORT() - حقن المكتبات ديناميكياً

**الوظيفة:**
تحقن مجموعة واسعة من المكتبات المدمجة والشهيرة مباشرة في الذاكرة للنماذج السريعة.

**الاستخدام:**
```python
from CRCODUI import IMPORT

# حقن جميع المكتبات
IMPORT()

# الآن يمكنك استخدام المكتبات المحقونة مباشرة
try:
    # مثال: استخدام rich (إن كانت محقونة)
    print("المكتبات الشهيرة متاحة الآن!")
except NameError:
    pass
```

**الفائدة:**
- توفير الوقت في الاستيراد اليدوي
- توفير المكتبات الشهيرة جاهزة للاستخدام
- تسريع عملية النماذج السريعة (Prototyping)

---

### 7. HELP() - عرض المساعدة

**الوظيفة:**
تعرض معلومات شاملة عن المكتبة والدوال المتاحة.

**الاستخدام:**
```python
from CRCODUI import HELP

# عرض المساعدة الكاملة
HELP()
```

**الفائدة:**
- الحصول على معلومات شاملة عن المكتبة
- شرح جميع الدوال والوسائط
- مرجع سريع أثناء التطوير

---

## 💡 مثال شامل يجمع كل الدوال

```python
import os
import sys
from CRCODUI import HELP, COLOR, CONSOLE, CONSOLT, AST, IN_OUT, IMPORT

# 1. عرض المساعدة
HELP()

# 2. طباعة نص ملون
print(COLOR("Welcome to CRCODUI Library", " - ", "Powered by @cr_dex"))

# 3. حقن المكتبات
IMPORT()

# 4. معالجة وسائط سطر الأوامر
sys.argv = ['main.py', 'input.py', '-o', 'output.py', '-v', '1.0.0']
try:
    in_file, out_file, ver, mod = IN_OUT(VERSION="1.0.0")
    print(COLOR("Input: ", str(in_file)))
    print(COLOR("Output: ", str(out_file)))
except SystemExit:
    pass

# 5. عرض كود مباشر
code_snippet = """def greet(name):
    return f"Hello, {name}!"
    
print(greet("Python"))"""
CONSOLT(code_snippet)

# 6. تنسيق ملف كود
messy_code = "def add(a,b):\n return a+b"
with open("temp.py", "w") as f:
    f.write(messy_code)

CONSOLE("temp.py")  # عرض قبل التنسيق
AST("temp.py")      # تنسيق الملف
CONSOLE("temp.py")  # عرض بعد التنسيق

# تنظيف
if os.path.exists("temp.py"):
    os.remove("temp.py")
```

---

## 📄 الترخيص

هذا المشروع مرخص تحت رخصة MIT. يمكنك استخدامه وتعديله وتوزيعه بحرية.

## 👨‍💻 المطور

تم تطوير هذه المكتبة بواسطة @cr_dex على Telegram. لا تتردد في التواصل للحصول على ملاحظات أو المساهمة.