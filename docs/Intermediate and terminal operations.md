|Operation|Type|Return Type|Functional Interface|Function Descriptor|
|---|---|---|---|---|
|filter|Intermediate|`Stream<T>`|`Predicate<T>`|`T -> boolean`|
|distinct|Intermediate|`Stream<T>`|||
|skip|Intermediate|`Stream<T>`|long||
|limit|Intermediate|`Stream<T>`|long||
|map|Intermediate|`Stream<R>`|`Function<T, R>`|`T -> R`|
|flatMap|Intermediate|`Stream<R>`|`Function<T, Stream<R>>`|`T -> Stream<R>`|
|sorted|Intermediate|`Stream<T>`|`Comparator<T>`|`(T,T) -> boolean`|
|anyMatch|Terminal|boolean|`Predicate<T>`|`T -> boolean`|
|noneMatch|Terminal|boolean|`Predicate<T>`|`T -> boolean`|
|allMatch|Terminal|boolean|`Predicate<T>`|`T -> boolean`|
|findAny|Terminal|boolean|`Optional<T>`||
|findFirst|Terminal|boolean|`Optional<T>`||
|forEach|Terminal|void|`Consumer<T>`|`T -> void`|
|collect|Terminal|R|`Collector<T, A, R>`||
|reduce|Terminal|`Optional<T>`|`BinaryOperator<T>`| `(T,T) -> T`|
|collect|Terminal|long|||

1. Find all transactions in the year 2011 and sort them by value (small to high).
2. What are all the unique cities where the traders work?
3. Find all traders from Cambridge and sort them by name.
4. Return a string of all traders’ names sorted alphabetically.
5. Are any traders based in Milan?
6. Print all transactions’ values from the traders living in Cambridge.
7. What’s the highest value of all the transactions?
8. Find the transaction with the smallest value.

Here’s the domain you’ll be working with, a list of Traders and Transactions:
```java
Trader raoul = new Trader("Raoul", "Cambridge");
Trader mario = new Trader("Mario","Milan");
Trader alan = new Trader("Alan","Cambridge");
Trader brian = new Trader("Brian","Cambridge");
List<Transaction> transactions = Arrays.asList(
  new Transaction(brian, 2011, 300),
  new Transaction(raoul, 2012, 1000),
  new Transaction(raoul, 2011, 400),
  new Transaction(mario, 2012, 710),
  new Transaction(mario, 2012, 700),
  new Transaction(alan, 2012, 950)
);
```
Trader and Transaction are classes defined as follows:
```java
public class Trader{
  private final String name;
  private final String city;
  public Trader(String n, String c){
    this.name = n;
    this.city = c;
  }
  public String getName(){
    return this.name;
  }
  public String getCity(){
    return this.city;
  }
  public String toString(){
    return "Trader:"+this.name + " in " + this.city;
  }
}

```
```java
public class Transaction{
  private final Trader trader;
  private final int year;
  private final int value;
  
  public Transaction(Trader trader, int year, int value){
    this.trader = trader;
    this.year = year;
    this.value = value;
  }
  public Trader getTrader(){
    return this.trader;
  }
  public int getYear(){
    return this.year;
  }
  public int getValue(){
    return this.value;
  }
  public String toString(){
    return "{" + this.trader + ", " +
    "year: "+this.year+", " +
    "value:" + this.value +"}";
  }
}
```
