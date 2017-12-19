# 2
## Benefits of Composition
? Compositinoってなに？

`関数のコーディング規約`

ひとつのことをするべき

```js
function getProfileLink (username) {
  return 'https://github.com/' + username
}

function getProfilePic (username) {
  return 'https://github.com/' + username + '.png?size=200'
}

function getProfileData (username) {
  return {
    pic: getProfilePic(username),
    link: getProfileLink(username)
  }
}
```

```
getProfileLink - ちょうどユーザーのGitHubプロファイルリンクの文字列を構築する
getProfilePic - ちょうどユーザーのGitHubプロフィールの画像を文字列で構築する
getProfileData - 新しいオブジェクトを返す
```

`理由`

```
コードリーディングし易い
管理し易い
```

https://www.linkedin.com/pulse/compose-me-function-composition-javascript-kevin-greene

## React & Composition

```
<Page />
<Article />
<Sidebar />
```

上記と同じようにコンポーネントが3つある

```js
<Page>
  <Article />
  <Sidebar />
</Page>
```

統合して、ネストしてみる

# 3宣言コードとは何ですか？

`命令コード`

JavaScriptコードが命令的に書かれているとき、私たちはJavaScriptに何をすべきか、それを行う方法を正確に伝えます。まるでどのステップを実行するかを正確にJavaScript コマンドを与えているかのように考えてください。たとえば、私はあなたに謙虚なforループを与えます：

```
イテレータの初期値を設定する - （let i = 0）
for停止する必要があるときにループを伝える- （i < people.length）
現在の位置に人を取得し、感嘆符を追加する - （people[i] + '!'）
データを格納i番目他のアレイ内の位置- （ excitedPeople[i]）
i変数を1つ増やす- （i++）
```

```js
for (let i = 0; i < people.length; i++) {
  excitedPeople[i] = people[i] + '!'
}
```

`宣言コード`

命令型コードとは対照的に、宣言型コードがあります。宣言型コードでは、最終結果を得るためのすべてのステップをコーディングしません。代わりに、私たちは何をしたいのかを宣言し、JavaScriptがそれを処理します。この説明は少し抽象的ですので、例を見てみましょう。for私たちが見ていた命令的なループコードを取り除き、それをより宣言的にするためにリファクタリングしましょう。

```js
const excitedPeople = people.map(name => name + '!')
```

```js
const people = ['Amanda', 'Geoff', 'Michael', 'Richard', 'Ryan', 'Tyler']
const longNames = people.filter(name => name.length > 6)
```

## reactは宣言的である

```html
<button onClick={activateTeleporter}>Activate Teleporter</button>
```

# 4単方向データフロー

reactは単方向、angularなどは双方向

AngularやEmberのようなフロントエンドフレームワークは、双方向のデータバインディングを利用しています。双方向データバインディングでは、更新される場所に関係なく、データはアプリ全体で同期された状態に保たれます。モデルがデータを変更すると、ビュー内のデータが更新されます。あるいは、ユーザーがビュー内のデータを変更すると、モデル内のデータが更新されます。双方向データバインディングは本当に強力ですが、アプリケーションを推論するのが難しくなり、データが実際に更新されている場所を知ることができます。
