All classes should have a single responsibility

Bad: employee is responsible for saving itself, pay, and generating reports, which lie under different business functions
```typescript
public class Employee {  
// Determines how much an employee is paid  
public calculatePay(): number;  
// Stores Employee data in database  
public save(): void;  
// Reports hours worked and pay for auditing  
public reportHours(): string;
}
```

Better: Each class is responsible for a different business function
```typescript
public class PayCalculator {  
	public calculatePay(emp: Employee): number;  
}  
public class EmployeeRepository {  
	public save(emp: Employee): void;  
}  
public class ReportGenerator {  
	public reportHours(emp: Employee): string;  
}
```
#310
#310
#310