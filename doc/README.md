# ストーリー
## 1. インストール方法(ライセンス導入まで)
## 2. UML
## 3. シミュレーション全体の設計をするために使用するべき図の提案
## 4. エージェント設計のために使用するべき図の提案
## 5. 実践
## 6. 他にも便利なastah\*の使い方
## 7. 最近UMLに対して思ったこと
## 8. シミュレーションを合同で作成するときに何が重要か(自分なりに考えてみた)
## 9. まとめ




## 1.astah*のインストール(ラインセンス導入まで)
 * [astah*のインストール](https://github.com/ie-ModelingAndDesign/astah/issues/1)
 * [astah*にライセンスkeyをセットするまで](https://github.com/ie-ModelingAndDesign/astah/issues/2)
 * 起動確認

## 2.UML
###　UMLとは
#### `〇〇である` をたくさん!!
* UMLとは `Unified Modeling Language` の略である
* UMLとは日本語に訳すと、`統一モデリング言語`である
* オブジェクトモデリングのために標準化した`仕様記述言語`である
* グラフィカルな記述で抽象化したシステムのモデルを生成する`汎用性モデリング言語`である

************************

### 何の役に立つのか
* 共同開発者達のイメージの共有
* 教えを請うときプログラムの全体像を伝えるのにすごく便利(貴方は1人でなんでもできる完璧なプログラマですか？)
* 頭の整理をするのにはちょうど良い
* デザインパターンを理解するのに役立つ

きっちりとする必要はない(伝えるにはきっちり知っとく必要が…w)

要は伝われば良い

多分、使われる側が一番嬉しい

使う側は自分の言いたいことが伝わることが嬉しい(コスト？)

設計技法というより、表現方法の1つ

(オレオレで伝えるか、標準化されているやつで伝えるか)

************************

### UMLのダイアグラム(=線図)
#### 基本的には2種類に分けられる
 * 構造図
 * 振る舞い

#### 1. 構造図 
* クラス図
* オブジェクト図
* 合成構造図
* パッケージ図
* コンポーネント図
* 配置図


#### 2. 振る舞い図
* ユースケース図
* アクティビティ図
* ステートマシン図

#### 2.1 相互作用図
* シーケンス図
* コミュニケーション図
* 相互作用概要図
* タイミング図

************************

### 各ダイアグラムに対してのトピック(リンク)
#### クラス図(構造図)
 * [クラス図](https://github.com/ie-ModelingAndDesign/astah/issues/9)

#### オブジェクト図(構造図)
 * [オブジェクト図](https://github.com/ie-ModelingAndDesign/astah/issues/10)

#### 合成構造図(構造図)
 * [合成構造図](https://github.com/ie-ModelingAndDesign/astah/issues/11)
 
#### パッケージ図(構造図)
 * [パッケージ図](https://github.com/ie-ModelingAndDesign/astah/issues/12)

#### コンポーネント図(構造図)
 * [コンポーネント図](https://github.com/ie-ModelingAndDesign/astah/issues/13)

#### 配置図(構造図)
 * [配置図](https://github.com/ie-ModelingAndDesign/astah/issues/14)

#### ユースケース図(振る舞い図)
 * [ユースケース図](https://github.com/ie-ModelingAndDesign/astah/issues/15)

#### アクティビティ図(振る舞い図)
 * [アクティビティ図](https://github.com/ie-ModelingAndDesign/astah/issues/16)
 
#### ステートマシン図(振る舞い図)
 * [ステートマシン図](https://github.com/ie-ModelingAndDesign/astah/issues/17)

#### シーケンス図(振る舞い図-相互作用図)
 * [シーケンス図](https://github.com/ie-ModelingAndDesign/astah/issues/18)

#### コミュニケーション図(振る舞い図-相互作用図)
 * [コミュニケーション図](https://github.com/ie-ModelingAndDesign/astah/issues/19)
 
#### 相互作用概要図(振る舞い図-相互作用図)
 * [相互作用概要図](https://github.com/ie-ModelingAndDesign/astah/issues/20)
 
#### タイミング図(振る舞い図-相互作用図)
 * [タイミング図](https://github.com/ie-ModelingAndDesign/astah/issues/21)


#### フローチャートが好かれない理由
 * 表現力がしょぼい
 * 人間はフローチャートのように考えない(落としこむのにむしろコストがかかる?頭の整理には向いてる？)
 * メリット：読みやすい(=表現力を犠牲にしているから)
 * オブジェクト指向開発に向かない
 * 粒度がめちゃくちゃ荒いならレベルならok?(しかし、ユーザーストーリで十分?)
 * どういう時に使用するか?

#### 具体例：FizzBuzz問題
問題：1->100までカウントアップし、出力する。出力する数字が3の倍数なら「Fizz」、5の倍数なら「Buzz」、15の倍数なら「FizzBuzz」を代わりに出力

出力例

```
1
2
Fizz
4
Buzz
Fizz
…
14
FizzBuzz
16
…
98
Fizz
Buzz
```

##### ソースコードその1
```
#include <stdio.h>

int main(int argc, char **argv){
    int i;
    for (i = 1; i <= 100; i++){
        if (i % 3){
            if (i % 5)
                printf("%d\n", i);
            else
                printf("Buzz\n");
        }else{
            if (i % 5)
                printf("Fizz\n");
            else
                printf("Fizzbuzz\n");
        }
    }
    return 0;
}

```

#### ソースコードその2
```
#include <stdio.h>

int main(int argc, char **argv){
    int i;
    for (i = 1; i <= 100; i++)
        printf( i % 3 ? i % 5 ? "%d\n"   : "Buzz\n"
                      : i % 5 ? "Fizz\n" : "FizzBuzz\n", i);
    return 0;
}
```

#### ソースコードその3
```
#include <stdio.h>

int main(int argc, char **argv){
    char *fizzbuzz[15];
    int i;
    for (i = 1; i < 15; i++)    fizzbuzz[i] = "%d\n";
    for (i = 3; i < 15; i += 3) fizzbuzz[i] = "Fizz\n";
    for (i = 5; i < 15; i += 5) fizzbuzz[i] = "Buzz\n";
    fizzbuzz[0] = "FizzBuzz\n";
    for (i = 1; i <= 100; i++)  printf(fizzbuzz[i % 15], i);
    return 0;
}
```


## 3. シミュレーション全体の設計を「表現」するために使用する図の提案
 * アクティビティ図

## 4. エージェント設計を「表現」するために使用する図の提案
 * アクティビティ図


## 今回は最初にやるべきである、ユースケース図などは書かなくていいのか？

### 答え：書かなくていいと思う
 * シミュレータを提供する側になるのか、使用する側になるのか -> 両方(どっちかって言うと、使用する側メイン？)
 * `artisoc` はシミュレーション中にユーザの手出しが「プログラムの一時停止」「プログラムの停止」


## 5. やってみよう(手を動かそう)
#### お題「artisocで動かすシミュレーション自体の全体フローチャートを書こう」
#### [sample.modelのGist](https://gist.github.com/kanpe777/7740814)

 
1. Gistからsample.modelのダウンロード
2. artisocで開く
3. Run(確認)
4. astah*を開く
5. [Diagram] -> [Activity Diagram] -> [New Activity Diagram]
6. 作成
7. [Tool] -> [Export Image] -> [Save Diagram as PNG…]

## 6. 便利なastah*の使用方法
 * javaのコードから自動でクラス図を生成(頭の整理と人に見せる時、便利)




## 7. 発表のチャンスをいただく -> 勉強(INPUT) -> OUTPUT(なう) -> UMLに対して思ったこと
#### Before
 * UML勉強したいなー
 * UML覚えたら少しはプログラミングできるようになるかなぁ
 * プログラミング3,4とかでも使用されているしなぁ

#### After
 * 学習コスト,記述コスト
 * 読める技術は欲しい(デザインパターン)
 * フレームワーク等の勉強にすごく便利(頭の整理)
 * 最近流行っている開発方法との相性(アジャイル開発に適用しようと考えてみる)
 * 流行りではない, しかし会社での必要度はかなり高め？
 * 書けて当たり前？読めて当たり前？


## 8. シミュレーションをグループで作成するときに何が重要か(自分なりに考えてみた)
 1. 何をシミュレートをするか？
 2. そのシミュレーションで何を観察したいか？
 3. それを観察するにあたって「何が」必要か洗い出す
 4. 洗いだしたものを求めるのに何が必要か洗い出す
 5. 4を再帰し続ける？
 6. 実装
 7. シミュレート
 8. 観察できたか？他に観察したいものはないか？(あるなら2から繰り返す)
 9. 結果としてまとめる、考察する
 10. 発表
  
## 9. まとめ
 * あくまでそのグループで考えをきちんと共有するのに「便利」であるだけで、使用するか使用しないかはグループ毎でいいのではないか？(今回は授業なので勉強を兼ねてやってもいいかも)
 * むしろ、何を「シミュレートするのか」「何がしたいのか」「何を期待しているのか」とかのほうが良かったりしそう. . .
 * UMLはあくまで表現方法として使ったほうが良い。共通言語なので、意思は伝わりやすい。
