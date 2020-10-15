# if文をマスターしよう3
m.oba

---

前回の復習

>>>

elseはif文の条件でないときに処理を実行してくれる命令です

>>>

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

>>>

```c
if(条件){
  条件がTrueのときに実行される;
}else{
  条件がFalseのときに実行される;
}
```

---

では1から10までの内，3の倍数のときはその数字を，5の倍数の時もその数字を，それ以外の数字の時は＊を表示させるにはどうすれば良いでしょうか？

>>>

前回と違うところは3の倍数に加えて5の倍数を表示できるようにならないといけないところですね

>>>

こんなときにはelse ifを使います．

>>>

else if を使うとある条件Aを満たさないかつある条件Bを満たす時に処理を実行することができます

>>>

```c
int main(void){
  for (int i=1; i<=10; i++){
    if (i%3==0){
      printf("%d\n", i);
    }else if(i%5==0){
      printf("%d\n", i);
    }else{
      printf("*\n");
    }

    return 0;
  }
}
```

>>>

```c
if(処理を実行するときの条件A){
  条件AがTrueのときに処理される;
}else if(処理を実行するときの条件B){
  条件BがTrueのときに処理される;
}else{
  条件Aも条件BもFalseのときに実行される
}
```

>>>

```c
int main(void){

  for (int i=1; i<=10; i++){

    if (i%3==0){
      // i%3==0がTrueのとき（つまりiが3の倍数のとき)に実行される
      printf("%d\n", i);
    }else if(i%5==0){
      // i%5==0がTrueのとき（つまりiが5の倍数のとき)に実行される
      printf("%d\n", i);
    }else{
      // i%3==0とi%5==0がFalseのとき（つまりiが3の倍数でも5の倍数でもないとき)に実行される
      printf("*\n");
    }

    return 0;
  }
}
```

---

問題

>>>

FizzBuzz問題<br>
1から100までで3の倍数のときFizz，5の倍数のときBuzz，3の倍数かつ5の倍数のときにFizzBuzzと表示させ，それ以外の数字の時はその数字を表示するプログラムを作れ

---

解説

>>>

```c
int main(void){
  for(int i=1; i<=100; i++){
    if (i%3==0 && i%5==0){
      printf ("FizzBuzz\n");
    }else if (i%3==0){
      printf("Fizz\n");
    }else if(i%5==0){
      printf("Buzz\n");
    }else{
      printf("%d", i);
    }
  }

  return 0;
}
