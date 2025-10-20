## Konstruktoren & Methoden

Konstruktoren sind spezielle Methoden, die beim Erstellen eines neuen Objekts automatisch aufgerufen werden. Sie initialisieren den Anfangszustand des Objekts.

```csharp
public class Kreis
{
    public Kreis(double radius, string farbe) // Konstruktor
    {
        this.Radius = radius;
        this.Farbe = farbe;
    }
}

Kreis meinKreis = new Kreis(5.0, "rot"); // Aufruf
```

---

## Methodensignatur & Überladen

Die **Methodensignatur** besteht aus Name + Parameterliste (Typ, Anzahl, Reihenfolge). Sie identifiziert eine Methode eindeutig.

**Überladen:** Mehrere Methoden mit gleichem Namen, aber unterschiedlicher Signatur.

```csharp
public class Rechner
{
    // Signatur: Add(int, int)
    public int Add(int a, int b)
    {
        return a + b;
    }
    
    // Signatur: Add(double, double) - ÜBERLADEN
    public double Add(double a, double b)
    {
        return a + b;
    }
    
    // Signatur: Add(int, int, int) - ÜBERLADEN
    public int Add(int a, int b, int c)
    {
        return a + b + c;
    }
}
```
