## 型と変数

### 型と変数名の宣言

型を書いて変数を書きます。

```java
int hanakoAge;
```

これで、int型の`hanakoAge`変数が宣言できました。  `int`は、整数を扱う型なので`hanakoAge`は、整数を扱う変数となります。

### いい変数名　わるい変数名

変数名は、自由に付けることができます。ただし、以下のルールがあります。

- 予約後は使用できない。（`public, private, int, String...`)
- 先頭文字に数値は使えない。
- camelCase記法を使う
    - 英字小文字を使う
    - 言葉の区切りだけ大文字にする。

camelCase記法は、単語と単語を組み合わせて変数名に意味を持たせるようにします。

例 camelCase記法

- hanakoAge
- addStr
- sendFile
- isDaikichi

他にも単語と単語の間をアンダーバー"_"でつなげるsnake_case記法もあります。

例 snake_cace

- hanako_age
- add_str
- send_file
- is_daikichi

C++やHTMLではsnake_case記法で書かれます。  
JavaではcamelCase記法が推奨されているので、Javaでプログラムをするときは基本的にcamelCace記法で書いてください。

#### 変数名の命名

変数名は自由に付けれますが、**変数の目的に合った意味をもつように**名称を工夫しましょう。  
例えば、同じシステムの中で人、犬、猫を扱う事があるとして、変数名`hanakoAge`は、何を表す変数名でしょうか。はなこさんの年齢？はなこさんって人ですか？人だと思いこんで変数`hanakoAge`を使っていたら、実は犬用や猫用の変数かもしれません。  
`hanakoAge`と変数名を付けた私の意識としては、`hanakoAge`は犬です。我が家の愛犬の名前です。  
もう少し明確な変数名にするなら、`onePetDogHanakoAge`で一匹の飼い犬である花子の年齢って読めますかね。変数を使う範囲がもう少し幅広く犬なら使える変数であれば、`dogAge`とすれば犬の年齢です。  
`hanakoAge`は研修内だけで使う変数名であり、皆さんも`hanakoAge`は犬の年齢だと認識したと思いますので、このまま使います。

#### 変数名の長さ

変数名の長さについてですが、変数名は長くなるとタイピング数が増え、スペルミスの可能性が高くなります。しかしIDEの補完機能もありますし、コピペを使ってもいいので、変数名を短くすることにこだわるよりは、変数名で意味が通じる事に重点をおきましょう。
変数名の付け方は慣れもあるかと思いますが、他人のプログラムを見る時も変数名がどのように付けられているか意識して確認することで、ちょうどいい変数名を作れるようになっていきましょう。

### 初期化

初期化は以下のように記述します。

```java
int hanakoAge;

hanakoAge = 3;
```

変数の宣言と初期化は、同時に行うことができます。基本的には、初期化を忘れないためにも変数の宣言と初期化は同時にやりましょう。  
見た目もすっきりします。見た目は大事です。

```java
int hanakoAge = 3;
```

花子は、３歳なので`hanakoAge`の初期値として3を代入しました。
変数は更新が可能なので、`hanakoAge`を4で更新してみましょう。

```java
int hanakoAge;

hanakoAge = 3;

hanakoAge = 4;
```

これで初期化処理時は、`hanakoAge`に3を入れていましたが、同じ`hanakoAge`に4が入り更新されました。`hanakoAge`はint型なので、int型の数値であれば、再代入することが可能となっています。

確認する場合は、以下のコードを実行してみてください。

```java
public class JavaTraining {
    public static void main(String[] args) {
        // 変数の選言と初期化
        int hanakoAge = 3;
        System.out.println("初期化直後　花子の年齢 : " + hanakoAge);

        // 変数の更新
        hanakoAge = 4;
        System.out.println("再代入　花子の年齢 : " + hanakoAge);
    }
}
```

### プリミティブ型

型付きで変数を宣言することで、型に合わせてメモリ上に領域が確保されます。確保された領域を利用して様々な値や文字あるいは参照アドレスを保持する事ができるようになります。

基本データ型 一覧表

|種類|データ型の名前|説明|値の範囲
|:--|:--|:--|:--
|整数型|byte|8ビット整数|-128 ～ 127
|整数型|short|16ビット整数|-2,768 ～ 32,767
|整数型|int|32ビット整数|-2,147,483,648 ～ 2,147,483,647（約±21億）|
|整数型|long|64ビット整数|-9,223,372,036,854,775,808 ～ 9,223,372,036,854,775,807(約±900京）|
|浮動小数点型|float|32ビット単精度浮動小数点数|約(-)3.40282347E+38（約6～7桁の精度）|
|浮動小数点型|double|64ビット倍精度浮動小数点数|(-).79769313486231570E+388（15桁の精度）
|文字型|char|16ビットUnicode文字|\u0000 ～ \uFFFF
|論理型|boolean|真偽値|「true」 or 「false」
|文字列型|String|文字列|扱えるデータの長さはint型と同じ（約21億）

```java
int i;
```

int型で宣言すると、32bit分の領域が確保されます。

```java
int i = 5;
```

`i`に5を代入していますがコンピュータは２進数で認識するため、メモリ上で`i`には5が`101`で代入されます。
1bitで0か1を表現できるので、101は3bitの領域を使って5となります。

が、

int型で変数を宣言した時点で32bit分の領域が確保されたあとは、ずっと32bit分の領域を使って変数を取り扱います。
なので変数`i`に`5`を代入すると前に0をたくさんつけて表示します。

`00000000000000000000000000000101`が`int i = 5;`の`i`を32bitで表す情報です。
intの変数は、変数が使われている間は32bitの領域を確保しているので、32bit分の整数を代入可能な状態となっています。

```java
public class VariableTest {
    public static void main(String[] args) {
        int hanakoAge = 4;
        System.out.print("hanakoAge:");
        System.out.print(hanakoAge);
    }
}
```

[question_01](https://github.com/ktsuru-cw/Java_training/blob/master/Question/question_01.md)

---
