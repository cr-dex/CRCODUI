# CRCODUI
![CRCODUI](https://raw.githubusercontent.com/cr-dex/CRCODUI/refs/heads/main/crcodui.jpg)

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

### 1. COLOR(text, text2)

**الوظيفة:**
تطبق تدرجات لونية عشوائية متناسقة على النصوص في الطرفية ( تحتاج الى print قبلها )

**الاستخدام:**
```python
from CRCODUI import COLOR

# مثال بسيط
print(COLOR("Welcome","Powered by @cr_dex"))
او
print(COLOR("Welcome Powered by @cr_dex"))
# ستتدرج الجملة Welocome Powerd by @cr_dex بالوان فائقة الجمال
```

**المميزات:**
- إضافة تأثيرات بصرية احترافية للمخرجات
- تحسين قراءة وتنسيق النصوص في المحطة الطرفية
- دعم الألوان المتقدمة و العشوائبة فى التلوين كل مرة
- وفر عليك مئات السطور من متغيرات الالوان

---

### 2. CONSOLE(File)
**الوظيفة:**
تعرض محتوى ملفات Python معSyntax Highlighting و كأنك فى محرر اكواد
( لا تحتا الى print )

**الاستخدام:**
```python
from CRCODUI import CONSOLE

# عرض محتوى الملف مع تصميم محرر الاكواد
CONSOLE("my_script.py")
```

**الفائدة:**
- عرض الأكواد بشكل منسق وسهل القراءة
- ترقيم تلقائي للأسطر
- تمييز العناصر البرمجية بالألوان

---

### 3. CONSOLT(text code)

**الوظيفة:**
تعرض نصاً برمجياً مباشرة بلا الحاجة لحفظه فى ملف حتى نعرضه على عكس CONSOLE التى تحتاج حفظ الكود فى ملف حتى تعرضه

**الاستخدام:**
```python
from CRCODUI import CONSOLT

code_snippet = """
def fetch_data():
        data = {
        'status': 200,
        'msg': 'Success'
    }
    return data
print(fetch_data())
"""

CONSOLT(code_snippet)
# سيعرض الكود مع التنسيق والألوان
```

**الفائدة:**
- عرض مقاطع أكواد صغيرة بشكل احترافي
- مفيدة للتوثيق والشروحات
- توضيح الأكواد بسهولة دون إنشاء ملفات

---

### 4. AST(text code)

**الوظيفة:**
تعيد بناء وتنسيق ملفات Python باستخدام Abstract Syntax Tree، لتصحيح المسافات والتنسيق.

**الاستخدام:**
```python
from CRCODUI import AST

# ملف بكود غير منسق
messy_code = """
import os, sys
def   messy_function  ( a ,  b ) : 
 return   a+b
print ( messy_function ( 5 ,  10 ) )
"""
open("code.py", "w").write(messy_code)

AST("code.py") # تم التنسيق بنجاح
ستجد الكود بالشكل التالى
import os
import sys
def messy_function(a,b):
    return a + b
print(messy_function(5, 10))
# الآن الملف منسق بشكل صحيح
```

**الفائدة:**
- تنسيق تلقائي للأكواس الفوضوية
- إصلاح المسافات والمحاذاة توحيد أسلوب الملفات

---

### 5. IN_OUT(version= الاصدار الحالى)
عقل الادخال و الاخراج و الاصدار و الوضع
**الوظيفة:**
من الطرفية بدل التعرض الى ادخال و اخراج و اصدار و وضع
يمكنك كتابة
python3 mycode.py input -o output -v 3.X -m any_thing

**الاستخدام:**
```python
from CRCODUI import IN_OUT

# الحصول على الوسائط
in_file, out_file, version, mode = IN_OUT(VERSION="3.12")
print(f"Input File: {in_file}") # input
print(f"Output File: {out_file}") # output
print(f"Version: {version}") # 3.12
print(f"Mode: {mode}") # any_thing

# اما لو كتبت
in_file, out_file, version, mode = IN_OUT()
print(f"Version: {version}") # 3.X
# عدم تحديد الاصدار سيعطيك الاصدار الذى حددته
```

**الفائدة:**
- معالجة اسطر الادخال و الاخراج بسهولة
- تحديد اصدارات مخصصة لاجزاء محددة من الكود بكفاءة
- دعم متغير اخر اسمه m (--mode)- لاى شيء تريده

---

### 6. IMPORT() - استدعاءات المكتبات ديناميكياً

**الوظيفة:**
استدعاءات مجموعة واسعة من المكتبات المدمجة فى بايثون لتقليل اسطر المكاتب

**الاستخدام:**
```python
from CRCODUI import IMPORT
IMPORT()
os.system("clear")
# لا حاجة لكتابة import os
```

**الفائدة:**
- توفير الوقت في الاستيراد اليدوي
- توفير المكتبات الشهيرة جاهزة للاستخدام
---

### 7. HELP() - عرض المساعدة

**الوظيفة:**
تعرض معلومات مختصرة عن المكتبة والدوال المتاحة بها.

**الاستخدام:**
```python
from CRCODUI import HELP
HELP() # بدون عمل print
```

**الفائدة:**
- الحصول على معلومات مختصرة عن المكتبة
- مرجع سريع أثناء التطوير

---

## 👨‍💻 المطور

تم تطوير هذه المكتبة بواسطة 
@cr_dex على Telegram
https://t.me/cr_dex
 لا تتردد في التواصل للحصول على ملاحظات أو المساهمة.❤️❤️
