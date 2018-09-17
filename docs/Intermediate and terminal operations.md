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
