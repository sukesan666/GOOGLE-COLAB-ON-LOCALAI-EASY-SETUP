# GOOGLE-COLAB-T4-L4
GOOGLE COLAB上にローカルAIを作るノートブックです。colab上のGPUに合ったファイルを読み込んでセルを再生するとcolab上にローカルAIとコードエディタと通信するためのトンネルのURLが作れます。

コードエディタにプラグインのコンテニューが必要です。初心者用です。

GPU（ランタイム）に合ったファイル使ってください。

一番目のセルでグーグルドライブに接続して、AIモデルを再びダウンロードしなくてもいいようになります。

なぜかアルパカのソフトやトンネルのソフトのダウンロード失敗が多いため、根気強く試してください。

AIモデル以外はグーグルドライブには保存しないほうがいいそうです。権限の問題が起きやすいそうです。

GOOGLE COLABは、閉じたときやランタイムの構成を変えた時にリセットされるので、また１番目のセルからやり直してください。

最後に出力されたURLをコピーしてプラグインのcontinueがインストールされたコードエディタのAIに使いたいＧＰＵのファイルをともに渡して、ＹＡＭＬファイルを書いてもらってください。

最近、cofigファイルの拡張子はyamlになったそうです。

次回起動時、ＧＰＵを変えない場合は、セルを１番から再生してＵＲＬを出力してコードエディタのＡＩに書き換えてもらってください。

AIモデルを変えたい場合は、コードエディタのAIにファイルを渡して（COLABのAIに渡すと古い形式で書かれるかも）、コード出してもらったらコピーしてCOLABにいき、二番目のセルを消してペーストしてください。

This is a notebook for creating a local AI on Google Colab. If you load a file compatible with the GPU on Colab and run the cells, you can generate a tunnel URL that allows the local AI to communicate with the code editor on Colab.

You’ll need the “Continue” plugin for the code editor. This is intended for beginners.

Please use a file compatible with your GPU (runtime).

The first cell connects to Google Drive, so you won’t need to download the AI model again.

For some reason, downloads of the Alpaca software and tunnel software often fail, so please be patient and keep trying.

It’s recommended that you do not save anything other than the AI model to Google Drive, as this can easily lead to permission issues.

Since Google Colab resets when you close it or change the runtime configuration, please start over from the first cell.

Copy the URL output at the end, then pass it along with the file for the GPU you want to use to the AI in your code editor (where the “Continue” plugin is installed) and have it generate the YAML file.

Apparently, the config file extension has recently changed to `yaml`.

The next time you launch the session, if you’re not changing the GPU, please replay the cells starting from the first one, output the URL, and have the code editor’s AI rewrite the code.

If you want to change the AI model, pass the file to the code editor’s AI (if you pass it to Colab’s AI, it might be written in the old format), copy the generated code, go to Colab, delete the second cell, and paste it there.

Translated with DeepL.com (free version)
