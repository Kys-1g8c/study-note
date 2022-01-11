
# 継承
  元となるクラス（スーパークラス）のメソッド、変数を引き継いだクラスを作ることができる。

  ```Java:Car.java
  public class Car {
    String carName;
    int weight;
    int maxSpeed;

    accelerator(){
    }

    brake(){
    }
  }
  ```
  `Car.java`に新たな機能を追加した`SuperCar.java`を作りたい。  
  コピペをして新たな機能を追加することでも解決できるが、以下のような問題がある。
  
  - 追加、修正に手間がかかる  

    `Car.java`に新たなメソッドが加わったときに`SuperCar.java`にも追加しなければいけなくなる。

  - 管理が大変になる
  
    `SuperCar.java`以外に、`Car.java`をもとにした別のクラスを作る場合、`Car.java`に変更がある度に同じ修正をそれぞれに行わなければいけない。

  以上の点からコピペによる解決は複雑になればなるほ ど面倒になるため、良くない。  
  そこで、継承を使う。

  `Car.java`を継承した`SuperCar.java`
  ```Java:SuperCar.java
  public class SuperCar extends Car {
    // 親クラスとの差分となる変数
    String carName = "SuperCar";

    // 新たに追加したメソッド
    turbo(){
    }
  }
  ```
  ※ソース上には、`Car.java`の変数、フィールドは書いていないが、引き継がれているため使うことができる。

  このように継承を使うことで、シンプルに書くことができる。
  <br>
  <br>

  ## オーバーライド
  

  ## 継承、オーバーライドの禁止
  クラス宣言に`final`をつけることで継承を禁止することができる。



  ## 抽象クラスとは


