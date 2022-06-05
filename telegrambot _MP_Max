import telebot
token = '5460784619:AAHt8Sx9KuNbDb6kQulDPPTLnfFcij2m2iA'
bot = telebot.TeleBot(token)

@bot.message_handler(commands=['start'])
def start_message(message):
bot.send_message(message.chat.id, "Здравствуйте, я ваш медицинский помощник!")
markup = telebot.types.InlineKeyboardMarkup()
markup.add(telebot.types.InlineKeyboardButton(text='Нижний Новгород', callback_data='nn'))
bot.send_message(message.chat.id, text="Из какого вы города?", reply_markup=markup)

@bot.callback_query_handler(func=lambda call: True)
def query_handler(call):
bot.answer_callback_query(callback_query_id=call.id)
answer = ''
if call.data == 'nn':
answer = "Хорошо, Нижний Новгород!"
bot.send_message(call.message.chat.id, answer)
markup = telebot.types.InlineKeyboardMarkup()
markup.add(telebot.types.InlineKeyboardButton(text='Автозоводской', callback_data='az'))
markup.add(telebot.types.InlineKeyboardButton(text='Канавенский', callback_data='kv'))
markup.add(telebot.types.InlineKeyboardButton(text='Ленинский', callback_data='ln'))
markup.add(telebot.types.InlineKeyboardButton(text='Московский', callback_data='ms'))
markup.add(telebot.types.InlineKeyboardButton(text='Нижегородский', callback_data='ng'))
markup.add(telebot.types.InlineKeyboardButton(text='Приокский', callback_data='po'))
markup.add(telebot.types.InlineKeyboardButton(text='Советский', callback_data='sv'))
markup.add(telebot.types.InlineKeyboardButton(text='Сормовский', callback_data='sm'))
bot.send_message(call.message.chat.id, text="Из какого вы района?", reply_markup=markup)
bot.infinity_polling()
