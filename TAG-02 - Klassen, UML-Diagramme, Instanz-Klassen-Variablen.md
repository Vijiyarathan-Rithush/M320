## Unterschied Instanz- und Klassenvariablen

#### Instanzvariable
Instanzvariablen gehören zum Objekt. Das sind die Variablen welches normal deklariert werden.

Beispiel:
```csharp
namespace InstanzVariable
{
	internal class InstanzVariable
	{
		private string name; <- Instanzvariable
		public int age; <- Instanzvariable
		
		public IntanzVariable(string name, int age) <- Konsturktor
		{
			this.name = name;
			this.age = age;
		}
	}
}
```

So wird eine Instanzvariable aufgerufen:

```csharp
InstanzVariable iv = new InstanzVariable("Max Mustermann", 67); <- Objekt 1
console.WriteLine(iv.name); // Ausgabe: Max Mustermann
console.WriteLine(iv.age); // Ausgabe: 67

InstanzVariable iv1 = new InstanzVariable("Good Boy", 21); <- Objekt 2
console.WriteLine(iv1.name); // Ausgabe: Good Boy
console.WriteLine(iv1.age); // Ausgabe: 21
```

#### Klassenvariablen
Klassenvariablen gehören zur Klasse.

>[!check]
>**Klassenvariabeln werden immer mit dem schlüsselwort `static` deklariert**

```csharp
namespace KlassenVariable
{
	internal class KlassenVariable
	{
		private string name; <- Instanzvariable // zum Unterschied zeigen
		private static double pi = 3.1418592654; <- KlassenVariable
	}
}
```

So wird eine Klassenvariable aufgerufen:

```csharp
KlassenVariable kv = new KlassenVariable();
console.WriteLine(kv.pi); // Ausgabe: 3.1418592654
```

---

## Aufbau UML-Klassendiagramm (UML 2 Standart)

![[{04707414-DD2B-4FBE-8182-436D1D5C3422}.png]]
## 1. Klassenname
Der Klassenname wird **IMMER** mittig geschrieben.
Der Klassenname ist immer im singular.

>[!important]
>Soll die Klasse abstract sein, so wird es unter dem Klassennamen als `{abstract}` definiert. Sollte das UML-Diagramm jedoch per hand gemacht werden, dann soll es ***KURSIV*** dargestellt werden.
>Beim Interface ist es wieder anders. Dort wird es per hand und digital so vermerkt:
>`<<interface>>` 
>Man muss beachten das man bei einem Interface ein `I` vor dem Klassennamen anhängt.

## 2. Attribute
Attribute sind immer linksbündig und klein zu schreiben.
Das Feld muss vorhanden sein, auch wenn es keine attribute gibt.

## 3. Operationen
Die Operationen müssen immer klein geschrieben werden.
Die Operationen sind nicht zwingend notwendig.
Operationen werden so geschrieben:
`Operationsname()`

