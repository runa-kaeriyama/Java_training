## eclipsでのデバック方法

### デバッグ

バグの原因を調査し、修正することを「デバッグ」といいます。

- 「ブレークポイント」でプログラムを一時停止
- その時点の変数などの値を見たり、1行ずつなど動かして、プログラムの動作を見る
- どこで想定と違う動きとなるか、といった調査を行う

実際に使って値を確認してみましょう。

```java
int num = 5;
num = 10;

if (num == 5) {
     System.out.println("numは5です");
} else {
    System.out.println(num);
}
```
