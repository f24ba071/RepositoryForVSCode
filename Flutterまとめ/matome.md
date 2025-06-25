# Flutterまとめ Chapter2
## 2-1プロジェクト構成p50
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
## アプリ画面とウィジェットツリー
- ウィジェット
    - 画面表示を作成する際の部品、
- ウィジェットツリー
    - ウィジェットの組み込み構造
## アプリ実行の仕組み
```
import package:flutter/material.dart
```
上記のコードはFlutterのマテリアルデザインによるアプリのUIウィジェットがまとめられているパッケージ。
最初にこれを`import`しておく。
```
void main() {
    runApp(ウィジェット);
}
```
「main関数で、runAppでアプリを起動する」という意味

## StatelessWidgetクラスについて
```
class クラス名 extends StatelessWidget {

    @override
    Widget build(BuildContext context) {
        return MaterialApp(....略....);
    }
}
```
MyAppというクラスのインスタンス
これは、「StatelessWidget」というクラスのサブクラス  
`return`で「MaterialApp」というクラスのインスタンスが返されている。・・・マテリアルデザインのアプリを管理するクラス  
### ・StatelessWidgetでMaterialAppインスタンスを`return`することでマテリアルデザインによるアプリが表示される  

すべてのウィジェットは、Widgetというクラスのサブクラスとして用意されていて、このWidgetのサブクラスのインスタンスを生成し、MaterialAppに組み込んで`return`すると、StatelessWidgetクラス（MyAppクラス）のウィジェットとして画面に組み込まれ表示される  
## MaterialAppクラスについて
引数に様々な設定情報を指定することができる  
```
return MaterialApp(
    title:'Flutter Demo',
    home: Text(
        'Hello, Flutter World!!',
        style: TextStyle(fontSize:32.0),
    ),
);
```
上記のコードは、MaterialAppクラスのインスタンスを作成し`return`するもの  
titleとhomeという2つの名前付き引数が用意されている  
`title`が、アプリケーションのタイトル  
`home`が、アプリケーションに組み込まれるウィジェットを示している  

### アプリの構造
1. アプリケーションは、main関数として定義する。このmain関数では、runAppでウィジェットのインスタンスを実行する
1. runApp関数では、StatelessWidget継承クラスのインスタンスを引数に指定する
1. StatelessWidgetr継承クラスにはbuildメソッドを用意する。ここで、マテリアルでアインのアプリクラスであるMaterialAppインスタンスを`return`する。
1. MaterialAppの引数homeに、実際にアプリ内に表示するウィジェットを設定

## マテリアルデザインについて
・Googleが提唱する視覚的デザイン言語  
・あらゆるデバイスで共通したルック＆フィールを構築し、同じようなユーザー体験を実現するものとして提唱されている。  

## ScaffoldとAppBar
```
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Hello Flutter!'),
        ),
        body: Text(
          'Hello Flutter World!!',
          style: TextStyle(fontSize:32.0),
        ),
      ),
    );
  }
}
```
### Scaffoldについて
MaterialAppのhomeに`Scaffold`というクラスのインスタンスが指定されている。Scaffoldというのは、建築の「足場」のこと  
Scaffoldは、アプリ作成の土台となる部分を担当する部品。これには**マテリアルデザインの基本的なデザインとレイアウト**が組み込まれている  

Scaffoldは、以下のようにしてインスタンスを作成します。
