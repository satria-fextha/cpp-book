# メモリ領域

プログラムが利用するメモリには様々な領域が存在します。ここでは、スタックとヒープについて紹介します。

## スタック

スタックはデータ構造上、ヒープに比べて高速に扱えます。スタックへのメモリの確保と解放はコンパイラ・OSが自動的に行います。

代わりに、使用できるスタックには限りがあるので、大きなデータを取り扱うのには向いていません。
また、スタックのサイズはプログラムのコンパイル・リンク時に決定しているので、実行前にメモリの確保期間が分かっているものに利用は限られます。

```cpp
void Function() {
    int x = 100; // ローカル変数xはスタックに確保される。
    int y = 200; // ローカル変数yはスタックに確保される。

} // 関数の終了とともに変数 x, y はスタックから取り除かれる。
  // スタックはLIFO（後入れ先出し）形式のため y, x の順で取り除かれる。

int main() {
    Function();

    return 0;
}
```

## ヒープ

ヒープのサイズはプログラム実行時に動的に変化します。ヒープはスタックのような制限がなく自由度が高いですが、アプリケーション側でメモリの確保と解放を行う必要があります。

メモリの確保期間が明確でない場合や、実行時にサイズが確定するようなものについてはヒープを利用します。例えば、 `std::vector` は、保持する要素をヒープ上に確保することで、要素数を実行時に変更できるという仕組みを実現しています。