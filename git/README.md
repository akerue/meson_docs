# Gitルール

## 主要ブランチ名

### master
本番環境を反映するブランチ。

### develop
開発環境を反映するブランチ。

### staging
masterにマージする前にコミットするブランチ。
stagingブランチのみがmasterにマージして良い。

### feature/XXX
機能を追加するためのブランチ。
一つの機能を追加するたびにこのブランチを生やす。
developから分岐させる。

### hotfix/XXX
緊急のバグ修正用のブランチ。
masterから分岐させる。


## マージのルール
develop, masterにマージする時にはGithubのPRを出して、
他の開発者に差分を確認してもらう。

## 開発フロー
### 通常開発

- developをmasterからマージして最新の状態に更新する
- 機能を追加する際にdevelopからfeatureブランチを分岐させて機能を実装
- 機能追加を完了したら、developにマージ
- masterにマージする際にはまずdevelopをstagingにマージして確認
- stagingで動作を確認して問題なさそうであればstagingからmasterに追加

### 緊急のバグ修正

- masterからhotfixブランチを分岐させる
- hotfix上でバグ修正を行い、完了したらstagingにマージ
- stagingで動作を確認し、問題なければstagingからmasterにマージ
