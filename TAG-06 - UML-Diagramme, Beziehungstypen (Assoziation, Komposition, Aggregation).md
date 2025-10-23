### Klassendiagramm, Objektidagramm & Sequenzdiagramm erstellen und interpretieren

#### Klassendiagramm:
![[Pasted image 20251023191241.png]]
#### C# Umsetzung

```csharp
public class Wasserfass
{
    public int MinimalPegel { get; }
    public int MaximalPegel { get; }
    public int Fuellstand { get; private set; }
    public int Kapazitaet { get; }

    public Wasserfass(int minimalPegel, int maximalPegel, int fuellstand, int kapazitaet)
    {
        this.MinimalPegel = minimalPegel;
        this.MaximalPegel = maximalPegel;
        this.Fuellstand = fuellstand;
        this.Kapazitaet = kapazitaet;
    }

    public int Befuellen(int menge)
    {
        return Fuellstand += menge;
    }

    public int Entnehmen(int menge)
    {
        return Fuellstand -= menge;
    }

    public void Entleeren()
    {
        Fuellstand = 0;
    }
}
```

#### Objektdiagramm:

![[Pasted image 20251023191617.png]]

#### C# Umsetzung

```csharp
using System;

class Mitarbeiter
{
    public string Name;
}

class Kunde
{
    public string Name;
    public Mitarbeiter Betreuer;
}

class Auftrag
{
    public int ID;
    public Kunde Erteiler;
}

class Program
{
    static void Main()
    {
        // Mitarbeiter
        Mitarbeiter maier = new Mitarbeiter { Name = "Markus Maier" };
        Mitarbeiter kaiser = new Mitarbeiter { Name = "Franz Kaiser" };

        // Kunden
        Kunde mueller = new Kunde { Name = "Knut Müller", Betreuer = maier };
        Kunde knudsen = new Kunde { Name = "Angela Knudsen", Betreuer = maier };

        // Aufträge
        Auftrag a1 = new Auftrag { ID = 1, Erteiler = mueller };
        Auftrag a2 = new Auftrag { ID = 2, Erteiler = mueller };
        Auftrag a5 = new Auftrag { ID = 5, Erteiler = knudsen };

        // Ausgabe
        Console.WriteLine($"{maier.Name} betreut {mueller.Name} und {knudsen.Name}");
        Console.WriteLine($"{mueller.Name} erteilt Auftrag {a1.ID} und {a2.ID}");
        Console.WriteLine($"{knudsen.Name} erteilt Auftrag {a5.ID}");
    }
}

```

#### Sequenzdiagramm:

![[Pasted image 20251023193814.png]]

#### C# Umsetzung:

```csharp
using System;

class K1
{
    K2 k2 = new K2();
    K3 k3 = new K3();

    public void Start()
    {
        // Nachricht1 an K2
        string antwort = k2.Nachricht1("Argument");

        // Antwort verarbeiten
        Console.WriteLine("K1 bekommt Antwort: " + antwort);

        // Nachricht2 an K3
        k3.Nachricht2();
    }
}

class K2
{
    public string Nachricht1(string arg)
    {
        Console.WriteLine("K2 bekommt Nachricht1 mit: " + arg);
        return "Ok = Nachricht1";
    }
}

class K3
{
    public void Nachricht2()
    {
        Console.WriteLine("K3 bekommt Nachricht2");
    }
}

class Program
{
    static void Main()
    {
        K1 k1 = new K1();
        k1.Start();
    }
}

```

### Beziehungstypen «Assoziation», «Komposition» und «Aggregation»

#### Assoziation:

- Bedeutung:
Eine **Assoziation** beschreibt eine allgemeine Beziehung zwischen zwei Klassen – sie **kennen sich gegenseitig** in irgendeiner Form.

- Beispiel:
Eine Klasse `Person` und eine Klasse `Auto`:  
Eine Person **besitzt** (oder benutzt) ein Auto, aber wenn die Person gelöscht wird, **existiert das Auto weiter**.

- In C#:
```csharp
class Auto
{
    public string Modell { get; set; }
}

class Person
{
    public string Name { get; set; }
    public Auto Auto { get; set; }  // Assoziation: Person kennt Auto
}
```

- UML Darstellung:
```csharp
Person ───── Auto
```

#### Komposition:

- Bedeutung:
Eine **Aggregation** ist eine **"Hat-ein"–Beziehung**, bei der ein Objekt Teil eines anderen ist, aber **unabhängig existieren kann**.

- Beispiel:
Eine `Mannschaft` besteht aus mehreren `Spielern`.  
Wenn die Mannschaft aufgelöst wird, **leben die Spieler weiter** (können in einer anderen Mannschaft spielen).

- In C#
```csharp
class Spieler
{
    public string Name { get; set; }
}

class Mannschaft
{
    public string Name { get; set; }
    public List<Spieler> SpielerListe { get; set; } = new List<Spieler>();
}
```

- UML Darstellung:
```csharp
Mannschaft ◇─── Spieler
```

#### Aggregation:

- Bedeutung:
Eine **Komposition** ist eine **starke Aggregation**:  
Das Teilobjekt **gehört ausschließlich** zum Ganzen und **wird mit ihm erstellt und zerstört**.

- Beispiel:
Ein `Haus` besteht aus `Räumen`.  
Wenn das Haus zerstört wird, **verschwinden auch die Räume** – sie existieren nicht unabhängig.

- In C#:
```csharp
class Raum
{
    public string Bezeichnung { get; set; }

    public Raum(string bezeichnung)
    {
        Bezeichnung = bezeichnung;
    }
}

class Haus
{
    public string Adresse { get; set; }
    public List<Raum> Raeume { get; private set; }

    public Haus(string adresse)
    {
        Adresse = adresse;
        Raeume = new List<Raum>
        {
            new Raum("Wohnzimmer"),
            new Raum("Küche")
        };
    }
}
```

- UML Darstellung:
```csharp
Haus ◆─── Raum
```
