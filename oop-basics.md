%title: Object-Oriented Programming Basics
%author: yakup.arslan@eteration.com
%date: 06-26-2021

-> Yakup Arslan <-

-> Yazilim Gelistirici @eteration <-

-> [Github](https://github.com/arslanyakup) <-

-------------------------------------------------
-> ## Icerik <-

> 0. OOP
> 1. Class
> 2. Object
> 3. Stateful - Stateless Objects
>> 0. Stateful
>> 1. Stateless
> 4. Constructor
> 5. This
> 6. Encapsulation
> 7. Access Specifiers
> 8. Get/Set Methods
> 9. Static
>> 0. Static variables
>> 1. Static methods
> 10. Final
>> 0. Final class
>> 1. Final local variable
>> 2. Final instance variable
>> 3. Final method
> 11. Interface
> 12. Inheritance
> 13. Polymorphism
> 14. Overriding
> 15. Overloading
> 16. Abstract Class-Method
> 17. Super
> 18. java.lang.Object


-------------------------------------------------
-> ## 0. Object-Oriented Programming <-

> Bir seyin haritasini/modellemesini cikarmak, bir seyi soyutlamak.

> Birden fazla nesnenin birbirleriyle iletisime gecerek gercek hayattaki bir problemi cozmesine yarayan bir sistematiktir.

> Hedef karmasikliklarin ustesinden gelmek.

-------------------------------------------------
-> ## 1. Class <-

> Nesne yonelimli programlamanin temelini siniflar olusturur.

> En basit haliyle bir seyin seklini ve dogasini soyutlamamizi saglar.

> Nesne uretim fabrikasi.

> Pokemon sinifi olusturup soyutlamayi hedeflersek:
>> Uzunluk, agirlik, isim, yetenek gibi ozellikleri, degiskenleri olacaktir.
>> Saldiri, Savunma, Hizlanma gibi davranislari olacaktir.

> ( *Vehicle* )

-------------------------------------------------
-> ## 2. Object <-

> Sinifin ete kemige burunmus halidir.

> Soyut olan sinifin somut ozelliklerini ifade edebilmemize yarar. 

> Nesnelerin ozellikleri ve davranislari vardir (degiskenler ozelliklerini, metotlar ise davranislarini belirler.)

> ( *handbrake*, *color* )

-------------------------------------------------
-> ## 3. Stateful - Stateless Objects <-

## 0. Stateful

> Olusturulan nesnenin alanlarini elinde tutan ve bu degerleri bir surece bagli olarak isleyen nesnelerdir. get/set metodlari bulunur ve bu da nesnenin ozelliklerine erisimi anlik mumkun kilar.
>> t aninda olusturulan bir nesnenin alanlarina erisebilirim. (Hafizada yer tutuyorum) O alanlari baska degerlerle degistirebilirim ve bu alanlar ile bir metot uzerinden cikti uretebilirim.

```
  calculator.setFirst(10);
  calculator.setSecond(20);
  int result = calculator.add();
```

## 1. Stateless

> Olusturulan nesnenin alanlari uzerinde bir degisiklik yapmayan, anlik girdilerinizi verip direk cikti uretebildiginiz metodlara sahip olan nesnelerdir. 

> Bu tur nesneler hafizada yer tutmazlar. Bundan dolayi daha sonra bu degerlere erisiminiz mumkun degildir.

> Nesne alanlarina direk mudahale istenmediginden get/set metodlarina ihtiyac duymazlar.
>> Metodlar ihtiyaclari olan veriyi parametre olarak alirlar.

```
  public int add(int first, int second) {
    int result = first + second;
    return result;
  }
```

-------------------------------------------------
-> ## 4. Constructor <-

> Nesnelere olusturulduklarinda kendilerini ilk kullanima hazirlama imkani saglar.

> Icinde bulunduklari sinifla ayni isme sahiptir ve sozdizimi olarak metotlara benzerler. 

> Donus tipleri yoktur ancak bir sinifin yapilandiricisi aslinda o sinif tipinde kapali bir donus tipi saglar.

> Yalnizca yeni nesne olustururken ve new anahtar kelimesi ile cagrilirlar.

> Constructor'i olmayan bir sinif olamaz! Default constructor yazmasak bile kendiliginden olusturulur.

-------------------------------------------------
-> ## 5. This <-

> Herhangi bir metot icinde gecerli nesneye referansta bulunmak icin kullanilir.

> O anki nesne referansiyla nesnenin bir alanina veya metoduna erisim saglanabilir.

> Set metodlari ve parametre alan constructorlar this kullanimina ornektir.

```
  public Box(double width, double height, double depth) {
		this.width = width;
		this.height = height;
		this.depth = depth;
	}
```

-------------------------------------------------
-> ## 6. Encapsulation <-

> Bir class'in ic yapisinin disaridan korunmasi olarak dusunulebilir. 

> Disariya acilma yalnizca belirledigimiz guvenli metotlar seviyesinde olacagindan ic mekanizma daima korunacaktir. 

> Özetle: Ne yaptigini bilmeniz yeterlidir. Nasil yaptigiyla ilgilenmezsiniz. Bir sozlesmeye uyum da denilebilir.

> Low Coupling + High Cohesion (Her sinif kendi ic yapisini iyi bilmeli ancak disarida olan bitenle cok ilgilenmemelidir.)

-------------------------------------------------
-> ## 7. Access Specifiers <-

> Bagimliligi dusuk tutmak ve birbiriyle alakaliligi yuksek tutmak amaciyla kullanilir.

> Hedef encapsulation saglamak.

> Javanin erisim belirtecleri, public, private ve protected'dir.

## public 
> Bir sinif uyesi public olarak belirtildiginde programin tum kodu tarafindan bu uyeye erisilebilir.

## private 
> Bir sinifin uyesi private olarak belirtildiginde, ona sadece kendi sinifinin diger uyeleri erisebilir.

## protected
> Bir sinifin uyesi protected olarak belirtildiginde, ona sadece bulundugu paket icerisindeki sinif uyeleri ve bu siniftan turetilmis alt sinif uyeleri erisebilir.

```
  private double width;
  public double height;
  double depth;
```

> Eger bir erisim belirteci kullanmazsaniz varsayilan haliyle o uye default'tur. Kendi paketi disinda erisilemez.

-------------------------------------------------
-> ## 8. Get/Set Methods <-

> Kapsullenms bir sinifin uye degiskenlerine erisim icin gereklidir.

> Kisaca nesnenin durumuna ulasmak veya bu durumu degistirmek istedigimiz durumlarda kullanilir.

```
  private double width;

  public void setWidth(width){
    this.width = width;
  }

  public double getWidth(){
    return width;
  }
```

> Üye degiskenler disariya bagimliligi azaltmak icin private olmali. Eger public yaparsak disariya bagimliligimiz artacaktir. (Low Coupling)

-------------------------------------------------
-> ## 9. Static <-

> Kendi sinifinin nesnelerinden bagimsiz olarak kullanilabilecek sinif alanlarina ihtiyac duyulan anlarda kullanilir.

> Tum nesnelerin ortak ozelligi ya da ortak durumunu temsil eder.


## 0. Static variables
> Sinif degiskenleridir. (class variable) Bu baglamda kapsami da tum siniftir.

> Statik olarak belirtilen bir degiskene sinifindan hicbir nesne olusturulmadan ve hicbir nesneye referans olmadan erisilebilir. Nesne uzerinden de erisilebilir ancak boyle bir kullanim nesne degiskeni izlenimi verecektir.

## 1. Static methods

> Yalnizca diger statik metotlari cagirabilirler.

> Yalnizca statik veriye erismelidirler. 

> this veya super anahtar sozcuklerini kendi iclerinde kullanamazlar. (nesne yoksa this'te yok!)

> Main metotlar her zaman sinif uzerinde ilk cagirilan metotlardir. cagirilmak icin bir nesneye veya tetiklemeye ihtiyac duymazlar.
```
  public static void main(String[] args) {}

  public static void main(String[] args) {
		SpringApplication.run(InformationApplication.class, args);
	}
```

> Nesne metotlarindan static degiskenlere/metotlara erisilebilir.

-------------------------------------------------
-> ## 10. Final <-

> Bir uyeyi final yapmak o uyenin degistirilemez olmasini saglar.

> Java'da 4 farkli final keyword kullanim sekli vardir:

## 0. Final class
>> Bir class final olarak tanimlanirsa bu class'in kalitilmasi engellenir.

## 1. Final local variable
>> Bir metot icerisinde tanimlanan final degiskenlerdir. Scope'u yalnizca o metottur ve o metot icerisinde degistirilemez.

## 2. Final instance variable
> Bir final degisken olusturuldugunda muhakkak ilk deger atamasi yapilmasi gereklidir. Bunu yapmanin 2 yolu vardir:
>> 1. Ilk olusturma esnasinda bir deger verilebilir.
>> 2. Bir constructor icerisinde bir deger verilebilir.

## 3. Final method
> Bir metot final olarak tanimlanirsa, icinde bulundugu sinif kalitilsa bile bu metot override edilemez.

-------------------------------------------------
-> ## 11. Interface <-

> Aslinda bir cesit sozlesme. Bu sozlesmeyi imzaliyorsan bu metodlari kendi bunyende barindirmalisin.

> Sinifin nasil yapacagini degil ne yapacagini belirtirler. 

> Metotlar govdesiz olarak olusturulur.

> Metot iceriginin ne olacagiyla ilgilenmeden onlari tanimlayabileceginiz anlamina gelir.

> Bir sinif birden fazla interface implementasyonunu barindirabilir.

> Bir interface'i sinifa implemente etmek icin sinifin interface uzerinde eklenmis olan tum metotlari uygulamasi gerekir.

> Interfaceler uzerinde degiskenler de tanimlanabilir. Bu degiskenler varsayilan olarak static ve final olacaktir. Yani uygulanan siniflar tarafindan degistirilemezler.

> Interface metotlari public olmak zorundadir.

> Interface referans degiskeni ile implemente edilen class nesnesi olusturabilirsiniz.
```
  InterfaceA aObj = new Clazz(); (Clazz sinifi InterfaceA'yi implemente eder)
```

-------------------------------------------------
-> ## 12. Inheritance <-

> Kalitim, iliskili ogelerin ortak ozelliklerini tanimlayan genel bir sinif olusturmayi saglayan bir yapidir.

> Java'da kalitim yoluyla alinan sinifa ust sinif, kalitimi alan sinifa da alt sinif denir. Bu baglamda bir alt sinif, ust sinifin daha ozellesmis bir versiyonudur.

> Java'da *extends* anahtar kelimesi ile kalitim alinir.

> Alt sinif ust sinifin tum public ve protected uyelerine erisebilir.

> Constructorlar alt sinif tarafindan devralinamazlar.

> Java coklu kalitimi desteklemez!
>> class A extends B, C --> Compile time error!

-------------------------------------------------
-> ## 13. Polymorphism <-

> Inheritance ile elde edilen overriding ozelligi uzerine kuruludur. 

> Bir ust sinif uzerinden edinilen metodu override eden bir cok sinif olabilir. Tum bu siniflarin o metodu override etmesi polymorphism ornegidir. 

> Polymorphism, turevlerinin tumu ortak olan metotlar tanimlamak icin genel bir sinif saglar. 

-------------------------------------
-> ## 14. Overriding <-

> Üst siniftaki bir metot alt siniftaki bir metotla ayni ada ve donus tipine sahipse ustteki metot gizlenir.

> Ezilen metot calistirildiginda her zaman alt siniftaki metot calistirilir.

```
  class A {
    void show(){
      System.out.println("Show running on class B");
    }
  }


  class B extends A {

    // overriding method
    void show(){
      System.out.println("Show running on class B");
    }
  }
```

-------------------------------------
-> ## 15. Overloading <-

> Parametre tanimlamalari farkli olmak uzere ayni sinifta ayni isimde iki ya da daha fazla metot tanimlanabilir. Bu durum metodun overload edilmesidir.

> Overload bir metot cagrildiginda Java hangi metotun cagrildigina karar vermek icin gecilen parametrelerin tipine ve sayisina bakarak karar verir. Bundan dolayi overload metotlarin parametre tipleri veya sayilari farkli olmasi gerekir.

> Farkli donus tiplerine sahip olabilirler.
```
  class OverloadDemo {
    void test(){
      System.out.println("No parameters!");
    }

    void test(int a){
      System.out.println("a: " + a);
    }

    void test(int a, int b){
      System.out.println("a: " + a + " b: " + b);
    }

    void test(double a){
      System.out.println("double a: " + a);
    }
  }
```

> cagri parametreleri ve metot parametreleri tam uyumlu olmayabilir. Bu gibi durumlarda Java otomatik tip donusumu gerceklestirir. (Math.abs metotlari)

> Constructorlar da overload edilebilir.

-------------------------------------------------
-> ## 16. Abstract Class-Method <-

> Her metotun implementasyonuna ihtiyac duymadan verilen bir ozetlemenin yapisini tanimlayan bir ust sinif ihtiyacinda kullanilir.

> Icerigin alt sinif tarafindan doldurulacagi bir form gibi dusunulebilir.

> Abstract classlar icerisinde govdeli ya da govdesiz metotlar barindirabilir.

> Abstract classlarin new ile yeni bir nesnesi olusturulamaz. cunku ozet bir sinif tam olarak tanimlanmamistir. Kendi basina pek bir sey ifade edemezler. 

```
  abstract class A {
    abstract void callMe();

    void callMeToo() {
      System.out.println("CallMeToo is running!");
    }
  }

  class B extends A {
    @Override
    void callMe() {
      System.out.println("callMe from B Class!");
    }

    public static void main(String[] args) {
      B b = new B();
      b.callMe();
      b.callMeToo();
      b.setClassName("abstraction using from B");
    }
  }
```

-------------------------------------------------
-> ## 17. Super <-

> Bir alt sinifin ust sinifin constructor'ini cagirmasini saglar.

> Bir ust sinifin, bir alt sinifin degiskeni tarafindan gizlenen bir degiskene erismek icin kullanilir.

```
	public BoxWeight(double width, double height, double depth, double weight) {
		super(width, height, depth);
		this.weight = weight;
	}
```

-------------------------------------------------
-> ## 18. java.lang.Object <-

> Butun java siniflari Object sinifini kalitirlar. Yani Object sinifi tum diger siniflarin ust sinifidir. 

> Object sinifi bir ust sinifa sahip degildir.

```
  class Box {} ───────► class Box extends Object {}
```

-------------------------------------------------

-> ## Kaynakca <-

-> [Java ile Nesne-Merkezli Programlamaya Giris - Akin Kaldiroglu](https://www.udemy.com/course/java-ile-nesne-merkezli-programlamaya-giris/) <-
-> [Java SE - Herbert Schildt](https://www.alfayayinlari.com/kitap.php?id=234917) <-
