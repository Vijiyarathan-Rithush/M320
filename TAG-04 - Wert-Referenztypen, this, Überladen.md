# Primitiven Datentypen & Objekten beschreiben & Call by Value / Call by Reference,

### Primitive Datentypen & Objekte:,

Sind die Typen die Standard integriert sind. Ganzzahlen:

- byte,
- short,
- int,
- long,

Gleitkommazahlen:

- float,
- double,

Zeichen:

- char,

Wahrheitswerte:

- boolean,

### Call by Value:,

Wert der Übergeben wird, wird kopiert. Dabei bleibt das Originale immer gleich. Der kopierte Wert wird verändert.

### Call by Reference:,

Speicheradresse der Variable wird weitergegeben. Original wird verändert.

---

# this-Verweis korrekt einsetzten und erklären

### Erklärung:

Wenn man ein Objekt erstellt bezieht es sich auf sich selber (Instanz).

### Einsetzten:

```csharp
public class Mitarbeiter
{
	private string alias;
	private string name;
	
	public Mitarbeiter(string name, string alias)
	{
		this.name = name;
		this.alias = alias;
	}
}
```
s