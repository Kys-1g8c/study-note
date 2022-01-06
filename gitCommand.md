# 既存のリポジトリのクローン
  `$ git clone <プロトコル(https or SSH)>`
  
  既存のGitリポジトリをコピーする
    
  ## プロトコル（httpsとSSH）の違い
  ### https
  - githubのユーザー名、パスワードで認証
  - clone速度が早い
  - githubの推奨方式

  ### SSH
  - github上でSSH公開鍵を設定し、そのパスフレーズで認証

  → 今回はSSHにしてしまったが、httpsの方がメリットが多い

  ## 参考資料
  [Githubからクローンする時のプロトコルの違い](https://qiita.com/smiler5617/items/2b06172b64499ad99942) 

  [GitHubのremote URLにはどのプロトコルを使えばよいのか？](https://qiita.com/chroju/items/67da13c672efcd2bc787)

  [https時代のgitアカウントを使い分ける方法のメモ](https://tech-1natsu.hatenablog.com/entry/2018/10/27/102621)

# ローカルリポジトリの作成
  `$ git init`

    .gitフォルダを作る
    今いるディレクトリをgitで管理するためのコマンド

  ## 参考資料
  [Git の作業ツリーを作成する](https://maku77.github.io/git/basic/init-and-clone.html)

  [initしてremote addするのとcloneするのの違い](https://hokaccha.hatenablog.com/entry/20110802/1312278626)



# 変更内容をステージングする
  `$ git add <ファイル名>`

    変更内容をインデックスに追加してコミット対象にする
    これをしてからコミットする必要がある
    
  ## TIPS
    なんでステージングが必要なのか？
    →変更部分をまとめることができてわかりやすくなるから

  ### 例
    コミットメッセージ : "A機能のバグ修正"
      A機能ファイル
      B機能ファイル ← A機能の修正には関係ないから除外したい
      "$ git add A機能ファイル" にすることでA機能ファイルだけコミットすることが可能！
      

  ## オプション
  `$ git add .`
      カレントディレクトリ以下のすべての変更があったファイルがステージングされる

    $ git add -u
      すでにバージョン管理されていて変更があったファイルがステージングされる
      変更されたファイル、削除されたファイルなど（新しく作られたファイルはステージングされない）

    $ git add -A
      変更があったすべてのファイルがステージングされる

    → "$ git add ." と "git add -A"は似ているが、ディレクトリの位置によって変わってくる


  ## 参考資料
  [git add ってなんのためにやるの？ Gitの「ステージング」をイラストで解説します！](https://kray.jp/blog/expound-git-add/)
  
  [git add -u と git add -A と git add . の違い](https://note.nkmk.me/git-add-u-a-period/)


# 変更内容をコミットする
  `$ git commit`

    ステージングされているものをコミットする
    コミットメッセージを入力する場面に飛ぶ
    vimで書くのでvimも勉強する必要があるかも？

  
  ## コミットメッセージの書き方
    1行目 変更内容のタイトル
    2行目 空白
    3行目 変更内容の詳細

    1行目にprefixをつけると良い
    feat: 新しい機能
    fix: バグの修正
    docs: ドキュメントのみの変更
    style: 空白、フォーマット、セミコロン追加など
    refactor: 仕様に影響がないコード改善(リファクタ)
    perf: パフォーマンス向上関連
    test: テスト関連
    chore: ビルド、補助ツール、ライブラリ関連
      
    ex. "fix: 削除ボタンを押しても、削除されないバグを修正"

  ## 参考資料
  [僕が考える最強のコミットメッセージの書き方](https://qiita.com/konatsu_p/items/dfe199ebe3a7d2010b3e)

# プッシュ
  `$ git push `
    
    ローカルリポジトリの内容をリモートリポジトリに反映する

    ex. git push origin master
    ローカルブランチ「master」をリモートレポジトリ「origin」上の同名のブランチに反映する

  ## 参考資料
  [git push コマンドの使い方と、主要オプションまとめ](https://www-creators.com/archives/1472)

# ブランチの作成
  `$ git branch <name>`

    <name>という名前のブランチを作成する

    【TIPS】
    なぜブランチを分けるか？
    ブランチを分けることで既存の作成した機能に影響を与えずに、新しい機能を追加する作業ができる。
