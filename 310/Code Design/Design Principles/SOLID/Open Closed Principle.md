A class must be closed for internal change, but open for extension
If we have a method that is very large and does not use [[Abstraction]], and we want to make a new class that has largely the same functionality, but changes one section, then we are forced to completely rewrite the method
```java
public class ReportGenerator  
{  
    public string GenerateReport(string reportType)  
    {  
        if (reportType == "PDF")  
        {  
            return "PDF Report Generated";  
        }  
        else if (reportType == "Excel")  
        {  
            return "Excel Report Generated";  
        }  
  
        return "Invalid Report Type";  
    }  
}
```
In the case where the large method calls other smaller methods within itself, we can make a modular change to that section, and get the desired output
```java
public interface IReport  
{  
    string Generate();  
}

public class PdfReport : IReport  
{  
    public string Generate()  
    {  
        return "PDF Report Generated";  
    }  
}  
  
public class ExcelReport : IReport  
{  
    public string Generate()  
    {  
        return "Excel Report Generated";  
    }  
}

public class ReportGenerator  
{  
    public string GenerateReport(IReport report)  
    {  
        return report.Generate();  
    }  
}

var generator = new ReportGenerator();  
  
var pdf = new PdfReport();  
Console.WriteLine(generator.GenerateReport(pdf));  
  
var excel = new ExcelReport();  
Console.WriteLine(generator.GenerateReport(excel));
```

code snippets from https://medium.com/@mishra.pankaj/mastering-the-open-closed-principle-with-c-with-examples-94f5e5fb4519

#310