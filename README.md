# stream-api-notes
Notes for Java Stream API

# Stream API
- Is used for processing collections and arrays.

### Stream API methods
- **filter**: will return all the values as long as condition is true.
```
Stream<T> filter(Predicate<T> condition)
```
- **map**: process each element and returns the processed element
```
R Stream<R> map(Function<T, R> mapper)
```
- **forEach**: process each element and returns void
```
void forEach(Consumer<T> consumer)
```
- **sorted**: sort the elements in natural order and specified comparator
```
Stream<T> sorted()
Stream<T> sorted(Comparator<T> comparator)
```
- **flatMap**: used for transforming and flattening of collection
```
Stream<T> flatMap(Function<Stream<T>> mapper)
```
- **count**: returns the size of processed collection
```
long count()
```
- **min**: will return the lowest value in the collection.
```
Optional<T> min(Comparator<T> comparator)
```
- **max**: will return the max value in the collection.
```
Optional<T> max(Comparator<T> comparator)
```
- **reduce**: will return the combined value of all the elements in collection
```
Optional<T> reduce(BinaryOperator<T> accumilator) 
```
- **peek**: used to see the elements while processing it.
```
Stream<T> peek(Consumer<T> action)
```
- **allMatch**: will return true if given condition match will all the elements.
```
boolean allMatch(Predicate<T> condition)
```
- **anyMatch**: will return true if any of the element match with the given condition.
```
boolean anyMatch(Predicate<T> condition)
```
- **noneMatch**: will return true if there no element match with the given condition.
```
boolean noneMatch(Predicate<T> condition)
```
- **findFirst**: returns the first element of stream
```
Optional<T> findFirst()
```
- **findAny**: will pick random values in stream elements.
```
Optional<T> findAny()
```
- **limit**: will limit the element that can be process in stream
```
Stream<T> limit(int maxSize)
```
- **toList**: returns the process element into list.
```
List<T> toList()
```
