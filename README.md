# sns-story-assets

**Instagramストーリーズの自動投稿のために、生成した画像を公開URLで配信するだけのリポジトリ。**

## なぜ public なのか

Instagram Graph API の Content Publishing は **`image_url` に公開URLしか受け付けない**
（ローカルファイルもBasic認証付きURLも渡せない）。GitHub Pages で配信するために public にしている。

🔴 **ここに秘密を置かない。** 中身は翌日Instagramに公開されるストーリーズ画像だけ。

## 正本はどこか

- 画像の生成元 → `~/dev/sns-insights/stories/`（**private**。`topics.json` が承認対象の正本）
- ここに入るのは `stories/out/*.png` のコピー。**ここを直接編集しない**

## 配信URL

```
https://hokutomiyazaki-arch.github.io/sns-story-assets/stories/<id>.png
```

## 更新のしかた

`~/dev/sns-insights` 側で:

```
./.venv/bin/python stories/publish_assets.py
```

（`stories/out/*.png` をここへコピーして commit・push し、公開URLを表示する）
