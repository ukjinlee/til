# Parse JSON

## Moshi
[Moshi](https://github.com/square/moshi/) is a modern JSON library for Android and Java. It makes it easy to parse JSON into Java objects:

```java
String json = ...;

Moshi moshi = new Moshi.Builder().build();
JsonAdapter<BlackjackHand> jsonAdapter = moshi.adapter(BlackjackHand.class);

BlackjackHand blackjackHand = jsonAdapter.fromJson(json);
System.out.println(blackjackHand);
```

And it can just as easily serialize Java objects as JSON:

```java
BlackjackHand blackjackHand = new BlackjackHand(
    new Card('6', SPADES),
    Arrays.asList(new Card('4', CLUBS), new Card('A', HEARTS)));

Moshi moshi = new Moshi.Builder().build();
JsonAdapter<BlackjackHand> jsonAdapter = moshi.adapter(BlackjackHand.class);

String json = jsonAdapter.toJson(blackjackHand);
System.out.println(json);
```

### Parse JSON Arrays
Say we have a JSON string of this structure:

```json
[
  {
    "rank": "4",
    "suit": "CLUBS"
  },
  {
    "rank": "A",
    "suit": "HEARTS"
  }
]
```

We can now use Moshi to parse the JSON string into a List<Card>.

```java
String cardsJsonResponse = ...;
Type type = Types.newParameterizedType(List.class, Card.class);
JsonAdapter<List<Card>> adapter = moshi.adapter(type);
List<Card> cards = adapter.fromJson(cardsJsonResponse);
```

### Kotlin

```kotlin
val moshi = Moshi.Builder()
    // ... add your own JsonAdapters and factories ...
    .add(KotlinJsonAdapterFactory())
    .build()
```
