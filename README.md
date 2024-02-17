from telegram.ext import Updater, CommandHandler
import random

def start(update, context):
    update.message.reply_text("Привіт! Як настрій?")

def name(update, context):
    bot_info ="Цей бот належить Джамалу і його душам йоу)"

    update.message.reply_text(bot_info)

def interesting(update, context):
    interesting_messages = [
        "Що ви думаєте про цю не хорошу людину?",
        "Чи знали ви, що вона бізнесмен?",
        "Чому він вас образив?"
    ]
    message = random.choice(interesting_messages)
    update.message.reply_text(message)

def main():
    updater = Updater("6532227688:AAF1xoJ9Y6mv7nnOdAISJpxpevVCBt_uzgc", use_context=True)

    dp = updater.dispatcher

    dp.add_handler(CommandHandler("start", start))

    dp.add_handler(CommandHandler("ім'я", name))

    dp.add_handler(CommandHandler("interesting", interesting))

    updater.start_polling()

    updater.idle()
