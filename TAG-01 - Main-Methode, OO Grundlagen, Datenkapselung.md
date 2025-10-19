## Main Methode und Bestandteile erklären

So sieht die Main Methode aus:

```csharp
public static void Main(string[] args)
{
	
}
```

`public`: Das ist der Zugriffsmodifikator 
`static`: Die methode gehört zur klasse und muss nicht mehr mit einem Objekt erzeugt werden
`void`: Das ist der Rückgabetyp, void gibt nichts zurück
`Main`: Das ist der name der Methode
`string[] args`: das gehört in den Klammern und wird übergeben wenn man befehlsargumente mitgibt.

---
## Objektorientierung und wesentliche Elemente beschreiben

Es gibt vier prinzipien der Objektorientierung:

- **Kapselung:**  
    Daten und Methoden werden zusammen in einer Klasse versteckt, um den direkten Zugriff von aussen zu verhindern. Nur ausgewählte Methoden (Schnittstellen) erlauben den Zugriff, was die Sicherheit verbessert.
- **Vererbung:**  
    Eine neue Klasse erbt Eigenschaften und Methoden von einer bestehenden Klasse. Dadurch wird Code wiederverwendet und es können spezialisierte Klassen erstellt werden, die die Basisfunktionalität erweitern oder anpassen.
- **Polymorphismus:**  
    Unterschiedliche Objekte können dieselbe Methode auf unterschiedliche Weise ausführen. Dies ermöglicht flexiblen Code, bei dem das gleiche Interface (Methodenaufruf) je nach Objekt unterschiedlich reagiert (z. B. "geräuschMachen" bei Hund und Katze).
- **Abstraktion:**  
    Komplexe Implementierungen werden versteckt, sodass nur die wesentlichen Eigenschaften oder Funktionen angezeigt werden. Der Benutzer interagiert mit einer einfachen, klaren Schnittstelle, ohne sich um Details kümmern zu müssen (z. B. beim Autofahren die Steuerung ohne Wissen über den Motor).

---

## Datenkapselung und Gehiminisprinip erkläutern

**Datenkapselung**: Kontrollierter Zugriff auf Daten durch Getter und Setter.

**Geheimnissprinzip**: Versteckt die interne Logik und Details der Implementierung. Du gibst nur die notwendigen Informationen preis und schützt so die Daten und Funktionsweise vor unerwünschtem Zugriff oder Manipulation.