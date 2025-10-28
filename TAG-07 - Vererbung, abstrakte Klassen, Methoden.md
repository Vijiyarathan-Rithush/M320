### Kennt Vererbung & Darstellung in UML

#### Klassendiagramm mit Vererbung:

![[{5699DDB1-15AC-4A9C-AF5A-14663E13E2EE}.png]]

#### Abstrakte Klasse:

##### In der Realen Welt existiert kein Objekt der Klasse "Person", sondern nur Objekte von "Kunde", "Lagerist" & Kleinkind.

> [!important] Damit sichergestellt werden kann, dass kein Objekt der Klasse Person erstellt wird, wird die Klasse "Person" `abstract` deklariert.

#### Abstrakte Methode:

##### Alle Personen tragen etwas jedoch auf seine eigene Weise. Deshalb muss die Operation trage() in der allgemeinen Klasse definiert werden und in den Unterklassen unterschiedlich implementiert werden.

> [!important] Nun wird trage() in der Basisklasse `abstract` deklariert, bedeutet das trage() zwingend in den Unterklassen zu implementieren ist, dies wird mit dem Schlüsselwort `override` gemacht.

#### Überschreiben:

##### Da Kinder insbesondere Kleinkinder auf ihre eigene Art essen wird bei ihnen zusätzlich die Operation essen() hinzugefügt. Essen ist in der Oberklasse auch schon vorhanden und wir Implementieren diese Operation mit derselben Methodensignatur, also überschreiben wir sie.

> [!important] Nun wird dazu die überschreibende Funktion essen() in der Unterklasse Kind mit `override` deklariert und die Funktion essen() in der Oberklasse Person mit `virtual`.

---

### abstrakte Klassen, abstrakte Methoden und Interface in C# umsetzen

#### Codebeispiel abstrakte Klasse & abstrakte Methode:

```csharp
abstract class Animal 
{
  public abstract void AnimalSound();
  public void Sleep() 
  {
    Console.WriteLine("Zzz");
  }
}
```

#### Man kann nun nicht mehr ein Objekt von der Klasse Animal erstellen

> [!important] Animal myObj = new Animal(); // Wird einen Fehler generieren (Cannot create an instance of the abstract class or interface 'Animal')

---

#### Codebeispiel Interface:

```csharp
interface IAnimal
{
    void AnimalSound();
}
public class Pig : IAnimal
{
    public void AnimalSound()
    {
        Console.WriteLine("The pig says: wee wee");
    }
}
class Program
{
    public static void Main(string[] args)
    {
        Pig pig = new Pig();
        pig.AnimalSound();
    }
}
```

#### Die Interface Methode hat keinen Body. In der Klasse Pig wird die Methode AnimalSound vom Interface IAnimal implementiert. Im Programm wird ein Objekt Pig erzeugt.