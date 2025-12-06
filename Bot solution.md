import discord
import random
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='-', intents=intents)

@bot.event
async def on_ready():
    print(f'We have logged in as {bot.user}')

@bot.command()
async def hello(ctx):
    await ctx.send(f'Hi! I am a bot {bot.user}!')
    await ctx.send(f'Ketik -Solusi_Laut untuk memberi informasi cara menjaga kebersihan lautan dan ketik -Solusi_Darat untuk memberi informasi cara menjaga kebersihan daratan')

@bot.command()
async def Solusi_Laut(ctx):
    await ctx.send(f'Hindari plastik sekali pakai: Gunakan botol air yang dapat digunakan kembali dan tas kain untuk mengurangi sampah plastik yang berakhir di laut. Plastik dapat merusak habitat laut dan membunuh banyak hewan laut setiap tahunnya')

@bot.command()
async def Solusi_Darat(ctx):
    await ctx.send(f'Memilah sampah, melakukan daur ulang, dan mengurangi penggunaan bahan-bahan yang sulit terurai dapat membantu menjaga kebersihan dan kesehatan ekosistem darat')

bot.run("Token bot only!")
