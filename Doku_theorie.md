### Was ist ein BSON?

- BSON (Binary JSON) ist ein binäres Format zur Darstellung von JSON-ähnlichen Dokumenten. Es wird von MongoDB genutzt, da es kompakter, schneller und effizienter als JSON ist.

* Vorteile:
  - Zusätzliche Datentypen: Unterstützt z. B. Date, Binary, ObjectId, Timestamp und Decimal128.
* Effiziente Verarbeitung:
  - Schnelle Abfragen und Traversierung durch binäre Kodierung.
* Erweiterbarkeit:
  - Kann neue Datentypen aufnehmen, bleibt dabei abwärtskompatibel. Im Vergleich zu JSON hat BSON etwas mehr Speicher-Overhead, ist aber optimal für MongoDB.
