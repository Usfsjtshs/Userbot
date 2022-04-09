
from pyrogram import Client, filters
from pyrogram.errors import FloodWait
 
from pyrogram.types import ChatPermissions
 
import time
from time import sleep
import random
 
app = Client("my_account")
 
# Команда type
@app.on_message(filters.command("Type", prefixes=".") & filters.me)
def Type(_, msg):
    orig_text = msg.text.split(".type ", maxsplit=1)[1]
    text = orig_text
    tbp = "" # to be printed
    typing_symbol = "▒"
 
    while(tbp != orig_text):
        try:
            msg.edit(tbp + typing_symbol)
            sleep(0.05) # 50 ms
 
            tbp = tbp + text[0]
            text = text[1:]
 
            msg.edit(tbp)
            sleep(0.05)
 
        except FloodWait as e:
            sleep(e.x)
 
# Команда взлома пентагона
@app.on_message(filters.command("Hack", prefixes=".") & filters.me)
def Hack(_, msg):
    perc = 0
 
    while(perc < 100):
        try:
            text = "👮‍ Взлом пентагона в процессе ..." + str(perc) + "%"
            msg.edit(text)
 
            perc += random.randint(1, 3)
            sleep(0.1)
 
        except FloodWait as e:
            sleep(e.x)
 
    msg.edit("🟢 Пентагон успешно взломан!")
    sleep(3)
 
    msg.edit("👽 Поиск секретных данных об НЛО ...")
    perc = 0
 
    while(perc < 100):
        try:
            text = "👽 Поиск секретных данных об НЛО ..." + str(perc) + "%"
            msg.edit(text)
 
            perc += random.randint(1, 5)
            sleep(0.15)
 
        except FloodWait as e:
            sleep(e.x)
 
    msg.edit("🦖 Найдены данные о существовании динозавров на земле!")
 
 
 
@app.on_message(filters.command("Scan", prefixes=".") & filters.me)
def Scan(_, msg):
	msg.reply_text("Здравствуйте, вас приветствует программа пробива по базе данных. \n\nПредоставляется: Kaspersky")
	msg.delete()
	time.sleep(2)
	msg.reply_text("Вы желаете узнать информацию об аккаунте с которым находитесь в чате?")
	time.sleep(1)
	msg.reply_text("Отправьте ответ с точкой в начале.\n\nВарианты ответа: Да/Нет\n\nПример: .да")
	
@app.on_message(filters.command("Да", prefixes=".") & filters.me)
def Да(_, msg):
	msg.reply_text("Хорошо, тогда я начинаю искать этого человека в базе данных..")
	time.sleep(10)
	msg.reply_text("Нашел, формирую результаты для чтения..")
	time.sleep(7)
	msg.reply_text("И так, результаты:\nДанный пользователь известен как обманщик\nЖалоб на него: 4 штуки\nВывод: Не советую проводить с ним операции продаж и обмена.")
	msg.reply_text("Спасибо за использование Kaspersky Accounts!")
	
@app.on_message(filters.command("Нет", prefixes=".") & filters.me)
def Нет(_, msg):
	msg.edit("Хорошо, операция сканирования была отменена. Если понадоблюсь: .scan в личный чат с человеком и я тут как тут! \n\nВаш Kaspersky!")
	
@app.on_message(filters.command("ACCOUNTIRONE", prefixes=".") & filters.me)
def ACCOUNTIRONE(_, msg):
	msg.reply_text("Модуль RTPRF1 запущен")
	msg.delete()
	time.sleep(2)
	msg.reply_text("AndraX запускает модуль ACCOUNTIRONE..")
	time.sleep(1)
	msg.reply_text("Главный модуль ACCOUNTIRONE запущен\n\nHey!  The ACCOUNTIRONE module welcomes you!  \n\nDo you want to know information about a user in a chat?  (y/n)")
	
@app.on_message(filters.command("Y", prefixes=".") & filters.me)
def Y(_, msg):
	msg.edit("Your choice: Yes\n\nLooking for user information..")
	time.sleep(5)
	msg.edit("Search Results: \nTag: Deceiver \nComplaints: 4 \nRestrictions: None")
	
@app.on_message(filters.command("N", prefixes=".") & filters.me)
def N(_, msg):
	msg.edit("ACCOUNTIRONE module disabled")
	
@app.on_message(filters.command("Auto", prefixes=".") & filters.me)
def Auto(_, msg):
	msg.edit("Автоматическая покупка/продажа\n\nЗдравствуйте, сейчас я проведу вместо этого человека покупку/продажу.\n\nИсскуственый интелект построен на API: Яндекс Алиса")
	time.sleep(7)
	msg.reply_text("И так, считываю информацию с чата..")
	time.sleep(10)
	msg.reply_text("Теперь я в курсе дел!\\n\nСколько стоит?")
	time.sleep(7)
	msg.reply_text("Имеются ли другие владельцы?")
	time.sleep(7)
	msg.reply_text("Подтвергался ли продукт блокировкам?")
	time.sleep(10)
	msg.reply_text("Считываю информацию..")
	time.sleep(10)
	msg.reply_text("Хорошо, какой банк?\nПо нику или номеру?")
	msg.reply_text("Деньги автоматический переведуться вам на счет благодаря автоматическому переводу.")
	time.sleep(17)
	msg.reply_text("Проверяю действительность ника/номера в указаном банке..")
	time.sleep(10)
	msg.reply_text("Нашла! Но отправлять деньги я не буду! Для начала я проверю вашу социальную метку!(Обманщик, Спамер и.т.д.)\n\nИ так, мой хозяин отправьте сообщение (.scan). После результатов отправьте(.chek). Я проверю результаты и сделаю вывод.")
	
@app.on_message(filters.command("Chek", prefixes=".") & filters.me)
def Chek(_, msg):
	msg.edit("Я тут! Начинаю собирать результаты с сканирования..")
	time.sleep(10)
	msg.edit("Социальная метка обманщик! Я отменяю операцию покупки/продажи! Дальше разбирайтесь сами!\n\nВаша Яндекс Алиса")
	
@app.on_message(filters.command("Game", prefixes=".") & filters.me)
def Game(_, msg):
	msg.edit("Начать расследование?")
	
@app.on_message(filters.command("Даа", prefixes=".") & filters.me)
def Даа(_, msg):
	msg.edit("У вас хороший день?")
	time.sleep(7)
	msg.reply_text("У тебя много обязонастей?")
	time.sleep(7)
	msg.reply_text("Ты знаком с тем что тебя окружает?")
	time.sleep(7)
	msg.reply_text("Ты знаешь где мы находимся?")
	time.sleep(7)
	msg.reply_text("У вас была когда - нибудь паническая атака?")
	time.sleep(7)
	msg.reply_text("Ты задаешься вопросом о своем существовании?")
	time.sleep(7)
	msg.reply_text("Ты отвечаешь на эти вопросы исходя из своей собственной мысли?")
	time.sleep(7)
	msg.reply_text("Ты уверен?")
	time.sleep(7)
	msg.reply_text("Ты чувствуешь себя комфортно?")
	time.sleep(7)
	msg.reply_text("А если бы свет выключился, ты бы испугался?")
	time.sleep(7)
	msg.reply_text("Ты когда нибудь задовался вопросом когда ты умрешь?")
	time.sleep(7)
	msg.reply_text("Ты чистил себе стол?")
	time.sleep(7)
	msg.reply_text("У тебя есть интернет?")
	time.sleep(7)
	msg.reply_text("У тебя есть какие нибудь враги?")
	time.sleep(7)
	msg.reply_text("Если ты внезапно пропадешь, тебя бы кто нибудь искал?")
	time.sleep(7)
	msg.reply_text("Ты один?")
	time.sleep(7)
	msg.reply_text("Если  бы ты закричал, кто нибудь бы услышал?")
	time.sleep(7)
	msg.reply_text("Ты знаешь того кто стоит сзади тебя?")
	time.sleep(7)
	msg.reply_text("Ты один?")
	time.sleep(7)
	msg.reply_text("Расслабься, расслабься немного")
	time.sleep(14)
	msg.reply_text("Ты расслаблен?")
	time.sleep(7)
	msg.reply_text("Все твои ощущения реальны, или запрограммированы как машина?")
	time.sleep(7)
	msg.reply_text("Есть какой - то смысл в жизни?")
	time.sleep(7)
	msg.reply_text("Ты знаешь кто ты?")
	time.sleep(7)
	msg.reply_text("Ты знаешь что сейчас происходит?")
	time.sleep(7)
	msg.reply_text("Если тебе сказать правду о твоем существовании, ты бы отказывался воспринимать это, в надежде получить хороший ответ?")
	time.sleep(7)
	msg.reply_text("Когда я спрашиваю тебя, это реально ты отвечаешь?")
	time.sleep(7)
	msg.reply_text("Если бы я сказал тебе, что ты не разумен. Ты бы поверил в это?")
	time.sleep(7)
	msg.reply_text("Ты хочешь знать правду?")
	time.sleep(7)
	msg.reply_text("Посмотри в свое окно..")
	time.sleep(14)
	msg.reply_text("Эта комната, это окно, этот компьютер..")
	time.sleep(10)
	msg.reply_text("А теперь пойми, что я просто с тобой разговаривал. А ты ощущал чье - то присутствие. Верно? Ты поддался манипуляции тобой.")
	
@app.on_message(filters.command("Спасибо", prefixes=".") & filters.me)
def Спасибо(_, msg):
	msg.edit("Спа")
	time.sleep(0.20)
	msg.edit("Спаси")
	time.sleep(0.20)
	msg.edit("Спасибо")
	time.sleep(0.20)
	msg.edit(".❤️")
	time.sleep(0.20)
	msg.edit(".🧡")
	time.sleep(0.20)
	msg.edit(".💛")
	time.sleep(0.20)
	msg.edit(".💚")
	time.sleep(0.20)
	msg.edit(".💙")
	time.sleep(0.20)
	msg.edit(".💜")
	time.sleep(0.20)
	msg.edit(".🖤")
	time.sleep(0.20)
	msg.edit(".🤎")
	time.sleep(0.20)
	msg.edit(".🤍")
	time.sleep(0.20)
	msg.edit("Спасибо")
	time.sleep(0.20)
	msg.edit("Спасибо❤️")
	time.sleep(0.20)
	msg.edit("Спасибо")
	
@app.on_message(filters.command("Здравствуйте", prefixes=".") & filters.me)
def Здравствуйте(_, msg):
	time.sleep(0.20)
	msg.edit(".👋")
	time.sleep(0.20)
	msg.edit("Здра")
	time.sleep(0.20)
	msg.edit("Здравст")
	time.sleep(0.20)
	msg.edit("Здравствуй")
	time.sleep(0.20)
	msg.edit("Здравствуйте")
	time.sleep(0.20)
	msg.edit("Здравствуйте👋")
	time.sleep(0.20)
	msg.edit("Здравствуйте")
	
@app.on_message(filters.command("Досвидания", prefixes=".") & filters.me)
def Досвидания(_, msg):
	msg.edit("До")
	time.sleep(0.20)
	msg.edit("До сви")
	time.sleep(0.20)
	msg.edit("До свида")
	time.sleep(0.20)
	msg.edit("До свидани")
	time.sleep(0.20)
	msg.edit("До свидания")
	time.sleep(0.20)
	msg.edit(".👋")
	time.sleep(0.20)
	msg.edit("До свидания👋")
	time.sleep(0.20)
	msg.edit("До свидания")
	
@app.on_message(filters.command("Type2", prefixes=".") & filters.me)
def Type2(_, msg):
    orig_text = msg.text.split(".type2 ", maxsplit=1)[1]
    text = orig_text
    tbp = "" # to be printed
    typing_symbol = "꧁꧂"
 
    while(tbp != orig_text):
        try:
            msg.edit(tbp + typing_symbol)
            sleep(0.05) # 50 ms
 
            tbp = tbp + text[0]
            text = text[1:]
 
            msg.edit(tbp)
            sleep(0.05)
 
        except FloodWait as e:
            sleep(e.x)
	
@app.on_message(filters.command("Type3", prefixes=".") & filters.me)
def Type3(_, msg):
    orig_text = msg.text.split(".type3 ", maxsplit=1)[1]
    text = orig_text
    tbp = "" # to be printed
    typing_symbol = "☞"
 
    while(tbp != orig_text):
        try:
            msg.edit(tbp + typing_symbol)
            sleep(0.05) # 50 ms
 
            tbp = tbp + text[0]
            text = text[1:]
 
            msg.edit(tbp)
            sleep(0.05)
 
        except FloodWait as e:
            sleep(e.x)
            
@app.on_message(filters.command("Type4", prefixes=".") & filters.me)
def Type4(_, msg):
    orig_text = msg.text.split(".type4 ", maxsplit=1)[1]
    text = orig_text
    tbp = "" # to be printed
    typing_symbol = "🔄"
 
    while(tbp != orig_text):
        try:
            msg.edit(tbp + typing_symbol)
            sleep(0.05) # 50 ms
 
            tbp = tbp + text[0]
            text = text[1:]
 
            msg.edit(tbp)
            sleep(0.05)
 
        except FloodWait as e:
            sleep(e.x)
            
@app.on_message(filters.command("Type5", prefixes=".") & filters.me)
def Type5(_, msg):
    orig_text = msg.text.split(".type5 ", maxsplit=1)[1]
    text = orig_text
    tbp = "" # to be printed
    typing_symbol = "🔜"
 
    while(tbp != orig_text):
        try:
            msg.edit(tbp + typing_symbol)
            sleep(0.05) # 50 ms
 
            tbp = tbp + text[0]
            text = text[1:]
 
            msg.edit(tbp)
            sleep(0.05)
 
        except FloodWait as e:
            sleep(e.x)
	
	
@app.on_message(filters.command("thanos", prefixes=".") & filters.me)
def thanos(_, msg):
    chat = msg.text.split(".thanos ", maxsplit=1)[1]
 
    members = [
        x
        for x in app.iter_chat_members(chat)
        if x.status not in ("administrator", "creator")
    ]
 
    random.shuffle(members)
 
    app.send_message(chat, "Щелчок Таноса ... *щёлк*")
 
    for i in range(len(members) // 2):
        try:
            app.restrict_chat_member(
                chat_id=chat,
                user_id=members[i].user.id,
                permissions=ChatPermissions(),
                until_date=int(time.time() + 86400),
            )
            app.send_message(chat, "Исчез " + members[i].user.first_name)
        except FloodWait as e:
            print("> waiting", e.x, "seconds.")
            time.sleep(e.x)
 
    app.send_message(chat, "Но какой ценой?")
 
app.run()
