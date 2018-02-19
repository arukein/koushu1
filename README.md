まずは、何の機能もない、何もしないプログラムを作ることから始めます。

ところで、C言語のプログラムを作るのに、どんな知識が必要でしょうか？
何を作るにせよ、その構造を知らないと作ることは出来ないでしょう。
本棚を作るには本棚の構造を知っている必要がありますが、これはC言語でも同様なのです。

では、C言語の構造とは、一体どのような構造なのでしょうか？
機械を作るときは、様々な部品を組み合わせて作ります
同じように、プログラミングでも部品を組み合わせます。この部品のことを関数と呼びます。
つまり、C言語のプログラムは、関数が集まって作られているのです。

C言語プログラムの構造 
C言語のプログラムは、関数が集まって作られている。 

ここで注意することは、関数の並びではなく、関数の集まりという点です。
並びと言う場合、それは順番を持っていることになります。
しかし、集まりと言う場合、それには順番はありません。

C言語の関数には、1部の例外を除き、順番の概念が全くありません。
C言語のプログラムの構造は、様々な関数がひとかたまりになった構造で、
それぞれの関数は、好きな順番で使用することが出来ます。

## 関数の作り方

C言語のプログラムの構造は、関数の集合であることがわかりました。
すると、次に問題となるのは当然、関数の構造です。

C言語の関数は、非常に明確な構造を持っています。次が、C言語の関数の構造です。

`関数の構造 型名　関数名(引数)｛処理｝`

型名とは、関数が計算結果を返す時に使う数値の種類のことです。
ここでは、とりあえずint(イント)という型を覚えて下さい。
intとは、整数を意味しています。

関数名とは、文字通り、関数の名前のことです。
この名前のつけ方には、下のような決まりがあります。

名前の規則
 1、半角アルファベット、半角数字、半角＿(アンダーバー)が使える。
 2、1文字目には、数字を使うことは出来ない。
 3、あらかじめ決められた予約語は使用することが出来ない。 

予約語とは、C言語の中で使われているキーワードです。
ただし、この予約語の数は少ないので、あまり気にすることはありません。



引数とは、関数に渡す数値の種類のことです。
関数は、渡された数値を元に計算を行って結果を返すことが出来ます。
しかし、始めに述べたように、今回の目的は、何もしないプログラムを作ることです。
何もしないプログラムに、情報を渡す必要はないでしょう。
そこで、情報がないことを表す、void(ボイド)を使用することにします。

処理とは、その名の通りの処理のことです。
始めに述べたように、今回の目的は、何もしないプログラムを作ることなのですが、
今回、唯一しなくてはならない処理として、関数を終了させる処理があります。
関数を終了させるには、return(リターン)文を使用します。
なお、return文には計算結果の数値を返す機能があるのですが、
今回は何もしないプログラムなので、とりあえず0にしておきます。

以上のようにして、次のような関数が完成しました。

`int main(void) 

{

return 0;

}` 

________________________________________
## main関数


上記では、関数には順番は存在しないと説明しました。
しかし、これでは、1つ困ったことが起こってしまいます。
1番最初に、どの関数から目をつけていけば良いのか、迷ってしまいます。

C言語では、この問題を、非常にシンプルな方法で解決しています。
C言語では、mainという名前の関数が、1番始めに動作すると決められています。

main関数の意味
 C言語では、main関数が1番始めに動作する 

もし、プログラムの中にmain関数がどこにもなかった場合、
1番初めの関数がなくなってしまうので、そのプログラムは動作出来ません。
逆に言えば、main関数さえあれば、C言語のプログラムは動作出来るのです。

先ほど作成した関数は、名前がmainになっているので、
この関数があれば、プログラムを動作させることが出来ます。

________________________________________
これが、今回作成した、何もしないプログラムです。

 
int main(void) 
{
return 0;
}
 

 

何も表示されていないみたいです。今回の目標通りの結果になりました。



これから、画面に文字列を表示する方法を解説します。
それは、この後、色々な解説を行うのに、どうしても必要だからです。

プログラムで色々な処理をさせることは実は簡単なのですが、
それを人間にわかるようにするのは、意外と難しいことです。
何故なら、コンピュータ内部の処理は電気信号の流れでしかないからです。

しかし、幸いなことに、現在では、それが容易に実現出来ます。
コンピュータには、ディスプレイがついています。
ですから、処理の内容を、ディスプレイに表示させれば良いのです。

処理の内容が表示されないと、プログラミングの学習は成り立ちません。
プログラムが、何をやり、そしてどうなったのか、それがわからないからです。

従って、今後のプログラミング学習のためには、
どうしても、画面に文字列を表示する方法を学んでおく必要があります。
つまり、画面に文字列を表示させるのは、学習のための準備なのです。

________________________________________
## printf関数

C言語で文字列を表示するには、printf(プリントエフ)関数を使います。
printf関数は、次のようにして使います。

 
printf("文字列"); 

例えば、HelloWorldと表示させたい場合、次のようにします。

 
printf("HelloWorld"); 

この文をプログラムの中に書けば、画面に HelloWorld と表示されます。

ところで、この文は、一体どこに書けばいいのでしょうか？



________________________________________
どこに書くのか？

前項で説明した通り、printf関数を使えば、画面に文字が表示されます。
しかし、始めにも説明したように、C言語は、main関数から始まります。
つまり、printf関数だけでは駄目であり、必ずmain関数が必要です。

とりあえず、始めに作った、main関数のプログラムを思い出してみます。

 
int main(void) 
{ 
return 0; 
} 

C言語は、main関数から始まることは説明しましたが、
その関数の中で、どんな順番でプログラムが動くのかは説明しませんでした。

関数の中では、単純に、上の文から順番に動いていきます。
そして、return文に到達すると、そこで関数の実行は終了します。

例えば、次のようなプログラムがあったと仮定した場合、

 
int main(void) 
{
 文1;
 文2;
 return 0;
 文3;
 } 

プログラムは、文1->文2、という順番で動きます。
文3に到達する前に、return文で関数が終わるので、文3は無視されてしまいます。

このことから考えると、printf関数を書くべき場所がわかります。
つまり、次のように書けば良いことになります。

 
int main(void) 
{
printf("HelloWorld"); 
return 0; 
} 


________________________________________
## 疑似命令

上記で、printf関数を使ったプログラムは完成したはずなのですが、
実は、このプログラムは準備不足なので、動かしても画面に文字は表示されません。

実は、printf関数は、C言語自体の機能ではありません。
言い換えるならば、C言語のコンパイラは、printfという関数のことを全く知りません。
従って、ただprintf関数を記述しただけでは、動かないのです。
動作させるには、コンパイラにprintf関数の説明書を読ませなければなりません。

C言語には、説明書を渡すための特別な命令が用意されています。
それは、#include(インクルード)疑似命令です。
#include疑似命令は、次のようにして使うことが出来ます。

疑似命令 
疑似命令とは、プログラムコードではない命令のことです。 #includeはprintf関数などの準備をする命令なので、 この命令は機械語に翻訳されず、その前段階で処理されます。 

 
#include <説明書のファイル名> 

printf関数の説明書は、stdio.h と言うファイルです。
つまり、次のようなプログラムを追加すれば、printf関数を使えるようになります。

 
#include <stdio.h> 

ところで、この命令はどこに書けば良いのでしょうか？
プログラムの説明書を渡すのですから、プログラムが実行される前である必要があります。
プログラムが実行されてしまった後では、説明書を渡しても手遅れなのです。

このことから考えて、1番先頭(main関数よりも先)に書くのが良さそうです。
つまり、printf関数で画面に文字列を表示するプログラムは、次のようになります。

 
#include <stdio.h> 


int main(void) 
{ 
printf("HelloWorld"); 
return 0; 
} 

なお、#includeは疑似命令なので、関数の外側に書くことが出来ます。

これでやっと、画面に文字列を表示するプログラムが完成しました。

 
#include <stdio.h>


int main(void) 
{
printf("HelloWorld");
return 0; 
} 

このプログラムの実行結果は、次のようになります。

 
HelloWorld 



## 変数
変数とは、数値を保存しておくためのメモリ領域に名前をつけることです。
これ、ほとんどの入門書では、数値を入れておく箱と説明しますが、
コンピュータをそれなりに使っている人には、メモリと言った方がすっきりします。

変数の宣言

メモリに名前をつけて管理することは、上記で説明しました。
つまり、変数を使うには、その変数に名前をつけてやらなくてはいけません。

C言語では、変数に名前をつけることを、変数を宣言すると呼んでいます。
変数を宣言するには、次のような書き方を使います。

型名　変数名;
 
型名とは、記憶しておきたい数値の種類を表す名前です。
とりあえずは、整数を意味するintを覚えておいて下さい。

変数名とは、その名の通り、変数につける名前のことです。
この名前のつけ方には、下のような決まりがあります。
1、半角アルファベット、半角数字、半角_を使うことが出来る。 
2、1文字目には、数字を使うことは出来ない。 
3、あらかじめ決められた予約語も使用することが出来ない。 
これは、関数名の名前のつけ方と全く同じなのです。

これだけのことがわかれば、変数を宣言することが出来ます。
次のプログラムは、int(整数値)という型の変数valueを宣言しています。

 
#include <stdio.h> 
int main(void) 
{ 
int value; /* 変数宣言の部分 */ 
return 0; 
}
 
変数の宣言は、基本的に、関数の先頭でしか行うことが出来ません。
例えば、次のように変数を宣言することは出来ません。

 
#include <stdio.h> 


int main(void) 
{
printf("Hello\n"); 
int value; /* 変数宣言の部分 */ 
return 0; 
} 

このプログラムは、動作させるとエラーになります。
変数宣言の部分を先頭に持ってくれば、動作するようになります。


________________________________________
## 変数への値の代入

1度宣言した変数は、その範囲内では自由に使用出来ます。
今回はmain関数の中で宣言しているので、main関数の中では自由に使えます。

変数の使い方は2種類あります。その内の1つが、代入です。
代入とは、変数に数値を記憶させることを意味しています。


代入
 変数に数値を記憶させること。 

変数に数値を代入するには、次のような書き方を使います。

変数名 = 数値; 



________________________________________
## 変数を数値の代わりに使う

変数もう1つの使い方は、数値の代わりとして使うことです。
これに関しては、特にこれといった書き方があるわけではありません。
数式の中に変数名を書くと、その変数の記憶している数値に置き換わります。
数値の表示や計算など、今まで数式を使ってきた全ての場面で応用可能です。
次のプログラムは、変数に記憶された値を表示する例です。
 
#include <stdio.h> 


int main(void) 
{ 
int value; /* 変数宣言の部分 */ 
value = 10; /* 代入の部分 */ 
printf("%d\n",value); /* 表示の部分 */ 
return 0; 
} 

このプログラムの実行結果は、次のようになります。
 
10 






## scanf関数

画面に表示する時にprintf関数を使用したように、
キーボードから入力する時にも、その為の関数を使用します。
そのためにＣ言語には、scanf(スキャンエフ)関数が用意されています。
scanf関数は、次のようにして使います。

 
scanf("入力変換指定子",&変数名);
 
入力変換指定子とは、入力された数字をどのような数値に変換するかを表す文字です。
printf関数で使用した出力変換指定子と、ほぼ同じように使用出来ます。

変数名には、入力されたデータを記憶しておく変数名を指定します。
scanf関数を使う場合は、変数名の前に & の文字をつける必要があります。

この関数を実行すると、プログラムは入力待ち状態となります。
プログラムを使う人が、データを打ち込んでリターン(Enter)キーを押すと、
そのデータが指定した変数に代入されます。

なお、scanf関数を使用するには、#include <stdio.h> が必要です。
printf関数を使う時と同じなので、改めて追加する必要はありません。



## 数値の入力

これだけのことがわかれば、キーボードからデータを入力することが出来ます。
次のプログラムは、scanf関数を使用して入力された数値をそのまま表示する例です。

 
#include <stdio.h> 


int main(void) 
{
int data; scanf("%d",&data); /* 入力部分 */ 
printf("%d\n",data); 
return 0; 
}
 
このプログラムの実行結果の例は、次の通りになります。
弱く表示された文字列は説明用に書き加えた文で、実際には表示されません。
 
100　入力したデータ 
100　表示されたデータ 

このプログラムを実行すると、入力待ち状態になります。
そこで数値を入力し、リターンキーを押すと、その数値がそのまま表示されます。
当然、100 以外の数値でも構いません。
