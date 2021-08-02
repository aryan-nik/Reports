# آشنایی با Git 



------



### مفهوم Repository

هر Repository در حقیقت مخزن تمام فایل های یکی پروژه های شما است. در هر مخزن میتوانید تاریخچه ی کاملی از تمام ورژن ها و تغییرات پروژه ی خود را ثبت کنید. با کمک دستوراتی که در ادامه به آن میپردازیم میتوانید حتی کوچیک ترین تغیرات را ثبت و بازبینی کنید.



### ساخت مخزن

ابتدا به پوشه ای که قرار است پروژه ی شما در آن قرار بگیرد بروید و دستور زیر را اجرا کنید:

```bash
git init .
```

بعد از اجرای این دستور یک مخرن خالی ایجاد میشود. و حالا میتوانید از تمام امکانات گیت استفاده کنید.





### افزودن فایل



حالا یک فایل جدید ایجاد میکنیم: 

```bash
touch index.html
```

میخواهیم گیت را از فایل جدیدی که ساخته ایم با خبر کنیم تا تمامی تغییرات روی آن را برای ما ثبت کند.

دستور status به ما تغییرات فعلی را نشان میدهد.

```bash
git status
```

این دستور خروجی زیر را به ما میدهد:

```bash
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html

nothing added to commit but untracked files present (use "git add" to track)


```

همان طور که در خروجی مشخص است گیت از فایل جدید ما با خبر هست حالا باید دستوری بدهیم تا تغییرات روی این فایل را کنترل کند. از دستور add برای این کار استفاده میکنیم:

 

```bash
git add .

```

کاراکتر "." نشان میدهد میخواهیم تمام تغییرات را در پوشه ی جاری کنترل کنیم. میتوانید به جای نقطه اسم فایل را بنویسید در آن صورت فقط تغییرات روی آن فایل ثبت میشود. به این صورت:

```bash
git add index.html
```

تا اینجا تغییراتی که اعمال کرده ایم ذخیره نشده اند فقط به گیت فهمانده ایم که کدام تغییرات را میخواهیم ثبت یا به اصطلاح stage کنیم. در ادامه میخواهیم این تغییرات را در مخزن خود ذخیره کنیم.



### Commit

برای دخیره ی نهایی تغییراتی که با دستور add آن ها به اصطلاح stage کرده ایم، از دستور commit استفاده میکنیم.

```bash
git commit -m "add index.html"
```

```bash
[master (root-commit) 21c9dfd] add index.html
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 index.html
```

در خروجی به ما نشان داده میشود که دستور به درستی وارد شده و از تمام تغییرات تا به حالا در مخزن ما ذخیره میشود. از این پس هر تغییر دیگری در مخزن نیازمند این است که مراحل قبلی را طی کنیم. به عنوان مثال کدهای زیر را در فایل index وارد میکنیم:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Hello World!</title>
</head>
<body>
  <h1>Hello World!</h1>
</body>
</html>
```

 مجددا از دستور Status برای بررسی تغییرات استفاده میکینم:

```bash
git status
```

```bash
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html

```

همان طور که می بینید گیت از تغییرات روی فایل index.html با خبر هست و این بار به پیام modified را نشان میدهد. این یعنی مجددا باید تغییرات اعمال شده ابتدا Stage شده و سپس در مخزن ذخیره شود.

```bash
git add index.html
```

با دستور بالا مجددا تغییرات Stage شده و حالا برای ذخیره ی کامل تغییرات باید باهم از دستور commit استفاده کنیم.

```bash
git commit -m "modified index.html"
[master f8a03ca] modified index.html
 1 file changed, 12 insertions(+)
```

به این ترتیب تمام تغییرات تا به اینجا به صورت دایم در مخزن یا همان repository ما ذخیره شد.

