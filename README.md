# mic22
## آزمایش شماره پنج : ساخت یک پیانو با استفاده از پیزو 

### هدف 

در این آزمایش به دنبال آن هستیم که به کمک قطعه <strong>پیزوالکتریک</strong> یک پیانو کوچک که دارای 4 عدد نت موسیقی می باشد بسازیم به طوری که بتوان با فشار دادن هر کلید یک نت آن را پخش کرد.

---

### مواد و وسایل مورد نیاز 

بردبورد	یک عدد
2	برد آردوینو UNO	یک عدد
3	سیم جامپر	یازده عدد
4	کابل USB	یک عدد
5	پیزو الکتریک	یک عدد
6	push button	چهار عدد
### توضیحات کلی 

در آزمایش قبلی نت ها خودشان به طور متوالی پخش می شدند اما در این آزمایش 4 نت موسیقی تعیین می کنیم و برای هر نت یک کلید قرار می دهیم به طوری که با فشار دادن هر کلید، نت موسیقی مرتبط به آن از طریق پیزو پخش شود.

---

### سورس کد 

```cpp
#define T_C 262
#define T_D 294
#define T_E 330
#define T_F 349
#define T_G 392
#define T_A 440
#define T_B 493

const int C = 10;
const int D = 9;
const int E = 8;
const int F = 7;
//const int G = 6;
//const int A = 5;
//const int B = 4;

const int Buzz = 11;

void setup() {
  pinMode(C, INPUT);
  digitalWrite(C, HIGH);

  pinMode(D, INPUT);
  digitalWrite(D, HIGH);

  pinMode(E, INPUT);
  digitalWrite(E, HIGH);

  pinMode(F, INPUT);
  digitalWrite(F, HIGH);

  //pinMode(G,INPUT);
  //digitalWrite(G,HIGH);

  //pinMode(A,INPUT);
  //digitalWrite(A,HIGH);

  //pinMode(B,INPUT);
  //digitalWrite(B,HIGH);
}

void loop() {
  while (digitalRead(C) == LOW)
    tone(Buzz, T_C);

  while (digitalRead(D) == LOW)
    tone(Buzz, T_D);

  while (digitalRead(E) == LOW)
    tone(Buzz, T_E);

  while (digitalRead(F) == LOW)
    tone(Buzz, T_F);

  //while(digitalRead(G)== LOW)
  //tone(Buzz,T_G);

  //while(digitalRead(A)== LOW)
  //tone(Buzz,T_A);

  //while(digitalRead(B)== LOW)
  // tone(Buzz,T_B);

  noTone(Buzz);

}
```



---


### توضیحات شماتیک مدار 

<ol>
<li>
اتصالات پیزو
<ul>
<li>یک پایه به پین 8 آردوینو</li>
<li>یک پایه به پین Gnd آردوینو</li>
</ul>
</li>
<li>
اتصالات کلیدها
<ul>
<li>یک پایه به پین Gnd آردوینو</li>
<li>یک پایه به ترتیب به پین های 1 تا 4 آردوینو</li>
</ul>
</li>
</ol>

---

### نتیجه گیری

با داشتن کلید های بیشتر می توان نت های موسیقی بیشتری را تنظیم کرد تا بتوانیم یک ساز موسیقی کامل بسازیم.
