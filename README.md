# چیت شیت جنگو | Django Cheat Sheet

## <a name=''></a>فهرست

<!-- vscode-markdown-toc -->

- [فهرست](#)
- [جنگو ادمین | Django Admin](#DjangoAdmin)
  - [تغییر جنگو ادمین یکی از اپ های خود جنگو یا یک اپ شخص ثالث](#-1)
- [احراز هویت Authentiaction](#Authentiaction)
  - [هش کردن کلمه عبور و اعتبار سنجی اش Password Hashing and Validating](#PasswordHashingandValidating)

<!-- vscode-markdown-toc-config
	numbering=false
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->

## <a name='DjangoAdmin'></a>جنگو ادمین | Django Admin

### <a name='-1'></a>تغییر جنگو ادمین یکی از اپ های خود جنگو یا یک اپ شخص ثالث

برای انجام این کار لازمه اول اون پنل ادمین ای که میخواهیم تغییرش بدیم رو unregister کنیم. روش درست این کار:

```python
try:
    admin.site.unregister(User)
except admin.sites.NotRegistered:
    pass
```

بعدش میتونیم ازش ارث بری کنیم و تغییرش بدیم یا بدون ارث بری تغییرش بدیم و admin.site.register اش کنم.

## <a name='Authentiaction'></a>احراز هویت Authentiaction

### <a name='PasswordHashingandValidating'></a>هش کردن کلمه عبور و اعتبار سنجی اش Password Hashing and Validating

```python
from django.contrib.auth.hashers import make_password, check_password

hashed_pwd = make_password("plain_text")
check_password("plain_text",hashed_pwd)  # returns True
```
