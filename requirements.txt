python-telegram-bot==20.8
bot.py
from telegram import Update, ReplyKeyboardMarkup
from telegram.ext import Application, CommandHandler, ContextTypes

TOKEN = "8915841113:AAF8U69c3xumo_YnBnYBA3KXWMIO8_E901k"

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    keyboard = [
        ["🛍 محصولات"],
        ["🛒 سبد خرید"],
        ["📞 پشتیبانی"],
        ["ℹ️ درباره ما"]
    ]

    await update.message.reply_text(
        "به فروشگاه خوش آمدید 🌹",
        reply_markup=ReplyKeyboardMarkup(keyboard, resize_keyboard=True)
    )

app = Application.builder().token(TOKEN).build()

app.add_handler(CommandHandler("start", start))

app.run_polling()
