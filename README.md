# 🚀 GOOGLE-COLAB-ON-LOCALAI-EASY-SETUP

**「自分のパソコンのスペックが低くても、Google Colab の高性能 GPU を使って無料でローカル AI（Ollama）を動かし、VS Code 等からチャットやファイル自動作成をさせる」** ための超初心者向けノートブック集です。

難しい設定やコードの書き換えを**自分で覚える必要はありません**。  
すべて **AI コーディングエージェント（Antigravity / Cursor / GitHub Copilot / Claude 等）に手伝ってもらう前提** で作られています！

---

## 📁 1. どのファイルを使えばいい？（GPU別一覧）

Google Colab の「ランタイムのタイプ（GPU）」に合わせてファイルを選んでください。  
右側の **「Open in Colab」ボタン** を押すと、ダウンロードしなくても一発で Google Colab 上で開けます！

| ファイル名 | 対象 GPU (VRAM) | 入っている主な AI モデル | おすすめ度・特徴 | Colab で直接開く |
| :--- | :--- | :--- | :--- | :--- |
| **`T4_gpu.ipynb`** | **T4** (16GB) | 軽量コーディングモデル (7B〜) | **無料枠でも使える**お試し用 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sukesan666/GOOGLE-COLAB-ON-LOCALAI-EASY-SETUP/blob/main/T4_gpu.ipynb) |
| **`L4_gpu_fixed.ipynb`** *(推奨)*<br>*(旧: `L4_gpu.ipynb`)* | **L4** (24GB) | `qwen2.5-coder:14b`<br>`qwen3:14b` | **コスパ最強！** Cline / Zoo Code のファイル自動操作（ツール呼び出し）に対応した改良版 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sukesan666/GOOGLE-COLAB-ON-LOCALAI-EASY-SETUP/blob/main/L4_gpu_fixed.ipynb) |
| **`A100_gpu.ipynb`** | **A100** (40GB / 80GB) | `qwen3-coder:30b`<br>`gemma4:31b` (Google)<br>`gemma4:26b` / `qwen3:32b` | **30B級の大型モデル**が爆速で動くプロ仕様（64K長文対応） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sukesan666/GOOGLE-COLAB-ON-LOCALAI-EASY-SETUP/blob/main/A100_gpu.ipynb) |
| **`G4_gpu.ipynb`** | **G4** (96GB) | `qwen3-coder-next` (80B MoE)<br>`gemma4:31b` / `gemma4:26b`<br>`qwen3-coder:30b` | **96GB VRAM** を活かして80Bモデルや複数モデル同時常駐ができる超高性能版（128K長文対応） | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sukesan666/GOOGLE-COLAB-ON-LOCALAI-EASY-SETUP/blob/main/G4_gpu.ipynb) |
| **`G4_gpu90gb.ipynb`** | **G4** (96GB) | `qwen3-coder-next:q8_0` (約85GB)<br>`gemma4:31b-it-bf16` (約63GB) | **ロマン枠・限界突破！** 96GB メモリを1つの無劣化モンスターモデルでギリギリまで使い切る仕様 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sukesan666/GOOGLE-COLAB-ON-LOCALAI-EASY-SETUP/blob/main/G4_gpu90gb.ipynb) |

---

## 🛠️ 2. 事前準備（必要なもの）

1. **Google アカウント**（Google Colab と Google ドライブを使います）
2. **AI コーディングエージェントが入ったエディタ**（以下のどれか）
   - **Antigravity** / **Cursor** / **VS Code**
   - ローカルAIを繋ぐ拡張機能：**Zoo Code**、**Cline**、**Roo Code**、**Continue** など

---

## ▶️ 3. 使い方（3ステップで完了！）

### ステップ①：Google Colab でセルを順番に再生する
1. 上の表から使いたい GPU のノートブックを Google Colab で開きます（または `.ipynb` ファイルをダウンロードして Colab にアップロードします）。
2. Colab 上部メニューの **「ランタイム」→「ランタイムのタイプを変更」** から、ファイル名と同じ GPU（`T4` / `L4` / `A100` / `G4`）を選びます。
3. **1番目のセルの再生ボタン（▶）** を押します。
   - Google ドライブへの接続許可を求められたら「許可」します。
   - ※これでダウンロードした AI モデルが Google ドライブに保存され、次回からダウンロード時間を短縮できます（空き容量が足りない場合は自動で Colab 本体に保存されます）。
4. **2番目のセルの再生ボタン（▶）** を押します。
   - AI 本体（アルパカのソフト＝Ollama）と通信用トンネル（Cloudflare）が自動でインストールされ、AI モデルの準備が始まります。
5. 一番下に以下のような **URL（`https://〇〇.trycloudflare.com`）** が出たら準備完了です！
   ```text
   🎉 準備完了！以下のURLを Zoo Code / Cline の Base URL に貼ってください：
   👉 https://xxxx-xxxx-xxxx-xxxx.trycloudflare.com
   ```

---

### ステップ②：AI に頼んでエディタの設定をしてもらう（コピペでOK！）
自分で設定ファイルを書く必要はありません。  
お使いのコードエディタにいる **AI（チャット欄）** に、使った `.ipynb` ファイルを添付（またはドラッグ＆ドロップ）して、以下の文章をコピペして送ってください。

#### 💬 初回設定用のコピペ指示文
```text
Google Colabでこのノートブックを実行して、ローカルAI（Ollama）を起動しました。
発行されたトンネルURLは以下です：
https://ここにコピーしたURLを貼る.trycloudflare.com

私が使っている拡張機能（Continue / Cline / Zoo Code / Roo Code）で、このローカルAIを使ってファイル操作ができるように設定を確認・書き換えてください。
```

---

### ステップ③：2回目以降（URLが変わったとき）の頼み方
Google Colab を閉じたり再起動すると、毎回 URL が新しくなります。  
次回使うときは、Colab でまた **1番目 → 2番目のセルを再生** して、新しい URL を AI に渡すだけです！

#### 💬 2回目以降（URL更新用）のコピペ指示文
```text
Colabを再起動してURLが変わりました。新しいURLに書き換えてください：
https://ここに新しいURLを貼る.trycloudflare.com
```

---

## 🔄 4. 別の AI モデルや別の GPU に改造したいとき

「もっと違う AI モデルを入れてみたい」「別の GPU 向けにパラメーターを調整したい」という時も、自分でコードをいじる必要はありません。  
エディタの AI に `.ipynb` ファイルを渡して、こう頼んでください：

#### 💬 モデル変更・改造用のコピペ指示文
```text
このColabノートブックのAIモデルを「〇〇（入れたいモデル名や用途）」に書き換えて、GPUに合ったパラメーターに調整してください。
書き換えたノートブックを作るか、2番目のセルに貼り付ける用のコードを出してください。
```
AI がコードを出してくれたら、それをコピーして Colab の **2番目のセルの中身を消して貼り付けるだけ** です！

---

## ⚠️ 5. 初心者がハマりやすい注意点（必読）

* **ダウンロードが途中で失敗するとき**
  * なぜか Ollama（アルパカのソフト）や Cloudflare トンネルのダウンロードが通信エラーで失敗することがよくあります。失敗したら**もう一度セルの再生ボタン（▶）を押してやり直して**ください（内部で壊れたゴミファイルを自動削除する仕組みが入っています）。
* **Colab の画面は閉じないで！**
  * Google Colab のタブを閉じたり、ランタイム（GPU）の種類を変更すると、中身がすべてリセットされて URL が切れます。切れたらまた **1番目のセルから順番に再生** してください。
* **Google ドライブには「AI モデル以外」は保存しない**
  * プログラム本体（実行ファイル）まで Google ドライブに置くと、権限エラー（Permission denied）で動かなくなります。このノートブックでは**「AI モデルのデータだけ」を安全にドライブへ保存する**ように設定してあるので、そのまま使えば安心です。

---
---

# 🌐 English Guide (For Beginners)

This repository provides beginner-friendly Google Colab notebooks that set up a **Local AI (Ollama)** on Colab GPUs and generate a **Cloudflare Tunnel URL** so your code editor can talk to it.

You **do not** need to know how to write config files or tune parameters yourself—**everything is designed so your AI Coding Agent does the setup for you!**

### How to Use

1. **Choose the notebook matching your Colab GPU runtime** (`T4`, `L4`, `A100`, or `G4`).
2. **Run Cell 1**: Connects to your Google Drive so downloaded AI models are saved persistently (you won't have to re-download them every time).
   * *Note: Only AI model weights should be stored in Google Drive; storing binaries on Drive causes permission errors.*
3. **Run Cell 2**: Installs Ollama (the alpaca software) and Cloudflare Tunnel, downloads the optimized AI models, and outputs a tunnel URL (`https://xxxx.trycloudflare.com`).
   * *Tip: Downloads of Ollama or Cloudflare occasionally fail due to network hiccups. If an error occurs, simply re-run the cell!*
4. **Let your AI Coding Agent configure your editor**:
   Copy the generated URL, attach the `.ipynb` file you used to your editor's AI chat (e.g., Antigravity, Cursor, Copilot, Cline, Zoo Code, Continue), and ask:
   > *"I started Ollama on Google Colab using this notebook. Here is the tunnel URL: `https://xxxx.trycloudflare.com`. Please configure my coding extension so I can use this local AI."*
5. **Next time you launch Colab**:
   Colab resets whenever you close the tab or change the runtime GPU. Just run Cell 1 and Cell 2 again, copy the new URL, and ask your editor's AI to update the URL.
6. **Want to change the AI models or parameters?**:
   Give the `.ipynb` file to your AI Coding Agent and ask it to rewrite the models/parameters for you. Then copy the generated code and replace the contents of the second cell in Colab!
