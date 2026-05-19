# 2026-python-122026-python-Chinese-Zodiac
# from turtle import *
import math
def initializeTurtle():
    setup(1200, 900)
    bgcolor("white")
    speed(0)
    pensize(3)
    hideturtle()


def drawFace(x, y):
    penup()
    goto(x, y - 60)
    pendown()
    circle(60)

def drawEyes(x, y):
    for dx in [-20, 20]:
        penup()
        goto(x + dx, y)
        dot(10)

def drawMouth(x, y):
    penup()
    goto(x - 10, y - 30)
    pendown()
    goto(x, y - 38)
    goto(x + 10, y - 30)

def drawLabel(x, y, text):
    penup()
    goto(x, y)
    write(text, align="center", font=("Arial", 14, "bold"))
    
def drawAnimal(x, y, animal):
    if animal != "蛇":
        drawFace(x, y)
        drawEyes(x, y)
        drawMouth(x, y)
    # 鼠
    if animal == "鼠":
        for dx in [-45, 45]:
            penup()
            goto(x + dx, y + 40)
            pendown()
            circle(18)
    # 牛
    elif animal == "牛":
        penup()
        goto(x - 45, y + 45)
        pendown()
        goto(x - 70, y + 70)
        goto(x - 50, y + 30)
        penup()
        goto(x + 45, y + 45)
        pendown()
        goto(x + 70, y + 70)
        goto(x + 50, y + 30)
    # 虎
    elif animal == "虎":
        penup()
        goto(x, y + 50)
        pendown()
        goto(x, y + 20)
        penup()
        goto(x - 25, y + 35)
        pendown()
        goto(x + 25, y + 35)
    # 兔
    elif animal == "兔":
        for dx in [-20, 20]:
            penup()
            goto(x + dx, y + 60)
            pendown()
            setheading(90)
            circle(10, 180)
    # 龍
    elif animal == "龍":
        penup()
        goto(x - 40, y + 40)
        pendown()
        goto(x - 20, y + 65)
        goto(x, y + 40)
        goto(x + 20, y + 65)
        goto(x + 40, y + 40)
    # 蛇
    elif animal == "蛇":
        penup()
        goto(x - 60, y)
        pendown()
        for i in range(100):
            forward(1)
            left(math.sin(i / 10) * 3)
    # 馬
    elif animal == "馬":
        penup()
        goto(x - 20, y + 55)
        pendown()
        goto(x, y + 80)
        goto(x + 20, y + 55)
    # 羊
    elif animal == "羊":
        penup()
        goto(x - 25, y + 40)
        pendown()
        circle(15, 200)
        penup()
        goto(x + 25, y + 40)
        pendown()
        circle(-15, 200)
    # 猴
    elif animal == "猴":
        for dx in [-55, 55]:
            penup()
            goto(x + dx, y)
            pendown()
            circle(18)
    # 雞
    elif animal == "雞":
        penup()
        goto(x - 10, y + 60)
        pendown()
        goto(x, y + 85)
        goto(x + 10, y + 60)
    # 狗
    elif animal == "狗":
        penup()
        goto(x - 45, y + 35)
        pendown()
        goto(x - 60, y - 10)
        penup()
        goto(x + 45, y + 35)
        pendown()
        goto(x + 60, y - 10)
    # 豬
    elif animal == "豬":
        penup()
        goto(x - 20, y - 20)
        pendown()
        circle(20)
    drawLabel(x, y - 100, animal)

# 主程式
initializeTurtle()

animals = [
    "鼠", "牛", "虎", "兔",
    "龍", "蛇", "馬", "羊",
    "猴", "雞", "狗", "豬"
]

startX = -400
startY = 250

index = 0

for row in range(3):
    for col in range(4):
        x = startX + col * 250
        y = startY - row * 250
        drawAnimal(x, y, animals[index])
        index += 1

done()
