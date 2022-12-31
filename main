import turtle

score1 = 0
score2 = 0

wn = turtle.Screen()
wn.title("Ultra Turbo Extreme Pong!")
wn.bgcolor("green")
wn.setup(width=840, height=640)
wn.tracer(0)

pen1 = turtle.Turtle()
pen1.color("cyan2")
pen1.penup()
pen1.hideturtle()
pen1.goto(280, 280)
pen1.write("Score: {}".format(score1),font=("Normal", 18, "normal"))

pen2 = turtle.Turtle()
pen2.color("gold1")
pen2.penup()
pen2.hideturtle()
pen2.goto(-360, 280)
pen2.write("Score: {}".format(score2),font=("Normal", 18, "normal"))



# paddle a
paddle_a = turtle.Turtle()
paddle_a.speed(0)
paddle_a.shape("square")
paddle_a.color("blue")
paddle_a.penup()
paddle_a.goto(-350, 0)
paddle_a.shapesize(stretch_wid=5, stretch_len=1)


# paddle b

paddle_b = turtle.Turtle()
paddle_b.speed(0)
paddle_b.shape("square")
paddle_b.color("blue")
paddle_b.penup()
paddle_b.goto(350, 0)
paddle_b.shapesize(stretch_wid=5, stretch_len=1)

ball = turtle.Turtle()
ball.speed(0)
ball.shape("circle")
ball.color("red")
ball.penup()
ball.goto(0, 0)
ball.dx = 0.8
ball.dy = 0.8



def paddle_a_up():
    y = paddle_a.ycor()
    y += 40
    paddle_a.sety(y)


def new_game():
    global score1
    global score2
    score1 = 0
    score2 = 0
    pen1.clear()
    pen2.clear()
    pen1.write("Score: {}".format(score1), font=("Normal", 18, "normal"))
    pen2.write("Score: {}".format(score2), font=("Normal", 18, "normal"))



def paddle_a_down():
    y = paddle_a.ycor()
    y -= 40
    paddle_a.sety(y)

def paddle_b_up():
    y = paddle_b.ycor()
    y += 40
    paddle_b.sety(y)

def paddle_b_down():
    y = paddle_b.ycor()
    y -= 40
    paddle_b.sety(y)

wn.listen()
wn.onkeypress(paddle_b_up, "Up")
wn.onkeypress(paddle_b_down, "Down")
wn.onkeypress(new_game, "o")



while True:
    if paddle_a.ycor() < ball.ycor():
        paddle_a_up()

    if paddle_a.ycor() > ball.ycor():
        paddle_a_down()

    if paddle_a.ycor() > 264:
        paddle_a.sety(264)
    if paddle_a.ycor() < -264:
        paddle_a.sety(-264)
    if paddle_b.ycor() > 264:
        paddle_b.sety(264)
    if paddle_b.ycor() < -264:
        paddle_b.sety(-264)

    wn.update()
    ball.setx(ball.xcor() + ball.dx)
    ball.sety(ball.ycor() + ball.dy)

    if ball.ycor() > 288:
        ball.sety(288)
        ball.dy *= -1

    if ball.ycor() < -288:
        ball.sety(-288)
        ball.dy *= -1

    if ball.xcor() > 380:
        ball.goto(0, 0)
        ball.dx *= -1
        score2 += 1
        pen2.clear()
        pen2.write("Score: {}".format(score2), font=("Normal", 18, "normal"))


    if ball.xcor() < -380:
        ball.goto(0, 0)
        ball.dx *= -1
        score1 += 1
        pen1.clear()
        pen1.write("Score: {}".format(score1), font=("Normal", 18, "normal"))

    if (ball.xcor() > 340 and ball.xcor() < 350) and (ball.ycor() < paddle_b.ycor() + 50 and ball.ycor() > paddle_b.ycor() - 50):
        ball.setx(340)
        ball.dx *= -1

    if ball.xcor() < -340 and (ball.ycor() < paddle_a.ycor() + 50 and ball.ycor() > paddle_a.ycor() - 50):
        ball.setx(-340)
        ball.dx *= -1

