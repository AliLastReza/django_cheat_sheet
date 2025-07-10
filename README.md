# چیت شیت جنگو | Django Cheat Sheet

## 1. <a name=''></a>فهرست

<!-- vscode-markdown-toc -->

- 1. [فهرست](#)
- 2. [جنگو ادمین | Django Admin](#DjangoAdmin)
  - 2.1. [تغییر جنگو ادمین یکی از اپ های خود جنگو یا یک اپ شخص ثالث](#-1)
- 3. [احراز هویت Authentiaction](#Authentiaction)
  - 3.1. [هش کردن کلمه عبور و اعتبار سنجی اش Password Hashing and Validating](#PasswordHashingandValidating)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->

## 2. <a name='DjangoAdmin'></a>جنگو ادمین | Django Admin

### 2.1. <a name='-1'></a>تغییر جنگو ادمین یکی از اپ های خود جنگو یا یک اپ شخص ثالث

برای انجام این کار لازمه اول اون پنل ادمین ای که میخواهیم تغییرش بدیم رو unregister کنیم. روش درست این کار:

```python
try:
    admin.site.unregister(User)
except admin.sites.NotRegistered:
    pass
```

بعدش میتونیم ازش ارث بری کنیم و تغییرش بدیم یا بدون ارث بری تغییرش بدیم و admin.site.register اش کنم.

## 3. <a name='Authentiaction'></a>احراز هویت Authentiaction

### 3.1. <a name='PasswordHashingandValidating'></a>هش کردن کلمه عبور و اعتبار سنجی اش Password Hashing and Validating

```python
from django.contrib.auth.hashers import make_password, check_password

hashed_pwd = make_password("plain_text")
check_password("plain_text",hashed_pwd)  # returns True
```
