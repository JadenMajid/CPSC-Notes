Long methods make code harder to understand. By reducing long methods into smaller chunks, we abstract out implementation details, and can reduce amount of information we need to keep in our short term memory when interpreting code.

Bad
```java
void printOwing() {
  printBanner();

  // Print details.
  System.out.println("name: " + name);
  System.out.println("amount: " + getOutstanding());
}
```

Good
```java
void printOwing() {
  printBanner();
  printDetails(getOutstanding());
}

void printDetails(double outstanding) {
  System.out.println("name: " + name);
  System.out.println("amount: " + outstanding);
}
```
#310
#310
#310