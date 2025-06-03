# Flutterまとめ
### 2-1プロジェクト構成p50
### プロジェクトのファイル構成
>プロジェクトのフォルダ類
>>「.dart_tool」フォルダ・・・Dart言語が自動生成するファイル類を保管するところ。  
「.idea」フォルダ・・・IntelliJ IDEA開発ツールの設定情報。  
「build」フォルダ・・・ビルドして生成されるファイル類。  
「android」フォルダ・・・Androidアプリ生成に必要なファイル類  
「ios」フォルダ・・・iosアプリ生成に必要なファイル類  
「linux」フォルダ・・・Linuxアプリ生成に必要なファイル類  
「macOS」フォルダ・・・macOSアプリ生成に必要なファイル類  
「windows」フォルダ・・・windowsアプリ生成に必要なファイル類  
「web」フォルダ・・・Webアプリ生成に必要なファイル類  
「lib」フォルダ・・・ここにDartのスクリプトが保存される  
「test」フォルダ・・・ユニットテスト関連のファイル類

>プロジェクトのファイル類
>>.gitignore・・・Gitで利用するファイル  
.metadata・・・Flutterツールが利用するファイル  
.packages・・・利用しているパッケージ情報  
anarysis_options.yaml・・・Dartの分析に関するファイル  
flutter_app.iml・・・モジュール定義ファイル  
pubspec.lock・・・Pub(Dartのパッケージマネージャ)が利用するファイル  
pubspec.yaml・・・Pubが利用するファイル  
README.md・・・リードミーファイル
---
### アプリ画面とウィジェットツリー
- ウィジェット
    - 画面表示を作成する際の部品、
- ウィジェットツリー
