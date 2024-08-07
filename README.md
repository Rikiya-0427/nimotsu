![logo](https://user-images.githubusercontent.com/44780846/206611013-34fda129-ca23-4118-95b0-0ae57e0d40cd.png)

**nimotsu**: 📦 荷物の配達状況を追跡するCLIツール

![screenshot](https://user-images.githubusercontent.com/44780846/141614236-b7ea80b9-e76f-4514-a0ce-d1fb19e5290a.png)

## 対応している配送業者

- [日本郵便](https://www.post.japanpost.jp/index.html)
- [ヤマト運輸](https://www.kuronekoyamato.co.jp/)
- [佐川急便](https://www.sagawa-exp.co.jp/)
- [OCS](https://www.ocs.co.jp/)

## インストール

### Homebrew

```sh
brew tap Rikiya-0427/tap
brew install nimotsu
```

### Scoop

```
scoop bucket add Rikiya-0427 https://github.com/Rikiya-0427/scoop-bucket.git
scoop install Rikiya-0427/nimotsu
```

### Go

```sh
go install github.com/Rikiya-0427/nimotsu@latest
```

## コマンド

### get

`get [<追跡番号>] [配送業者フラグ]`

追跡番号から荷物を追跡します。

```txt
$ nimotsu get 1122334455 --sagawa
```

配送業者を指定しなかった場合、選択肢が表示されます。

```txt
$ nimotsu get 112233445566
Use the arrow keys to navigate: ↓ ↑ → ←
Carrier?
  > 日本郵便
    ヤマト運輸
    佐川急便
```

### get all

リスト内の荷物を全て追跡します。

```txt
$ nimotsu get all
```

### add

`add [<追跡番号>] [配送業者フラグ] [--comment "コメント"]`

リストに荷物を追加します。

コメントを省略した場合、"なし" が設定されます。

```txt
$ nimotsu add 112233445566 --japanpost --comment "🍺"
✔ Added!
```

配送業者・コメントを指定しなかった場合、対話形式で入力できます。

```txt
$ nimotsu add 112233445566
Carrier: 日本郵便
Comment: beer🍺
✔ Added!
```

### remove

リスト内の荷物を選択して削除します。

```txt
$ nimotsu remove
Use the arrow keys to navigate: ↓ ↑ → ←
Tracking number?
    112233445566
    223344556677
  > 123456789123
Carrier: 日本郵便
Comment: beer🍺
```

### remove all

リスト内の荷物を全て削除します。

```txt
$ nimotsu remove all
✔ Removed all!
```

### edit

リスト内の荷物を選択してコメントを変更します。

```txt
$ nimotsu edit
Tracking number: 444191245470
Comment: iPad
✔ Edited!
```

### list

リスト内の荷物を表示します。

```txt
$ nimotsu list
```

### version

バージョンを表示します。

```txt
$ nimotsu version
📦 nimotsu ver.x.x.x
```
