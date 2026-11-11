# GOOGLE-COLAB-ON-LOCALAI-EASY-SETUP
GOOGLE COLAB上にローカルAIを作るノートブックです。ファイルを読み込んでセルを再生するとcolab上にローカルAIとコードエディタと通信するためのトンネルのURLが作れます。

AI Coding Agentが必要です。初心者用です。

GPU（ランタイム）に合ったファイル使ってください。

一番目のセルでグーグルドライブに接続して、AIモデルを再びダウンロードしなくてもいいようになります。

なぜかアルパカのソフトやトンネルのソフトのダウンロード失敗が多いため、根気強く試してください。

AIモデル以外はグーグルドライブには保存しないほうがいいそうです。権限の問題が起きやすいそうです。

GOOGLE COLABは、閉じたときやランタイムの構成を変えた時にリセットされるので、また１番目のセルからやり直してください。

最後に出力されたURLをコピーしてAI Coding AgentのAIに使いたいＧＰＵのファイルをともに渡して、configファイルを書いてもらってください。

次回起動時、ＧＰＵを変えない場合は、セルを１番から再生してＵＲＬを出力してコードエディタのＡＩに書き換えてもらってください。

AIモデルを変えたい場合は、AI Coding AgentのAIにファイルを渡して、コード出してもらったらコピーしてCOLABにいき、二番目のセルを消してペーストしてください。

This is a notebook for creating a local AI on Google Colab. When you load the file and run the cells, it generates a tunnel URL that allows the local AI to communicate with the code editor on Colab.

You’ll need AI Coding Agent. This is intended for beginners.

Please use a file compatible with your GPU (runtime).

The first cell connects to Google Drive, so you won’t need to download the AI model again.

For some reason, downloads of the Alpaca software and the tunnel software often fail, so please be patient and keep trying.

It’s recommended that you do not save anything other than the AI model to Google Drive, as this can easily lead to permission issues.

Google Colab resets when you close it or change the runtime configuration, so please start over from the first cell.

Copy the URL output at the end, provide it along with the file for the GPU you want to use in the AI Coding Agent, and have it generate the config file.

The next time you launch the application, if you are not changing the GPU, play back the cells starting from the first one to generate the URL, then have the AI in the code editor rewrite the code.

If you want to change the AI model, provide the file to the AI in AI Coding Agent. Once it generates the code, copy it, go to Colab, delete the second cell, and paste the code there.


Translated with DeepL.com (free version)
