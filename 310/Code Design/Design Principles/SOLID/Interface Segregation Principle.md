No client of an interface should be forced to depend on methods that it does not use

Violation:
```java
public interface Bakery{
	public void sellBread();
	public void sellDoughnuts();
}

public interface CoffeeShop{

	public void sellCoffee();
}

public class CoffeeShopImplementation implements Bakery, CoffeeShop{
	public void sellBread(); // But coffee shop doesn't want to sell bread!
	public void sellDoughnuts();
	public void sellCoffee
}
```

Fixed:
```java
public interface FullTimeBakery{
	public void sellBread();
}

public interface CoffeeShopBakery{
	public void sellDoughnuts();
}

public interface CoffeeShop{
	public void sellCoffee();
}

public class CoffeeShopImplementation implements CoffeeShopBakery, CoffeeShop{
	public void sellDoughnuts();
	public void sellCoffee
}
```
#310