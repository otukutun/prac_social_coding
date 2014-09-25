# ソーシャルコーディング

## 目的
githubを用いてソーシャルコーディングを体得する．

## 作るもの
ホームページ．随時変更アリ．

参加してもらえる方はなにをプルリクしたら良いかわからないと思うので，Issuesにあるもののどれかをやってみましょう．

## やり方
1. github(https://github.com/otukutun/prac_social_coding) Forkをクリック.  
(自分のgithub上にフォークされます)   

2. ローカル環境にクローンする
```sh
$ git clone https://github.com/[user_name]/prac_social_coding
```
3. ブランチを作成
```sh
$ cd prac_social_coding
```
```sh
$ git checkout -b [branch_name]
```
4. ファイル追加・修正・削除などしてから
```sh
$ git add [file_name]
```
```sh
$ git commit -m "[commit_message]"
```
5. 自分のgithubリポジトリ(forkしたやつ)にpushする
```sh
$ git push origin [branch_name]
```
6. githubのページからPull Reauest  ボタンをクリック
 
 ## 注意
 * 自分が作業するときは常に最新からのブランチにしよう
 * 自分のgithubリポジトリも常に最新のものにしよう( remoteにupstream追加する )

 ### 本家から最新をもってきて自分のところも最新状態にする

 1. masterブランチに切り替える
 ```sh
 $ git checkout master
 ```

 2. リモート先（本家）を追加する
 ```sh
 $ git remote add upstream git@github.com:otukutun/prac_social_coding.git
 ```
 3. 自分のローカルのmasterを最新にする
 ```sh
 $ git pull upstream master
 ```
 4. github側も最新にする
 ```sh
 $ git push origin master
 ```

 この状態でブランチをつくると良いと思います．

 ## Pull Request が Merge されたあとですること

 1. 自分のローカルリポジトリにある、master ブランチと Pull Requestしたブランチが古くなってるはずなので上の**注意**に書いてあることを確認＆実行しましょう

 2. もし本家のmasterが進んだのに、自分の作業ブランチが遅れたmasterを元にしてるというのは良くないのでbranch元をやり直すためにrebaseをしておきましょう
 ```sh
 $ git checkout [branch_name]  
 ```
 ```sh
 $ git rebase master
 ```
 ※ rebaseはよくない場合がある。


 3. 2が良くない時。feature-branchに移動してmergeする(ローカルのmasterが最新の状態で)
 ```sh
 $ git merge master
 ```

 3. ブランチを消してもよいとき（ブランチの役目が終わったとき）
 ```sh
 $ git checkout master
 ```
 ```sh
 $ git branch -D [branch_name]
 ```

 ## shiritoriを続ける場合

 1. ローカルリポジトリにshiritoriブランチの作成
 ```sh
 $ git checkout shiritori
 $ git pull upstream shiritori
 ```
 ※最新のshiritoriブランチをpullするようにしましょう

 2. リモートリポジトリにshiritoriブランチの作成
 ```sh
 $ git push origin shiritori
 ``` 
 ※しりとりを続けてcommitしたらpushするようにしましょう

 3. pull requestを送る場合
  whitech0c0:shiritori　←　ユーザー名:shiritori
   となるようにpull requestを送ること
    ※masterに送るなどブランチを間違えないようにしましょう

    4. 緊急時（なんかミスってshiritoriブランチを削除する場合）
    ```sh
    $ git checkout master
    $ git branch -d shiritori
    $ git push origin :shiritori
    ```
    これでローカルとリモートのshiritoriブランチを削除できる

    ## 約束ごと
    * 失敗を恐れない
    * issueとかgithubの機能をいろいろ使ってみる
    * わからないことは積極的に調べる＆聞く

    このREADMEも間違っている＆わかりずらい箇所があると思うのでみんなで修正していきましょう．

    ## 参考資料
    * [いつやるの？git入門](http:// www.slideshare.net/matsukaz/git-17499005)
    * [こわくないgit](http:// www.slideshare.net/kotas/git-15276118)
    * [デザイナー向けGit解説](http:// uniq.heteml.jp/blog/2012/06/22/%E3%83%87%E3%82%B6%E3%82%A4%E3%83%8A%E3%83%BC%E5%90%91%E3%81%91git%E8%A7%A3%E8%AA%AC-%E3%82%A8%E3%83%B3%E3%82%B8%E3%83%8B%E3%82%A2%E3%81%A8%E5%90%8C%E3%81%98%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81/)
    * [Git初心者に捧ぐ！Gitの「これなんで？」を解説します。](http:// kray.jp/blog/git-why-explanation/)
