## Polymorphie
Polymorphie bedeuted "mehrere gestalten". In der Objektorientierung heisst es dass man **DIE GLEICHE METHODE ÜBERSCHREIBT UND MAN ANDERS IMPLEMENTIERT** . Man hat zwei Möglichkeiten: Interfaces oder Vererben.

**Vererbung:**

```csharp
namespace Piggy
{
    internal abstract class Animal
    {
        public virtual void makeSound()
        {
            Console.WriteLine("BITTE HIER EIGENE IMPLEMENTIERUNG MACHEN");
        }
    }
}
```

```csharp
namespace Piggy
{
    internal class Dog : Animal
    {
        public override void makeSound()
        {
            Console.WriteLine("WAU WAU");
        }
    }
}
```

```csharp
namespace Piggy
{
    internal class Cat : Animal
    {
        public override void makeSound()
        {
            Console.WriteLine("MIAUUUUUU MIAUUUUUUU");
        }
    }
}
```

```csharp
namespace Piggy
{
    internal class Chicken : Animal
    {
        public override void makeSound()
        {
            Console.WriteLine("gawk gawk");
        }
    }
}
```

```csharp
namespace Piggy
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Dog d = new Dog();
            Cat c = new Cat();
            Chicken ch = new Chicken();
            List<Animal> animals = new List<Animal>() { d,c,ch};

            foreach( Animal animal in animals)
            {
                animal.makeSound();
            }

        }
    }
}
```
