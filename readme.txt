畳み込み再生アプリケーションサンプル 2021/05/11 古川　光照

  フォルダ階層：
    convolutionPlayerSample
        |
        |- impulseフォルダ  インパルス応答波形
        |
        |- sourceフォルダ   ノコギリ波DOWNスウィープ波形、ホワイトノイズのDOWNスウィープ波形
        |
        |- ConvolutionPlayer.exe.config
        |                   インパルス畳み込みディレイエフェクトの簡易プレーヤー関連ファイル
        |
        |- ConvolutionPlayer.exe
        |                   インパルス畳み込みディレイエフェクトの簡易プレーヤー
        |
        |- Audio IO.dll     XAudio2簡易プレビューワ.dll
        |
        |- KLabAudio.dll    オーディオ操作ユーティリティ.dll
        |
        |- KLabUIProps.dll  Windows Form UIユーティリティ.dll
        |
        |- readme.txt       このファイル
 
  ConvolutionPlayer.exeについて：
    動作環境：
      Windows 10 64ビット環境

      以下のランタイムライブラリのインストール
        Microsoft .NET Framework 4.8
          https://support.microsoft.com/ja-jp/topic/windows-%E7%94%A8%E3%81%AE-microsoft-net-framework-4-8-%E3%82%AA%E3%83%95%E3%83%A9%E3%82%A4%E3%83%B3-%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%A9%E3%83%BC-9d23f658-3b97-68ab-d013-aa3c3e7495e0

        Visual Studio 2015、2017、および 2019 用 Microsoft Visual C++ 再頒布可能パッケージ(x64)
          https://support.microsoft.com/ja-jp/topic/%E6%9C%80%E6%96%B0%E3%81%AE%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%82%8B-visual-c-%E3%81%AE%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89-2647da03-1eea-4433-9aff-95f26a218cc0

    使い方：
      Source Folderに適当に波形ファイルをぶち込んでください
      波形ファイルのフォーマットはMicrosoft .wav形式で

      ・48KHz、Int16ビット、Int24ビット、IEEE float 32ビット、ステレオ又はモノラル
        推奨

      ・44.1KHz、Int16ビット、Int24ビット、IEEE float 32ビット、ステレオ又はモノラル
        動作はするが、インパルスの波形のリサンプリング処理は省いているので
        レンダリング後のディレイ間隔が実時間より短くなる

      Previewボタン：
        Source Folerのリストで選択した波形ファイルを再生

      Post Previewボタン：
   　   Source Folerのリスト波形ファイルをImpulse Response Folderで指定した波形ファイルを
        インパルス反応情報と見做してディレイエフェクトをレンダリング
        Output FolderにMicrosoft .wav形式の波形ファイルを作成して再生

      Normalizeトグルボタン：
          ON  ： レンダリング後のノーマライズ有り
          OFF ： レンダリング後のノーマライズ無し
        OFFだと、Source Folerのリストで選択した波形ファイルの音量が極端に小さかったり
        大きかったりすると聴きづらかったり、音が割れたりするので、デフォルトでは
        ONにしてあります

      Stop Previewボタン：
        再生中の波形ファイルの発音停止

      Volume：
        音量(100%～0%)

      Image View：
        左側：
          Source Folerのリストで選択した波形ファイルを表示

        右側：
      　  Impulse Response Folerのリストで選択した波形ファイルを表示
          Post Preview後にはインパルス波形でレンダリングされた
          Output Folderに作成されたMicrosoft .wav形式の波形ファイルを表示

      また、
        Source Folder
        Impulse Response Folder
    　  Output Folder
      のフォルダのパスは変更可能です
