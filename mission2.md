# LESSON2 かべを作ってみよう
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 5; index++) {
        for (let index = 0; index < 6; index++) {
            agent.setItem(PLANKS_BIRCH, 1, 1)
            agent.place(FORWARD)
            agent.move(LEFT, 1)
        }
        agent.move(UP, 1)
        agent.move(RIGHT, 6)
    }
})

```

```template
player.onChat("run", function () {
    agent.teleport(world(19, -21, -1), EAST)
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.till(FORWARD)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```



## 目標（もくひょう）
<p>先ほど作ったプログラムを改造（かいぞう）して、かべを作るようにしよう！</p>
<p>・チャットで「run」と入力したら、エージェントができていない部分のかべを作るようにプログラミングをする</p>
<p>・エージェントは、はじめにワールド11 -21 20、南(zのプラス方向)にテレポートする</p>
<p>・ブロックをおく➡左に１ブロック動く を６回くり返して、次にブロックをおく場所にエージェントを動かす</p>
<p>・かべはシラカバの板材（いたざい）でたて５ブロック、横６ブロックの大きさにする</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_complete2.gif"></p>

## 畑を直したプログラムを使って、かべを作るプログラムを作ろう
<p>まずは畑を直したプログラムを使って、かべを１列分作らせましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_make_row2.gif"></p>

## 1.いらないプログラムを消そう

<p>`||agent.エージェントに前を耕（たがや）させる||`と書いてあるブロックにカーソルを合わせて右クリックをしましょう</p>
<p><img style="width:90%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_delete_block.png">をクリックするといらないブロックを消すことができます</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_delete_till2.gif"></p>
```block
player.onChat("run", function () {
    agent.teleport(world(19, -21, -1), EAST)
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## 2.座標を入力してみましょう

<p>`||positions.ワールド19 -21 -1||`を`||positions.ワールド11 -21 20||`と入力しましょう</p>
<p>そして`||agent.東(xのプラス方向)||`を`||agent.南(zのプラス方向)||`にしましょう</p>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## 3.くりかえしの数を入力しましょう

<p>今回はブロックを６個おくのでくりかえしの数も６回にしましょう</p>
<p>`||functions.くりかえし５回||`を`||functions.くりかえし６回||`にしましょう</p>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 6; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## 4.ブロックをえらびましょう

<p>ブロックにシラカバの板材（いたざい）をえらびましょう</p>
<p>`||blocks.ニンジン||`をクリックして`||blocks.シラカバの板材||`にしましょう</p>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 6; index++) {
        agent.setItem(PLANKS_BIRCH, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## エージェントを次にブロックをおき始める場所へ動かしましょう
<p>１列分のブロックをおくプログラムができました！</p>
<p>次にブロックをおきはじめる場所にエージェントを動かしてみましょう</p>
<p>次のページにいく前に、下の赤いわくにエージェントを動かすには上に何ブロック、右に何ブロック動かせばいいか考えてみましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_to_next_pos.png"></p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_move_to_next_pos2.gif"></p>

## 5.エージェントを上に動かしましょう

<p>エージェントを上に１ブロック、右に６ブロック動かせばいいことがわかりましたか？さっそくそのプログラムを作りましょう</p>
<p>`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||loops.くりかえし６回||`の下にドラックしてみましょう</p>
<p>`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.上▼||`に変更しましょう</p>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 6; index++) {
        agent.setItem(PLANKS_BIRCH, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
    agent.move(UP, 1)
})
```

## 6.エージェントを右に動かしましょう

<p>`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動させる||`と書いてあるブロックを`||agent.エージェントを上に１ブロック移動させる||`の下にドラックしてみましょう</p>
<p>`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.右▼||`に変更しましょう</p>
<p>`||functions.１ブロック||`を`||functions.６ブロック||`にしましょう</p>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 6; index++) {
        agent.setItem(PLANKS_BIRCH, 1, 1)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
    agent.move(UP, 1)
    agent.move(RIGHT, 6)
})
```

## プログラムを高さの数だけくりかえしましょう
<p>これで１列分のブロックをおいて、次のブロックをおく場所に動くプログラムができました！</p>
<p>さいごにこのプログラムをかべの高さの数だけくりかえすようにしましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_movement_set2.gif"></p>

## 7.くりかえしを入れてみましょう

<p>`||loops.ループ||`ボタンをクリックしてその中の`||loops.くりかえし４回||`と書いてあるブロックで`||agent.エージェントを…テレポートさせる||`より下のプログラムをはさみましょう</p>
<p>そして`||functions.４回||`を`||functions.５回||`にしましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_repeat2.gif"></p>
```block
player.onChat("run", function () {
    agent.teleport(world(11, -21, 20), SOUTH)
    for (let index = 0; index < 5; index++) {
        for (let index = 0; index < 6; index++) {
            agent.setItem(PLANKS_BIRCH, 1, 1)
            agent.place(FORWARD)
            agent.move(LEFT, 1)
        }
        agent.move(UP, 1)
        agent.move(RIGHT, 6)
    }
})
```

## 8.『実行』ボタンをクリックしましょう
画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう