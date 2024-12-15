### Start

```
import com.mongodb.client.MongoClient;
import com.mongodb.client.MongoClients;
import com.mongodb.client.MongoCollection;
import com.mongodb.client.MongoDatabase;
import org.bson.Document;

public class MongoDB {
    public static void main(String[] args) {
        String connectionString = "mongodb://localhost:27017"; // MongoDB-Verbindungs-URI
        try (MongoClient mongoClient = MongoClients.create(connectionString)) {
            MongoDatabase database = mongoClient.getDatabase("exampleDB");
            MongoCollection<Document> collection = database.getCollection("exampleCollection");

            // Daten auslesen
            for (Document doc : collection.find()) {
                System.out.println(doc.toJson());
            }
        }
    }
}

```

### create

```
Document document = new Document("name", "Max Mustermann")
        .append("age", 30)
        .append("city", "Berlin");
collection.insertOne(document);

```

### read

```
Document query = new Document("name", "Max Mustermann");
Document result = collection.find(query).first();
System.out.println(result.toJson());

```

### update

```
Document query = new Document("name", "Max Mustermann");
Document update = new Document("$set", new Document("age", 31));
collection.updateOne(query, update);

```

### delete

```
Document query = new Document("name", "Max Mustermann");
collection.deleteOne(query);

```

### Datenmodell für eine NoSQL-Datenbank erstellen

```
{
  "name": "Max Mustermann",
  "email": "max@example.com",
  "age": 30,
  "addresses": [
    {
      "type": "Home",
      "city": "Berlin",
      "postalCode": "10115"
    },
    {
      "type": "Work",
      "city": "Hamburg",
      "postalCode": "20095"
    }
  ]
}

```

### NoSQL-Modell in die Datenbank überführen

```
Document user = new Document("name", "Max Mustermann")
        .append("email", "max@example.com")
        .append("age", 30)
        .append("addresses", Arrays.asList(
                new Document("type", "Home").append("city", "Berlin").append("postalCode", "10115"),
                new Document("type", "Work").append("city", "Hamburg").append("postalCode", "20095")
        ));
collection.insertOne(user);

```

### Mit JSON und MongoClient auf MongoDB zugreifen

```
// Daten als JSON-String einfügen
String json = "{\"name\":\"Anna\", \"age\":25, \"city\":\"München\"}";
Document doc = Document.parse(json);
collection.insertOne(doc);

// JSON-Ausgabe
for (Document doc : collection.find()) {
    System.out.println(doc.toJson());
}

```

### Was ist ein POJO (Plain Old Java Object)?

- Ein POJO ist eine einfache Java-Klasse ohne spezielle Abhängigkeiten oder Annotationen.
- Es wird häufig für Datenstrukturen genutzt.

```
public class User {
    private String name;
    private String email;
    private int age;

    // Getter und Setter
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    public String getEmail() { return email; }
    public void setEmail(String email) { this.email = email; }

    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
}

```
