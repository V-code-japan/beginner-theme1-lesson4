```template
player.onChat("run", function () {
    agent.teleport(world(-7, -21, 0), SOUTH)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 7; index++) {
                agent.setItem(PLANKS_ACACIA, 1, 1)
                agent.place(FORWARD)
                agent.move(LEFT, 1)
            }
            agent.move(UP, 1)
            agent.move(RIGHT, 7)
        }
        agent.move(DOWN, 4)
        agent.move(LEFT, 8)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    }
})
```

# 学んだプログラムを使ってみよう

## プログラムを自由にくみかえよう
<p>今日、学んだプログラムを見てみましょう</p>
<p>見終わったら`||完了||`をクリックしてすべての使って自由にプログラミングをしてみましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_finished.gif"></p>