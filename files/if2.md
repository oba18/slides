# if文をマスターしよう2
m.oba

---

前回の復習

>>>

if文を使うとある条件のときのみ実行する処理をを実現することができます

>>>

```c
int main(void){

  for(int i=0; i<=10; i++){
    if( i%3==0){
      printf("%d\n", i);
    }
  }

  return 0;
}
```

>>>

```c
if (処理を実行するときの条件){
  条件がTrueの時に実行する処理;
}
```
この()の中身がTrueの時にif文の中身が実行されます．

---

では1から10までの内，3の倍数のときはその数字を，それ以外の数字の時は＊を表示させるにはどうすれば良いでしょうか？

>>>

こんなときはelseを使いましょう

>>>

elseはif文の条件でないときに処理を実行してくれる命令です

---

```c
int main(void){

  for(int i=1; i=<10; i++){

    if (i%3==0){
      printf ("%d\n", i);
    }else{
      printf ("*\n");
    }

  }

  return 0;
}
```

---

解説

>>>

```c
if(条件){
  条件がTrueのときに実行される;
}else{
  条件がFalseのときに実行される;
}
```

>>>

```c
int main(void){

  for(int i=1; i=<10; i++){

    if (i%3==0){
      // i&3==0がTrueのとき(3の倍数のとき)に実行される
      printf ("%d\n", i);
    }else{
      // i&3==0がFalseのとき(3の倍数でないとき)に実行される
      printf ("*\n");
    }

  }

  return 0;
}
```

---

問題

>>>

キーボードから数字を1つ入力して10以上なら「10以上です」，10以下なら「10以下です」と表示するプログラムを作りなさい

>>>

1から100までの好きな数字を入力して，60点以上なら「合格です」と，60点以下なら「あと◯点足りません」と表示するプログラムを作りなさい．

---

解答

>>>

```c
int main(void){
  int num;
  scanf("%d", &num);

  if (num>=10){
    printf ("10以上です\n");
  }else{
    printf ("10以下です\n");
  }

  return 0;
}
```

>>>

```c
int main(void){
  int num;
  scanf("%d", &num);

  if (num>=60){
    printf ("合格です\n");
  }else{
    printf ("あと%d点足りません\n", 60-num);
  }

  return 0;
}
```
