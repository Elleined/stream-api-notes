# stream-api-notes
Notes for Java Stream API

# Stream API
- Is used for processing collections and arrays.

### Stream API methods
#### filter
- will return all the values as long as condition is true.
- ###### Method signature
  ```
  Stream<T> filter(Predicate<T> condition)
  ```
- ###### Code sample
  ```
  
  ```

#### map
- process each element and returns the processed element
- ###### Method signature
  ```
  R Stream<R> map(Function<T, R> mapper)
  ```
- ###### Code sample
  ```
  
  ```
  
#### forEach
- process each element and returns void
- ###### Method signature
  ```
  void forEach(Consumer<T> consumer)
  ```
- ###### Code sample
  ```
  
  ```
#### sorted
- sort the elements in natural order and specified comparator
- ###### Method signature
  ```
  Stream<T> sorted()
  Stream<T> sorted(Comparator<T> comparator)
  ```
- ###### Code sample
  ```
  
  ```

#### flatMap
- used for transforming and flattening of collection
- ###### Method signature
  ```
  Stream<T> flatMap(Function<Stream<T>> mapper)
  ```
- ###### Code sample
  ```
  
  ```

#### count
- returns the size of processed collection
- ###### Method signature
  ```
  long count()
  ```
- ###### Code sample
  ```
  
  ```

#### min
- will return the lowest value in the collection.
- ###### Method signature
  ```
  Optional<T> min(Comparator<T> comparator)
  ```
- ###### Code sample
  ```
  
  ```

#### max
- will return the max value in the collection.
- ###### Method signature
  ```
  Optional<T> max(Comparator<T> comparator)
  ```
- ###### Code sample
  ```
  
  ```

##### reduce
- will return the combined value of all the elements in collection
- ###### Method signature
  ```
  Optional<T> reduce(BinaryOperator<T> accumilator)
  ```
- ###### Code sample
  ```
  
  ```
  
#### peek
- used to see the elements while processing it.
- ###### Method signature
  ```
  Stream<T> peek(Consumer<T> action)
  ```
- ###### Code sample
  ```
  
  ```

#### allMatch
- will return true if given condition match will all the elements.
- ###### Method signature
  ```
  boolean allMatch(Predicate<T> condition)
  ```
- ###### Code sample
  ```
  
  ```

#### anyMatch
- will return true if any of the element match with the given condition.
- ###### Method signature
  ```
  boolean anyMatch(Predicate<T> condition)
  ```
- ###### Code sample
  ```
  
  ```

#### noneMatch
- will return true if there no element match with the given condition.
- ###### Method signature
  ```
  boolean noneMatch(Predicate<T> condition)
  ```
- ###### Code sample
  ```
  
  ```

#### findFirst
- returns the first element of stream
- ###### Method signature
  ```
  Optional<T> findFirst()
  ```
- ###### Code sample
  ```
  
  ```

#### findAny
- will pick random values in stream elements.
- ###### Method signature
  ```
  Optional<T> findAny()
  ```
- ###### Code sample
  ```
  
  ```

#### limit
- will limit the element that can be process in stream
- ###### Method signature
  ```
  Stream<T> limit(int maxSize)
  ```
- ###### Code sample
  ```
  
  ```

#### toList
- returns the process element into list.
- ###### Method signature
  ```
  List<T> toList()
  ```
- ###### Code sample
  ```
  
  ```
