# stream-api-notes
Notes for Java Stream API

# Stream API
- Is used for processing collections and arrays.

# What is stream() method do?
- Stream<E> stream() method is called to use Stream API
- Stream<E> stream() serves as entry point for us to access Stream API methods 

### Stream API methods
#### filter
- will return all the values as long as condition is true.
- ###### Method signature
  ```
  Stream<T> filter(Predicate<T> condition)
  ```
- ###### Code sample
  ```
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21);
  Person barPerson = new Person("Bar", 22);
  Person fooBarPerson = new Person("FooBar", 23);

  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);
    
  // Will return only the persons that age is greater than or equal to 22    
  List<Person> personsWithFilteredAge = persons.stream()
    .filter(person -> person.age() >= 22)
    .toList();
  ```

#### map
- process each element and returns the processed element
- ###### Method signature
  ```
  R Stream<R> map(Function<T, R> mapper)
  ```
- ###### Code sample
  ```
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21, 5_000);
  Person barPerson = new Person("Bar", 22, 10_000);
  Person fooBarPerson = new Person("FooBar", 23, 15_000);
        
  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);
    
  // Adding 2_000 for each person salary
  persons.stream()
    .map(person -> person.salary() + 2_000)
    .forEach(System.out::println);
  ```
  
#### forEach
- process each element and returns void
- ###### Method signature
  ```
  void forEach(Consumer<T> consumer)
  ```
- ###### Code sample
  ```
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21, 5_000);
  Person barPerson = new Person("Bar", 22, 10_000);
  Person fooBarPerson = new Person("FooBar", 23, 15_000);
        
  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);
    
  // Printing each person in the list
  persons.stream()
    .forEach(System.out::println);
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
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21, 5_000);
  Person barPerson = new Person("Bar", 22, 10_000);
  Person fooBarPerson = new Person("FooBar", 23, 15_000);
        
  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);
    
  // Sorting person list via age
  persons.stream()
    .sorted(Comparator.comparing(Person::age))
    .forEach(System.out::println);
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
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21, 5_000);
  Person barPerson = new Person("Bar", 22, 10_000);
  Person fooBarPerson = new Person("FooBar", 23, 15_000);
        
  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);
    
  // Get the count of persons who age is greater than 22
  long personCount = persons.stream()
    .filter(person -> person.age() > 22)
    .count();
  ```

#### min
- will return the lowest value in the collection.
- ###### Method signature
  ```
  Optional<T> min(Comparator<T> comparator)
  ```
- ###### Code sample
  ```
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21, 5_000);
  Person barPerson = new Person("Bar", 22, 10_000);
  Person fooBarPerson = new Person("FooBar", 23, 15_000);

  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);

  // Finding the person with the minimum age
  Optional<Person> minAgePerson = persons.stream()
    .min((p1, p2) -> Integer.compare(p1.getAge(), p2.getAge()));
  ```

#### max
- will return the max value in the collection.
- ###### Method signature
  ```
  Optional<T> max(Comparator<T> comparator)
  ```
- ###### Code sample
  ```
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21, 5_000);
  Person barPerson = new Person("Bar", 22, 10_000);
  Person fooBarPerson = new Person("FooBar", 23, 15_000);

  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);

  // Finding the person with the minimum age
  Optional<Person> minAgePerson = persons.stream()
    .max((p1, p2) -> Integer.compare(p1.getAge(), p2.getAge()));
  ```

##### reduce
- will return the combined value of all the elements in collection
- ###### Method signature
  ```
  Optional<T> reduce(BinaryOperator<T> accumilator)
  ```
- ###### Code sample
  ```
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21, 5_000);
  Person barPerson = new Person("Bar", 22, 10_000);
  Person fooBarPerson = new Person("FooBar", 23, 15_000);

  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);

  // Get the total salary of the company
  double totalSalary = persons.stream()
    .map(Person::salary)
    .reduce(0, (t, s) -> t + s);
  ```
  
#### peek
- used to see the elements while processing it.
- ###### Method signature
  ```
  Stream<T> peek(Consumer<T> action)
  ```
- ###### Code sample
  ```
  // Declaring person objects
  Person fooPerson = new Person("Foo", 21, 5_000);
  Person barPerson = new Person("Bar", 22, 10_000);
  Person fooBarPerson = new Person("FooBar", 23, 15_000);

  // Creating a list of person
  List<Person> persons = Arrays.asList(fooPerson, barPerson, fooBarPerson);

  // Get the total salary of the company
  double totalSalary = persons.stream()
    .map(Person::salary)
    .peek(System.out::println)
    .reduce(0, (t, s) -> t + s);  
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
