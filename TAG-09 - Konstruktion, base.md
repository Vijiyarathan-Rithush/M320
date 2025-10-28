## Konstruktion

Wird von Oben nach Unten Instanziiert. Erst Superklasse dann Unterklasse

---
## Base

##### In C#:

```csharp
namespace Base 
{
	public abstract class Fahrzeug 
	{
		public string Marke {get; set;}
		public string Farbe {get; set;}
		public int Baujahr {get; set;}
		
		public Fahrzeug (string marke, string farbe, int baujahr) 
		{
			this.Marke = marke;
			this.Farbe = farbe;
			this.Baujahr = baujahr;
		}
		
		public virtual void macheGeraeusch()
		{
			Console.WriteLine("Brrmmm Brrmmm");
		}
	}
}
```

```csharp
namespace Base 
{
	public class Auto : Fahrzeug
	{
		public int S {get; set;}
		
		public Auto (string m, string f, int b, int s) : base (m, f, b)
		{
			this.S = s;
		}
		
		public override void macheGeraeusch()
		{
			base.macheGeraeusch();
		}
	}
}
```

```csharp
namespace Base
{
	public static void Main(string[] args)
	{
		Auto auto = new Auto("Porsche", "Schwarz", 2015, 2);
		
		auto.macheGeraeusch(); // Ausgabe: Brrmmm Brrmmm
	}
}
```

