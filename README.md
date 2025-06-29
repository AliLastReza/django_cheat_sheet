# چیت شیت جنگو | Django Cheat Sheet

## جنگو ادمین | Django Admin

### تغییر جنگو ادمین یکی از اپ های خود جنگو یا یک اپ شخص ثالث

برای انجام این کار لازمه اول اون پنل ادمین ای که میخواهیم تغییرش بدیم رو unregister کنیم. روش درست این کار:

```python
try:
    admin.site.unregister(User)
except admin.sites.NotRegistered:
    pass
```

بعدش میتونیم ازش ارث بری کنیم و تغییرش بدیم یا بدون ارث بری تغییرش بدیم و admin.site.register اش کنم.

