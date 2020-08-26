# for文をマスターしよう
m.oba

---

for文を使うと処理を繰り返すことができます

---

例えば，「1から10まで足したらいくつ？」  
という問題があったとします．

---

「1から10まで足したらいくつ？」   
for文を使わない場合なら

>>>

```c
int main(void){

  int total = 1;
  total = total + 2;
  total = total + 3;
  total = total + 4;
  total = total + 5;
  total = total + 6;
  total = total + 7;
  total = total + 8;
  total = total + 9;
  total = total + 10;

  return total;
}
```

---

じゃあ今度は1から10000まで足し合わせたら？？

>>>


```c
int main(void){

  int total = 1;
  total = total + 2;
  total = total + 3;
  total = total + 4;
  :
  :
  total = total + 9999;
  total = total + 10000;

  return total;
}

```

>>>

やってられない

---

ここでfor文を使います！！

>>>

```c
int main(void){

  int total = 0;
  for(int i=0;i<=10000;i++){
    total = total + i;
  }
  printf("%d",total);

  return 0;
}
```

---

for文の書き方  

```c
for (初期値;繰り返しを続けるか判定;増え方){
  処理;
}
```

>>>

初期値
```c
int i=0
```
`i`を使って処理を回す  
最初は定義なので，型宣言が必要

>>>

繰り返しを続けるか
```c
i<=10000
```
この部分がTrueなら処理を続ける  
例えばiが100なら10000以下なのでTrue  
そのため処理(ループ)を続ける

>>>

増え方
```c
i++
```
処理(ループ)を行ったときに，初期値として設定した`i`をどのように増やすか(処理をするか)  
```c
i++
i=i+1
i+=1
```
これらは全部同じ意味で，`i`に1足して`i`を更新するという意味

---

再掲
```c
int main(void){

  int total = 0;
  for(int i=0;i<=10000;i++){
    total = total + i;
  }
  printf("%d",total);

  return 0;
}
```

>>>

```c
int main(void){

  int total = 0;
  for(int i=0;i<=10000;i++){
    total = total + i;
//             0       0
  }
  printf("%d",total);
//                   0
  return 0;
}
```

>>>

```c
int main(void){

  int total = 0;
  for(int i=0;i<=10000;i++){
    total = total + i;
//             0       1
  }
  printf("%d",total);
//                   1
  return 0;
}
```

>>>

```c
int main(void){

  int total = 0;
  for(int i=0;i<=10000;i++){
    total = total + i;
//             1       2
  }
  printf("%d",total);
//                  3
  return 0;
}
```

>>>

```c
int main(void){

  int total = 0;
  for(int i=0;i<=10000;i++){
    total = total + i;
//             2       3
  }
  printf("%d",total);
//                  5
  return 0;
}
```

>>>


```c
int main(void){

  int total = 0;
  for(int i=0;i<=10000;i++){
    total = total + i;
//49995000 10000
  }
  printf("%d",total);
// 50005000
  return 0;
}
```

---

# 問題

>>>

このように表示させるプログラムを作ろう
```
x  x^2  x^3
1   1    1
2   4    8
3   9    27
4   16   64
5   25   125
```

---

# 回答例

>>>

```c
int main(void){

  printf("x\tx^2\tx^3\n");

  for (int i=1;i<=5;i++){
    int n = i * i;
    int m = i * i * i;
    printf("%d\t%d\t%d\n",i,n,m);
  }

  return 0;
}
```
