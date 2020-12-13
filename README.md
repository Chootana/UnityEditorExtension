# All Every Rotation Constraint (AERC)
**階層構造のあるゲームオブジェクトにRotation Constraintを簡単に追加・設定するためのエディタ拡張**

ソース（コピー元）のゲームオブジェクトとターゲット（コピー先）のゲームオブジェクトを指定すると，ターゲットの子オブジェクトそれぞれに対して，

    1. 対応するゲームオブジェクトにAdd Component (Rotation Constraint)する
    2. Is Active を On にする
    3. Constraint Settingsに同じ階層に存在するソースオブジェクトのTransformを追加する

を繰り返し行ってくれる．

# How to Use
アバターにサブアームと装着することを例とする．

今回はサブアームを導入は既に済んでおり，腕の関節それぞれにRotation Constraintを追加して同期させたいとする．


（サブアーム導入方法は[コチラ](https://booth.pm/ja/items/2203578)をおススメします．）

<br />

1. まずUnityでUnityEditor_AERC.unitypackageをインポートする．
    - Assets直下にEditorディレクトリがあることを確認する．

2. インポート後，Unit上部のWindowタブにExtension Toolsが表示されるようになり，その下のAdd Every Rotation Constraintをクリックする．
![Window/ExtensionTools](https://user-images.githubusercontent.com/44863813/102009739-d7c23480-3d7c-11eb-83c4-d99650156c21.png)

- 項目の説明

    - Original Avatar: コピー元を指定する箇所
    - Target Abatar: コピー先を指定する箇所
    - GameObject(Joint): Rotation Constraintを追加したいゲームオブジェクトを指定する
    - Root Name: 指定したゲームオブジェクトの最上層の親の名前が表示される
    - Number of Joints: 指定したゲームオブジェクトとその子オブジェクトの数が表示される

    ![Explanation/Window](https://user-images.githubusercontent.com/44863813/102009753-fc1e1100-3d7c-11eb-9ba6-ec54bcbb8715.png)


3. Original Avatarの方にコピー元となる腕（例えば本体アバターのSoulder.L）を，Target Avatarの方にコピー先となる腕（例えばサブアームのSoulder.L）をそれぞれに指定する．
    - この時Number of Jointsの値が一致しているか確認する．
    - もし一致していなかったら対応していないゲームオブジェクトが含まれているので，そのオブジェクトを非アクティブにする
4. **Copy**ボタンをクリックすると，Target Avatar側のゲームオブジェクト（及び子オブジェクト）にRotation Constraintが追加・設定される
5. **Reset**ボタンをクリックすると，Target Avatar側のゲームオブジェクト（及び子オブジェクト）に存在するRotation Constraintが削除される
![Explain/AddGameObjectAndRun](https://user-images.githubusercontent.com/44863813/102009789-34bdea80-3d7d-11eb-8e02-c603ab1289d5.png)

# Examples of Use
VRChat用のアバター改変をする時に，以下のような作業が簡単になる！

- 頭にアバターを追加し，両腕を本体と同期させる
- サブアームの追加する
- アバターのフルトラッキング適正向上（後日追記）
- 複数アバターのアニメーションを同期させる

などなど
![Result](https://user-images.githubusercontent.com/44863813/102007590-d2112280-3d6d-11eb-9870-5ca335b6973c.png)

善きVRChatライフを！

# Notes
説明のため[ロポリこんちゃん](https://mido0021.booth.pm)，[稲荷原](https://booth.pm/ja/items/2297510)，[メカアーム](https://booth.pm/ja/items/1221319)を使用するが，本製品に含まれていない．

# Author
chootana (ちゅーたな)

twitter: [@choo_zap](https://twitter.com/choo_zap)

# License

AERC is released under the [MIT license](https://opensource.org/licenses/mit-license.php).