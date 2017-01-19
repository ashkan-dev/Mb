# [TeleEliza](https://telegram.me/tele_eliza)

**A PowerFul Telegram Tg-Cli Bot Based On [SeedTeam/TeleSeed](https://github.com/SEEDTEAM/TeleSeed).**
> این ربات تنها در سوپرگروه ها و پی وی کارکرد دارد

> این سورس بطور کامل دوباره نویسی شده است

> این سورس به دستورات با 2 زبان فارسی و انگیسی پاسخ میدهد

> پاسخ دهی های ربات بطور کامل به زبان شیرین فارسی میباشد

# نصب ربات
```sh
# اول از همه شما باید یه سرور اوبونتو ورژن 16 به بالا داشته باشید.

# ترمینال رو باز میکنیم و دستورات پایین رو وارد میکنیم
sudo apt-get install libreadline-dev libconfig-dev libssl-dev lua5.2 liblua5.2-dev lua-socket lua-sec lua-expat libevent-dev make unzip git redis-server autoconf g++ libjansson-dev libpython-dev expat libexpat1-dev

# حالا وقت نصب رباته. دستورای زیر رو به ترتیب توی ترمینال وارد میکنیم
cd $HOME
git clone https://github.comashkan-dev/mb.git
cd mb
chmod +x run.sh
./run.sh install
# حالا صبر میکنیم تا کارش تموم بشه و بعد ...
./run.sh
# حال از شما شماره میخواد ، شماره رو وارد کرده و سپس کد فعالسازی رو وارد میکنید
# توجه* : با توجه به تست ما شماره روسیه بالاترین سرعت رو داره*
```
#### نصب ربات به صورت یک دستور
```sh
sudo apt-get install libreadline-dev libconfig-dev libssl-dev lua5.2 liblua5.2-dev lua-socket lua-sec lua-expat libevent-dev make unzip git redis-server autoconf g++ libjansson-dev libpython-dev expat libexpat1-dev && cd $HOME && git clone https://github.com/ashkan-dev/mb.git && cd mb && chmod +x run.sh && ./run.sh install && ./run.sh
```

#### رفع اررور
اگر هنگام ران کردن ربات با اررور پایین برخوردید از دستور زیر استفاده نمایید
```sh
# Error : /usr/bin/env: ‘bash\r’: No such file or directory

cd mb
sed -i 's/\r$//' run.sh
```

* * *

## تنظیم سودو
برای تنظیم سودو ابتدا به پوشه ی

**./bot/bot.lua**

رفته و در قسمت

```
sudo_users = {
    201707431,
    0
  }
```
حال به جای 0 آیدی خودتون رو قرار بدید
* * *

# دستورات ربات

### > chat_mod.lua
| دستور(EN) | دستور(FA) | توضیحات |
|:----------|:----------|:--------------|
| [/!#]add | نصب | اضافه کردن گروه به لیست گروه های مدیریت شده |
| [/!#]rem | لغو نصب | حذف گروه از لیست گروه های مدیریت شده
| [/!#]admins | ادمین ها | نمایش ادمین های گروه
| [/!#]gpinfo | اطلاعات گروه | نمایش اطلاعات اصلی گروه
| [/!#]modlist | مدیران فرعی | نمایش لیست مدیران فرعی ربات در گروه
| [/!#]bots | ربات ها | نمایش لیست ربات های معمولی موجود در گروه
| [/!#]owner | مدیر اصلی | نمایش آیدی مدیر اصلی(اونر) ربات در گروه
| [/!#]filter [word] | فیلتر عبارت | فیلتر کردن یک کلمه یا عبارت در گروه
| [/!#]rf [word] | رفع فیلتر عبارت | رفع فیلتر یک کلمه یا عبارت فیلتر شده
| [/!#]filterlist | لیست فیلتر | نمایش لیست کلمات فیلتر شده در گروه
| [/!#]del {Reply} | حذف | حذف یک پیام در گروه با استفاده از ریپلای
| [/!#]setlink | تنظیم لینک | تنظیم لینک یک گروه
| [/!#]link | لینک | دریافت لینک تنظیم شده
| [/!#]setowner [id/username/reply] | تنظیم مدیر اصلی | تنظیم مدیر اصلی(اونر) برای ربات در گروه
| [/!#]promote [id/username/reply] | ترفیع | ترفیع یک کاربر به عنوان مدیر فرعی ربات
| [/!#]demote [id/username/reply] | عزل | عزل یک مدیر فرعی به یک کاربر عادی
| [/!#]clean [filterlist/silentlist/owner/gbanlist/banlist/modlist/deleted/bots] | پاکسازی | پاکسازی (لیست فیلتر، لیست سکوت ، مدیر اصلی ، مسدود همگانی ، لیست مسدود ، لیست مدیران فرعی ، کاربران دلیت اکانت در گروه ، ربات های معمولی موجود در گروه)ا
| [/!#]me | ---- | دریافت مقام کاربر در گروه

### > ban.lua
| دستور(EN) | دستور(FA) | توضیحات |
|:----------|:----------|:--------------|
| [/!#]ban [id/reply/username] | مسدود | مسدود کردن یک کاربر از گروه
| [/!#]unban [id/reply/username] | ازاد |آنبن کردن یک کاربر در گروه
| [/!#]banall [id/reply/username] | مسدود همگانی | مسدود کردن یک کار از تمامی گروه های ربات
| [/!#]unbanall [id/reply/username] | ازاد همگانی | آنبن کردن یک کاربر از تمامی گروه های ربات
| [/!#]silent [id/reply/username] | ساکت کردن | اضافه کردن یا حذف کردن یک کاربر از لیست افراد سایلنت شده
| [/!#]kick [id/reply/username] | اخراج | اخراج فرد از گروه
| [/!#]id [reply/username] | ایدی | دریافت اطلاعات کاربر
| [/!#]idfrom [reply] | ایدی فروارد| دریافت اطلاعات فرد ارسال کننده ی پیام فروارد شده
| [/!#]banlist | لیست مسدود | دریافت لیست کاربران بن شده
| [/!#]gbanlist | لیست مسدود همگانی | دریافت لیست کاربران مسدود شده از تمامی گروه های ربات
| [/!#]silentlist | لیست سکوت | دریافت لیست کاربران سایلنت شده در گروه

### > locks.lua
| دستور(EN) | دستور(FA) | توضیحات |
|:----------|:----------|:--------------|
| [/!#]lock link | قفل لینک | قفل کردن لینک
| [/!#]lock forward | قفل فروارد | قفل کردن فروارد در گروه
| [/!#]lock bot | قفل ربات | قفل کردن ربات ورود ربات به گروه
| [/!#]lock inline | قفل کیبورد | قفل کردن کیبورد شیشه ای
| [/!#]lock cmd | قفل دستورات | پاسخ ندادن ربات به کاربران عادی
| [/!#]lock english | قفل انگلیسی | قفل انگلیسی نویسی
| [/!#]lock spam | قفل اسپم | حذف پیام های طولانی در گروه
| [/!#]lock flood | قفل رگباری | قفل پیام های رگباری
| [/!#]lock persian | قفل فارسی | قفل فارسی و عربی نویسی
| [/!#]lock tg | قفل خدمات | حذف پیام های ورود و خروج
| [/!#]lock strict | قفل سخت | اخراج کردن کسانی که در گروه لینک ارسال میکنند
| [/!#]lock audio | قفل صدا | حذف صدا های ارسال شونده در گروه
| [/!#]lock photo | قفل عکس | حذف عکس های ارسال شده در گروه
| [/!#]lock video | قفل ویدیو | حذف ویدیو های ارسالی در گروه
| [/!#]lock file | قفل فایل | حذف فایل های ارسالی در گروه
| [/!#]lock text | قفل متن | حذف متن های ارسالی در گروه
| [/!#]lock gif | قفل گیف | حذف گیف های ارسالی در گروه
| [/!#]lock sticker | قفل استیکر | حذف استیکر های ارسالی در گروه
| [/!#]lock contact | قفل مخاطب | حذف مخاطب های ارسالی در گروه
| [/!#]lock chat | قفل چت | حذف هرگونه مطلب یا پیام ارسالی در گروه
| [/!#]lock wlc | قفل خوشامد | فعال کردن خوش آمد گویی در گروه
| [/!#]unlock [lockname] | بازکردن قفل | غیرفعال کردن قفل مورد نظر
| [/!#]setflood [num] | تنظیم رگباری | تنظیم حساسیت پیام های رگباری
| [/!#]settings | تنظیمات | دریافت تنظیمات گروه

بقیه ی دستورات رو میتونید با مراجعه به پلاگین ها متوجه بشید. بزودی بقیه ی دستورات رو همین گیت قرار خواهند گرفت

## برنامه نویس و توسعه دهنده
[اشکان پیرجهان](https://telegram.me/A_S_H_K_A_N_PJ)

* * *
```
      Powered By : ashkan.pj
             
