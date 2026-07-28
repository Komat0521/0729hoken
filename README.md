# AI時代の学校 ／ 養護教諭のための生成AI研修（120分）

養護教諭向け 120分研修のスライドです。reveal.js を使った単一HTMLで、GitHub Pages にそのまま公開できます。

- 全44スライド（第1部〜第7部＋付録①〜⑤）
- 画面上部に「第◯部／経過時間」、下部に120分のタイムラインを常時表示
- 発表者ノート付き（`S`キーで発表者ビュー）

---

## 公開のしかた（GitHub Pages）

1. GitHubで新しいリポジトリを作る（例：`ai-yogo-kyoyu`／Public）
2. `index.html` と `README.md` をアップロード（`Add file` → `Upload files` → `Commit changes`）
3. リポジトリの `Settings` → 左メニューの `Pages`
4. **Source** を `Deploy from a branch`、**Branch** を `main` / `/ (root)` にして `Save`
5. 1〜2分待つと `https://ユーザー名.github.io/リポジトリ名/` で公開されます

会場ではこのURLを開けばOKです。ネットが不安な会場では、`index.html` をローカルに保存して開いても動きますが、フォントとreveal.js本体はCDN読み込みのため、**オフラインなら事前に一度開いてキャッシュさせる**か、下記「オフライン対応」を行ってください。

---

## 操作方法

| キー | 動作 |
|---|---|
| `→` / `Space` | 次のスライド |
| `←` | 前のスライド |
| `S` | 発表者ビュー（ノート・タイマー・次スライド表示） |
| `F` | 全画面 |
| `Esc` / `O` | スライド一覧 |
| `B` | 画面を暗転（会場に注目させたいとき） |

### PDFに書き出す
URLの末尾に `?print-pdf` を付けて開き（例：`.../index.html?print-pdf`）、Chromeで `Ctrl/Cmd + P` → 送信先「PDFに保存」→ 用紙「横」、余白「なし」、背景のグラフィック「オン」。

---

## 編集のしかた

### スライドを1枚足す
`<section>` をコピーして中身を書き換えるだけです。`data-` 属性が上部の表示とタイムラインに反映されます。

```html
<section data-part="第3部" data-title="仕事はここまで変わる" data-clock="45">
  <div class="eyebrow"><span class="cross"></span>小見出し</div>
  <h2>スライドの見出し</h2>
  <ul>
    <li>項目</li>
  </ul>
  <p class="note">補足の一文</p>
  <aside class="notes">発表者ノート（会場には出ません）</aside>
</section>
```

| 属性 | 意味 |
|---|---|
| `data-part` | 画面上部に出る「第◯部」 |
| `data-title` | その部のタイトル |
| `data-clock` | 開始からの経過分。下部タイムラインの位置になります |
| `data-cover="true"` | 表紙・締めなど、上下の表示を隠したいとき |

### よく使う部品

| クラス | 用途 |
|---|---|
| `.grid.g2` `.g3` `.g4` | カードを2〜4列に並べる（中に `.card`） |
| `.vs` + `.side.bad` / `.side.good` | ×と○の対比 |
| `.flow` + `.step` | 「生成→比較→修正→完成」のような流れ |
| `.prompt` | プロンプト例の箱（`.is-bad` で赤枠） |
| `.alert` | 注意喚起（第6部で使用） |
| `.check` | チェックリスト（付録③） |
| `.list50` | 2段組みの一覧（付録①のプロンプト集） |
| `<span class="cross"></span>` | 緑十字のマーク |

### 色を変える
`<style>` の先頭 `:root` にまとめてあります。ここだけ触れば全体の配色が変わります。

```css
--green:  #2E8B72;   /* 基調色（緑十字） */
--coral:  #DD6055;   /* 注意・× */
--paper:  #F2F6F3;   /* 背景 */
--ink:    #16323B;   /* 文字 */
```

---

## 会場に合わせて直すところ

- 表紙の日付・会場・講師名
- 第2部のツール表（自治体で使用が認められているツールに絞る）
- 第4部の題材8つ（その学校で困っている業務に差し替えると食いつきが良くなります）
- 第5部のケース（実在の事例は使わず、必ず一般化した形で）

---

## オフライン対応（任意）

CDNに頼らず動かす場合は、reveal.js を同梱します。

```
リポジトリ/
├── index.html
└── dist/
    ├── reveal.js
    └── reveal.css
└── plugin/notes/notes.js
```

[reveal.js のリリース](https://github.com/hakimel/reveal.js/releases) からダウンロードし、`index.html` 内のCDNのURLをローカルパスに書き換えてください。フォントは端末のゴシック体にフォールバックします。

---

## ライセンス

スライドの内容は自由に改変してお使いください。reveal.js は MIT License です。
