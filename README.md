# TISCON - Insurance Order
## 背景

保険代理店のお客様が、書類で行っていた保険の加入申込みをオンライン化することになりました。
保険の申し込みシステムなど、いくつかのシステムを開発する必要があり、協業するSI企業を選定しているとのこと。

> 当社はこれまで相談窓口での提案を中心として、保険の売り上げを伸ばしてきました。<br>
> しかし現在、保険の申込みはダイレクト型といわれるインターネット申込が当たり前になってきています。<br>
> 自社のサイト上に保険の申込みができる環境を構築することが当社の急務です。

> 弊社内で、見よう見真似で申込サイトを作ってみたのですが、どうも出来栄えが悪く社内でも不評です。。<br>
> そこで、信頼できるSI企業にプロの視点で指摘・改修の提案をお願いしたいと思っています。<br>
> ぜひ、保険の新規加入者が継続的に増えていくようなコンバージョン率の高いシステムの提案をよろしくお願いします！

私達は技術コンペに参加することにしました。

## ミッション

**技術コンペに参加して、案件を獲得する。**

お客様は各社の技術力と提案内容を比較して、開発を委託する企業を選定します。<br>
既存サイトの問題点をプロの視点で改善し、お客様の信頼を勝ち取ってください。

### 改善事項

以下は、お客様の社内で挙がった意見です。改善の参考にしてください。

 - 入力しにくい
 - すべての入力が終わるまでに時間がかかる
 - 処理が遅い

### 成果物

プレゼン資料
 - お客様にとって使いやすいアプリケーションについて、改善提案のための資料を用意してください.

デモ用アプリケーション
 - チームで１つのシステムを改修してください。
 - 成果物は代表者のGithubリポジトリに統合（マージ）してください。

---

# 環境構築

本手順はIntelliJでの操作を前提としています。

## プロジェクトをcloneする

1. IntelliJを起動し、 `Check out from Version Control` > `Git` を選択します。

2. URL欄にclone元のURLを入力します。<br>
本ページ右上の『Clone or download』をクリックすると、URLをコピーできる吹き出しが表示されます。

3. Cloneボタンをクリックします。<br>
"Would you like to open it?" のメッセージが出た場合、『Yes』を選択してプロジェクトを開いてください。<br>
画面下部にステータスが表示されます。バーの表示が消えればcloneは完了です。

## アプリケーションを起動する

IntelliJ で Mavenウィンドウ の `Execute Maven Goal` から、以下に記載する各コマンドを順番に実行してください。
- Mavenウィンドウは、IntelliJ のメニューから `View` > `Tool Windows` > `Maven` で開きます。
- `Execute Maven Goal` を開くには、Mavenウィンドウ上部の青い"m"の付いたアイコンをクリックします。<br>
`Command line` に実行したいコマンドを入力して `Execute`ボタンで実行します。

1. データベース(h2)を起動する。<br>
    ```sh
    exec:java@h2-start
    ```

2. db/ddl配下のDDLの実行からダンプファイル作成までを行う。
    ```sh
    -P gsp clean generate-resources
    ```

3. アプリケーションをビルドして起動する。
    ```sh
    clean compile waitt:run
    ```
    コマンド実行後、自動でブラウザが立ち上がります。

---


# 参考

- [使用している技術](https://github.com/tiscon/tiscon4-startup-guide/blob/master/content/aboutUsingTechnology.md)
- [H2 Databaseに登録したデータを確認する](https://github.com/tiscon/tiscon4-startup-guide/blob/master/content/h2Database.md)
共有スライド
https://docs.google.com/presentation/d/11s_3iyVdz5oZ1e12qzjZS40Nzc-qX7gLSzGtyJjFOuc/edit?usp=sharing
