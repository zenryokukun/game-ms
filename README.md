このリポジトリは```create-react-app```を利用しています。

[vite版](https://github.com/zenryokukun/minesweeper-vite)を公開しましたので、拘りがなければこちらの利用をお願いいたします。

---

# Minesweeper極(KI-WA-MI)

Websiteで公開しているReact流[マインスイーパー改](https://www.zenryoku-kun.com/production/minesweeperkai)のゲーム部分を
ローカルで実行できるようにしたもの。webページにあるナビゲーションバーやフッターの機能は落としています。  

## インストール方法

1. このリポジトリをclone。

```
git clone https://github.com/zenryokukun/game-ms.git
```

2. game-msフォルダにcd

```
cd game-ms
```

3. dependenciesをインストール

```
npm i
```
yarnは使ったことないですごめんなさい。  
インストールに数分かかります。321MBあるのでご留意ください。Reactは重い。
create-react-appでインストールされるパッケージ以外、追加のものはありません。

## 実行

```
npm start
```

## ゲームのルール

- マスを**左クリック**すると開きます。
- 地雷が埋まっているマスをクリックすると負けです。
- 数字のマスは、隣接するマスに埋まっている地雷の数を表しています。
- 数字をヒントに、地雷があると思われるマスに**右クリック**で旗を立てます。
- 全ての地雷のマスに旗を立て、それ以外のマスを全て開くと勝ちです。
- 左上の数字は、残地雷数です。旗を立てると減りますが、間違えていても減ります。
- 右上の数字は経過秒数です。
- 同じ難易度で再プレイする場合は😊マークを**左クリック**。
- 数字のマスを**ダブルクリック**すると、隣接するマスを全て開きます。時短にどうぞ。

## フォルダについて

ホームページの１ページだったものを抜き出しているので、階層が少し深くなってるフォルダもあります。 
後、cssモジュールがComponentフォルダに入っていたり、stylesフォルダに入っていたり統一感が無い箇所あります。ご容赦ください。

- **/src**  
  直下のファイル。  

  - **index.tsx**  
    Reactのエントリポイントです。  

  - **App.tsx**  
　　メインのComponentです。  

  - **index.css**  
    全てのComponentに適用されるcssです。create-react-appで生成された状態そのままです。  
    
  - **declaration.d.ts**  
    何故かcssモジュールのインポートでエラーになるため、typescriptが"*.module.css"をモジュールとして認識するように追加しました。  
    create-react-app --template typescriptでインストールすれば、cssモジュールが使える状態になるはずだと思うのですが。。。原因分かる人いたら教えて下さい。  

- **/src/styles**  
  cssモジュールが入っています。  

- **/src/component/minesweeperkai**  
  App.tsxで利用しているComponentを配置。Component内で利用しているcssモジュールも１つだけ入っています。  

  - **Description.tsx**  
    「ルール説明」リンクを押したときに表示されるモーダル  
    
  - **GameBoard.tsx**  
    ゲーム部分。地雷数、ニコニコマーク、時間、ゲーム版など  

  - **LevelSelect**  
    画面上部のレベル選択エリア。EASY,MEDIUM,HARD,極のとこ  

  - **Result**  
    画面下部のゲーム状態を文字で表示している部分。PLAYING...とか。  

  - **Tile**  
    ゲーム版の各マスを部品化したもの  

- **/src/lib/mskai**  
  React Component以外のモジュールが入っています。ゲームのロジック部分です。  
