#　MSTest

## 概要
C＃でテストを行うライブラリの一つ。visual studioで作成可能

## 作り方
visual stdio 2017にて右クリック単体テストをクリックで作成可能（publicでないと自動で作成できない）
そのため、windows formを作る際は単体テストを意識してビジネスロジックを分離しておく必要がある。


## クラス
- テストエクスプローラは、クラスごとに分類されるため、クラスはテストしたい機能ごとに作る方が良さそう
- 

## メソッド
- メソッドの先頭にはTestMethod属性をつける必要がある。ない場合テスト実行されない。

## 判定方法
- 真偽判定
  trueを入れておけば絶対に成功するテストになる
```
Assert.IsTrue(a);
Assert.IsFalse(a);
```

- オブジェクトの判別
```
Assert.AreEqual(a, b);
```


## テストケース
各メソッドの先頭にDataRow属性をつけることで、メソッドの引数に値を渡すことができる。これによって様々なテストケースを実行可能
```
[TestMethod]
[DataRow(1, 1)]
[DataRow(1, 2)]
[DataRow(1, 3)]
public void testMethod(int a, int b){
    int result = calc.add(a, b);
    Assert.AreEqual(result, a + b);
}
```