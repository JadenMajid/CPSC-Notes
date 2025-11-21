Switches depending on the type of an input object are a type of [[Code Smells]]. They're an indicator that a method is doing too much, and indicates too much [[Coupling]] between a encapsulation and subtypes in a system. 

In the below code, Bird.TYPE is switched on, when a cleaner way would be to create an interface or abstract class bird, that is inherited by subclasses

Bad
```java
public getSpeed(obj: BirdContainer): number {
    switch (obj.kind) {
        case Bird.EUROPEAN:
            return this.getBaseSpeed();
        case Bird.AFRICAN:
            return this.getBaseSpeed() - this.getLoad() * this.coconutCount;
        case Bird.NORWEGIAN_BLUE:
            return (this.isNailed) ? 0 : this.getBaseSpeed();
    }
    throw new Error("Unknown kind of bird");
}
```

Better
```java
abstract class Bird {
    abstract getSpeed(): number;
}

class EuropeanSwallow extends Bird {
    constructor(private baseSpeed: number) { super(); }

    getSpeed(): number {
        return this.baseSpeed;
    }
}

class AfricanSwallow extends Bird {
    constructor(
        private baseSpeed: number,
        private loadFactor: number,
        private coconutCount: number
    ) { super(); }

    getSpeed(): number {
        return this.baseSpeed - this.loadFactor * this.coconutCount;
    }
}

class NorwegianBlueParrot extends Bird {
    constructor(
        private baseSpeed: number,
        private isNailed: boolean
    ) { super(); }

    getSpeed(): number {
        return this.isNailed ? 0 : this.baseSpeed;
    }
}

```
#310