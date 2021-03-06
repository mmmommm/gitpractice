# gitpractice  
  
自分自身がrebaseやstash、mergeなどについてわかっていないため擬似チーム開発環境を作って練習するために作成した練習用リポジトリです。  
自分が開発する時の順番みたいなのを忘れた時に見返すためにも作りました。  
間違っていたらプルリクを下さると、、、  
  
## 一連の流れ  
  
ローカルにdevブランチ、リモートにremotes/origin/devブランチを作って紐づけておく  
  
`git checkout -b dev`  
devブランチを作ってそこに移動  
  
`git branch -a`  
ブランチができているかを確認  
  
`git push -u origin dev`  
リモートに作成  
  
`git branch -a`  
できているかを確認  
  
`git checkout -b ブランチ名`  
ローカルにブランチを作成してそのブランチに移動  
*この時のブランチ名はgit-flowに従う(そんな大した規模じゃないので下の説明ではreleaseとかは切ってないです)  
[git-flowの説明](https://qiita.com/KosukeSone/items/514dd24828b485c69a05)  
  
作業して`git add, commit, push`する  
このpushをした時にリモートリポジトリにブランチが作成される  
  
### devへのマージ  
  
`git checkout dev`  
  
`git merge ブランチ名`  
そのブランチでpushしたのをdevにマージ  
  
`git pusn origin dev`  
取り込んだマージをリモートに送信  
  
`git branch -d ブランチ名`  
ローカルのブランチを削除  
  
`git pusn origin :ブランチ名`  
リモートブランチを削除  
*エラーが出たときは`git remote prune origin`  
  
### masterへのマージ  
  
```
git checkout master  
git merge dev  
git push origin master  
```
*devブランチは消さなくていい  
  
## 参考URL  
  
[git機能一覧](https://qiita.com/gold-kou/items/7f6a3b46e2781b0dd4a0#%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB)  
[リモートブランチと追跡ブランチは違うって話](https://www.kaeruspoon.net/articles/1078)  
[一連の流れについて分かり易かった](https://www.kaeruspoon.net/articles/1078)  
[上流ブランチについて](http://www-creators.com/archives/4931)  
[masterブランチに間違えてcommitしてしまった時の対処法](https://qiita.com/rh_/items/2498e326810888b11415)  
  
[こわくないgit](https://www.slideshare.net/kotas/git-15276118)  
  
[ブログ](https://www.atmarkit.co.jp/ait/articles/1703/29/news021.html)  
  
[けんたさんのやつ](https://www.youtube.com/watch?v=wlY8YG-eB8E)