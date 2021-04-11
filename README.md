# import telebot
#token

bot = telebot.TeleBot("token")

@bot.message_handler(commands=['start', 'help'])
def send_welcome(message):
	bot.reply_to(message, "Howdy, how are you doing?")

@bot.message_handler(func=lambda m: True)
def echo_all(message):
    if message.text =='привет':
        bot.reply_to(message, 'Привет, создатель!')
    elif message.text == 'ку':
        bot.reply_to(message, 'Приветули!')
	#bot.reply_to(message, message.text)

bot.polling()

