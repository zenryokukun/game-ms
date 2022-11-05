# Minesweeper極(KI-WA-MI)

Websiteで後悔しているReact流[マインスイーパー改](https://www.zenryoku-kun.com/production/minesweeperkai)のゲーム部分を
ローカルで実行できるようにしたもの。ページのナビゲーションバーやフッターは表示されません。

## install

1. このリポジトリをclone。

```
git clone https://github.com/zenryokukun/game-ms.git
```

2. dependenciesをインストール

```
npm i
```
yarnは使ったことないですごめんなさい。  
インストールに時間に数分時間がかかります。321MBあるのでご留意ください。Reactは重い。
create-react-appでインストールされるパッケージ以外、追加のものはありません。

## 実行

```
npm start
```

## フォルダについて

ホームページの１ページだったものを抜き出しているので、階層が少し深くなっています。  
後、cssモジュールがComponentフォルダに入っていたり、stylesフォルダに入っていたり統一感が無い箇所も少しありますがご容赦ください。

- **/src**  
  直下のファイル。
  - **index.tsx**  
    Reactのエントリポイントです。  
  - **App.tsx**  
　　メインのComponentです。
  - **index.css**  
    全てのComponentに適用されるcssです。create-react-appで生成された状態そのままです。
  - **declaration.d.ts**  
    何故かcssモジュールのインポートでエラーになるため、typescriptが"*.module.css"モジュールとして認識するように追加しました。  
    create-react-app --template typescriptでインストールすれば、cssモジュールを使える状態になっているはずだと思うのですが。。。原因分かる人教えて下さい。  

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