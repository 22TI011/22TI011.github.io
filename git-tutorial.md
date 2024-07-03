# git
- 分散管理型のバージョン管理システム
- 変更履歴が残る
- 変更した箇所に戻ることができる
- 他人と共同編集できる

## gitの設定
- グローバルセッティング
    - ホスト（OS）全体のgitの設定
- git config –global
- git config –global user.name yourname
- git config –global user.email yourname@example.com

## gitによる共同編集（コンフリクト）
- git stash
    - 一時退避
- originにあるindex.htmlとローカルのindex.htmlの比較
    - git diff origin -- index.html
- 一時退避
    - git stash
- originからプル（同期）
    - git pull
- 一時退避したものの変更を加える
    - git stash pop

## コミット
- [ファイル作成／変更／削除]の記録
- 対象ファイルは一つでも複数でもよい
- コミットの単位はユーザーが自由に決定する

## レポジトリ
- gitが管理するプロジェクトのフォルダ
1. ローカルレポジトリ
    - 個々のプロジェクト実行環境
    - ワークツリー（worktree）
    - ***untracked***
        - gitで管理されていないファイルの状態
    - ***unmodified***
        - gitで管理されているが変更されていないファイルの状態
    - ***modified***
        - gitで管理されていて変更されたファイルの状態
    - ステージングエリア（staging area）、インデックス（index）
        - gitで管理するファイルを登録する
    - ***staged***
        - staging areaに登録されたファイルの状態
    - Gitディレクトリ
        - コミット(commit)により変更を登録
        - commitは原則、変更・削除できない
        - commitの変更・削除も記録として残る
        - commitされたファイルはunmodifiedの状態になる
2. リモートレポジトリ
    - 共有の管理場所
        - Github/Gitlab など
    - ローカルレポジトリでcommitされた変更をリモートレポジトリへ反映 (git push)
    - リモートレポジトリにある内容をローカルレポジトリに反映 (git pull)

## ブランチ
- 作業を枝分かれさせることができる
- 共同作業・並行作業が可能

## 追跡するブランチの設定
- git branch --set-upstream-to origin/main
    - リモートブランチ（origin/main）と紐付ける設定
- origin
    - リモートでのデフォルトのサーバー

## ブランチマージのコンフリクトの対処例
- git merge --abort 
    - main ブランチを、マージを試行する前の状態に復元
    - git pull コマンドを実行して、マージ先の変更を取得
    - 新しいブランチを作成し、変更を行って、そのブランチを main ブランチにマージ
    - 変更をプッシュ
- git reset --hard
    - マージを開始する前の状態に戻す
    - 影響を受けたファイルに Git によって挿入された情報を使用して、手動で解決

## 既出のgitコマンド（設定・確認系）
- git init
    - gitの初期化・設定開始
- git status
    -ワークツリーのステータスを表示
- git config 
    - 設定周りの確認・変更
- git log
    - ログを表示  
    - -- onelineでコミットメッセージの1行のみの一覧表示
- git diff
    -ファイルの差分を表示

## 既出のgitコマンド（コミット系）
- git add
    - ステージングエリアに追加
- git commit 
    - コミットの実行

## 既出のgitコマンド（修正系）
- git commit --amend --no-edit
    - コミットの修正
- git checkout
    - 削除されたファイルを復旧や過去コミットの復元など（元に戻す変更がstaging area/index内にある場合）
- git reset
    - コミットのリセット
- git revert
    - 「コミットの変更を打ち消す」コミット
- git rm
    - ファイルとindex情報の削除

## 既出のgitコマンド（リモート系）
- git clone
    - レポジトリをコピー
- git pull
    - リモートレポジトリの同期	
- git push
    - 変更をアップロードする
- git request-pull
    - プルリクエスト：変更依頼
- git remote
    - リモートレポジトリの設定

## 既出のgitコマンド（ブランチ系）
- git branch
    - ブランチの作成
- git checkout
    - ブランチの切り替え
- git merge
    - ブランチの統合
    - --ff-only: fast forward only. 変更のない統合先ブランチにマージ（参考）
- git clone
    - レポジトリをコピー
- git push
    - 変更をアップロードする
