## Was sind Unit Test

##### Unit Test sind automatisierte Tests, die einzelne Code-Einheiten wie Methoden oder Klassen überprüfen, um sicherzustellen, dass sie korrekt funktionieren.

---

## Umsetzung in C# 

```csharp
namespace Smarthome
{
    public class SmartHome
    {
        public bool lichtZustand { get; private set; }

        public int Temperatur { get; private set; }

        public string AktiverModus { get; private set; }

        public SmartHome(bool lichtZustand, int temperatur, string aktiverModus)
        {
            this.lichtZustand = lichtZustand;
            Temperatur = temperatur;
            AktiverModus = aktiverModus;
        }
        public SmartHome() { }

        public void LichtEin()
        {
            lichtZustand = true;
        }

        public void LichtAus()
        {
            lichtZustand = false;
        }

        public int TemperaturSetzen(int grad)
        {
            return grad;
        }

        public string ModusWechseln(string modus)
        {
            AktiverModus = modus;
            return AktiverModus;
        }

        public string StatusAnzeigen()
        {
            return $"Temperatur: {Temperatur} AktiverModus: {AktiverModus} Lichtzustand: {lichtZustand}";
        }
    }
}
```

```csharp
namespace SmartHome_Testing
{
    [TestClass]
    public sealed class Test1
    {
        
        [TestMethod]
        public void LichEinTest()
        {
            var smarthome1 = new Smarthome.SmartHome();

            smarthome1.LichtEin();

            Assert.IsTrue(smarthome1.lichtZustand);
        }
        [TestMethod]
        public void LichtAustest()
        {
            var smarthome2 = new Smarthome.SmartHome();

            smarthome2.LichtAus();

            Assert.IsFalse(smarthome2.lichtZustand);
        }
        [TestMethod]
        public void TemperaturMin()
        {
            var smarthome3 = new Smarthome.SmartHome();

            int resultat3 = smarthome3.TemperaturSetzen(30);

            Assert.AreEqual(30, resultat3);

        }
        [TestMethod]
        public void TemperaturMax()
        {
            var smarthome4 = new Smarthome.SmartHome();

            int resultat4 = smarthome4.TemperaturSetzen(100);

            Assert.AreEqual(100, resultat4);
        }
        [TestMethod]
        public void Rithush()
        {
            var smarthome5 = new Smarthome.SmartHome();

            string resultat5 = smarthome5.ModusWechseln("Aktiv");

            Assert.AreEqual("Aktiv", resultat5);
        }
        [TestMethod]
        public void StatusRithushAnzeigen()
        {
            var smarthome6 = new Smarthome.SmartHome(true, 20, "Rithush");

            string resultat6 = smarthome6.StatusAnzeigen();

            Assert.AreEqual("Temperatur: 20 AktiverModus: Rithush Lichtzustand: True", resultat6);


        }
    }
}
```