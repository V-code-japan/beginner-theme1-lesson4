# LESSON1 畑を作ってみよう
```block
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

```template
player.onChat("run", function () {
	
})
```

## エージェントを動かすプログラムを作ろう @unplugged
<p>エージェントを動かして畑や家のかべを作ろう！</p>
<img style="display: block; margin: auto;" height="50%" width="90%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_complete1.gif">

## 目標（もくひょう）
<p>まずはこれから作るものの形をかくにんしよう！</p>
<p>・チャットで「run」と入力したら、エージェントが畑をたがやしてニンジンを植えるようにプログラミングをする</p>
<p>・エージェントは、はじめにワールド19 -21 -1、東(xのプラス方向)にテレポートする</p>
<p>・たがやす➡ニンジンを植える➡左に１ブロック動く を５回くり返す</p>
<p>・畑は横５ブロックの大きさにする</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_cultivate1.gif"></p>

## エージェントに１ブロック分の畑をたがやして、ニンジンを植えさせよう
<p>まずはエージェントに１ブロック分の畑をたがやして、ニンジンを植えてもらいましょう</p>
<p>エージェントの動きは次の１～４のようにします</p>
<p>１.エージェントにニンジンをわたす</p>
<p>２.前をたがやす</p>
<p>３.ニンジンを植える</p>
<p>４.エージェントを左に１ブロック動かす</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_movement_set1.gif"></p>

## 1.エージェントにアイテムをわたしましょう

<p>`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに…を１個、自分のスロット１番に設定（せってい）させる||`と書いてあるブロックを`||player.チャットコマンド～||`の中にドラックしてみましょう</p>
<p>`||blocks.土ブロック||`をクリックして`||blocks.ニンジン||`にしましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_set_block_to_agent1.gif"></p>
```block
player.onChat("run", function () {
    agent.setItem(CARROTS, 1, 1)
})
```

## 2.エージェントに畑をたがやさせましょう

<p>`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前を耕（たがや）させる||`と書いてあるブロックを`||agent.エージェントに…設定させる||`の下にドラックしてみましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_till1.gif"></P>
```block
player.onChat("run", function () {
    agent.setItem(CARROTS, 1, 1)
    agent.till(FORWARD)
})
```

## 3.エージェントにニンジンを植えてもらいましょう

<p>`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントに前へ置（お）かせる||`と書いてあるブロックを`||agent.エージェントに前を耕させる||`の下にドラックしてみましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_place_block1.gif"></p>
```block
player.onChat("run", function () {
    agent.setItem(CARROTS, 1, 1)
    agent.till(FORWARD)
    agent.place(FORWARD)
})
```

## 4.エージェントを動かしましょう

<p>`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを前に１ブロック移動（いどう）させる||`と書いてあるブロックを`||agent.エージェントに前へ置かせる||`の下にドラックしてみましょう</p>
<p>`||agent.エージェントを前に１ブロック移動させる||`の`||agent.前▼||`をクリックして`||agent.左▼||`に変更しましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_move_left1.gif"></p>
```block
player.onChat("run", function () {
    agent.setItem(CARROTS, 1, 1)
    agent.till(FORWARD)
    agent.place(FORWARD)
    agent.move(LEFT, 1)
})
```

## エージェントに同じ動きをくりかえさせましょう
<p>これで１ブロック分の畑をたがやして、ニンジンを植えてもらうプログラムができました</p>
<p>つぎはこの動きを５回くりかえさせましょう</P>
<p><img style="display: block; margin: 0 auto; width:50%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_movement_set1.gif"></p>
<p><img style="display: block; margin: 0 auto; width: 25%;" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_down_arrow1.png"></p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_cultivate1.gif"></p>


## 5.くりかえしを入れてみましょう

<p>`||loops.ループ||`ボタンをクリックしてその中の`||loops.くりかえし４回||`と書いてあるブロックで今までに作ったプログラムをはさみましょう</p>
<p>そして`||functions.４回||`を`||functions.５回||`にしましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_repeat1.gif"></p>
```block
player.onChat("run", function () {
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.till(FORWARD)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## エージェントを畑をたがやしはじめる場所にテレポート
<p>さいごにエージェントを畑をたがやしはじめる場所にテレポートさせましょう</p>

## 6.エージェントをテレポートさせよう

<p>`||agent.エージェント||`ボタンをクリックしてその中の`||agent.エージェントを…へ西(xのマイナス方向)向きにテレポートさせる||`と書いてあるブロックを`||loops.くりかえし５回||`の上にドラックしてみましょう</p>
<p>`||agent.西(xのマイナス方向)▼||`をクリックして`||agent.東(xのプラス方向)▼||`にしましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_teleport1.gif"></p>
```block
player.onChat("run", function () {
    agent.teleport(pos(0, 0, 0), EAST)
    for (let index = 0; index < 5; index++) {
        agent.setItem(CARROTS, 1, 1)
        agent.till(FORWARD)
        agent.place(FORWARD)
        agent.move(LEFT, 1)
    }
})
```

## 7.座標を入れてみましょう

<p>`||positions.ポジション||`ボタンをクリックしてその中の`||positions.ワールド0 0 0||`を`||agent.~0~0~0||`の上までドラッグします</p>
<p>`||positions.ワールド0 0 0||`を`||positions.ワールド19 -21 -1||`にしましょう</p>
<p><img style="width:100%" src="https://vcode-esia.com/images_for_world_data/Basic/Theme1/Lesson4/L4_set_world_pos1.gif"></p>
```block
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

## 8.『実行』ボタンをクリックしましょう
<p>画面右下にある緑の『▶』ボタンをクリックして作ったプログラムを実行し、チャットコマンドで`||player.run||`と入力してみましょう</p>