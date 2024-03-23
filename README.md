import discord
from discord.ext import commands
import random

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix="!", intents=intents)

@bot.event
async def on_ready():
    print(f'Merhaba {bot.user} olarak giriş yaptım.Umarım gününüz iyi geçiyordur!')

ülke1 = "Türkiye"
ülke2 = "Almanya"
ülke3 = "Japonya"
ülke4 = "Çin"
ülke5 = "Avusturya"
ülke6 = "Hollanda"
ülke7 = "Fransa"
ülke8 = "Rusya"
ülke9 = "Hindistan"

ülke = {"Türkiye":"Ankara","Almanya":"Berlin","Japonya":"Tokyo","Çin":"Pekin","Avusturya":"Viyana","Hollanda":"Amsterdam","Fransa":"Paris","Rusya":"Moskova","Hindistan":"Yeni Delhi"}

ülkeler = [ülke1,ülke2,ülke3,ülke4,ülke5,ülke6,ülke7]

@bot.command()
async def ülkelerr(ctx):
    a,b = random.choice(ülke.items())
    await ctx.send(f'{a} nın/nin başkenti neresidir?')
    tahmin_mesaji = await bot.wait_for("message", check=lambda m: m.author == ctx.author)
    kullanici_tahmini = tahmin_mesaji.content



bot.run("")
