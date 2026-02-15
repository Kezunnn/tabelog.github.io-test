現在のwebページは以下から
https://kezunnn.github.io/tabelog.github.io-test/

# -- 作業開始 ---

```jsx
git checkout main                 # 作業の起点を main ブランチに切り替える（まず“本流”に戻る）
git pull                          # リモート（GitHub）の main の最新状態を取り込む（作業前に同期）
git checkout -b <feat or fix>/<short-name> # 新しい作業ブランチを作って、そのブランチに切り替える（作業はここでやる）
```

# -- 変更→最低限チェック→コミット→push ---

```jsx
git add -A                        # 変更を全部ステージング（次のコミットに含める候補に追加）
git commit -m "feat: <summary>"   # ステージングした変更をコミット（履歴として確定。-mはメッセージ指定）
git push -u origin feat/<short-name> # ブランチをGitHubへ初回push（-uで以後 git push だけで済むよう追跡設定）
```

# -- マージ後（片付け）---

```jsx
git checkout main                 # main に戻る（次の作業の準備）
git pull                          # マージ後の main を最新化（GitHub側でマージした内容を取り込む）
git branch -d feat/<short-name>   # 使い終わった作業ブランチをローカルから削除（-dは安全削除：未マージなら拒否）
```
