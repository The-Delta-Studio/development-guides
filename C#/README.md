# The Delta Studio Backend Style Guide

## Table of Contents

1. [Convention Table](#convention-table)
2. [Types](#types)
3. [Namespaces](#namespaces)
4. [Objects](#objects)
5. [Classes](#classes)
6. [Interfaces](#interfaces)
7. [Declerations](#declerations)
8. [Abbreviations](#abbreviations)
9. [Methods](#methods)

## Convetion Table

| Object Name      | Notation   | Length | Plural | Prefix | Suffix | Abbreviation | Char Mask  | Underscores |
| :--------------- | :--------- | -----: | :----- | :----- | :----- | :----------- | :--------- | :---------- |
| Class name       | PascalCase |    128 | No     | No     | Yes    | No           | [A-z][0-9] | No          |
| Constructor name | PascalCase |    128 | No     | No     | Yes    | No           | [A-z][0-9] | No          |
| Method name      | PascalCase |    128 | Yes    | No     | No     | No           | [A-z][0-9] | No          |
| Method arguments | camelCase  |    128 | Yes    | No     | No     | Yes          | [A-z][0-9] | No          |
| Local variables  | camelCase  |     50 | Yes    | No     | No     | Yes          | [A-z][0-9] | No          |
| Constants name   | PascalCase |     50 | No     | No     | No     | No           | [A-z][0-9] | No          |
| Field name       | camelCase  |     50 | Yes    | No     | No     | Yes          | [A-z][0-9] | Yes         |
| Properties name  | PascalCase |     50 | Yes    | No     | No     | Yes          | [A-z][0-9] | No          |
| Delegate name    | PascalCase |    128 | No     | No     | Yes    | Yes          | [A-z]      | No          |
| Enum type name   | PascalCase |    128 | Yes    | No     | No     | No           | [A-z]      | No          |

## Types

-[2.1](#types--primitives) **Primitives**: When you access a primitive type you work directly on its value.

```csharp
//Good
int index = 100;
string timeSheet;
bool isCompleted;

//Bad
var index = 100;
var timeSheet;
```

-[2.2](#types--complex) **Complex**: When you access a complex type you work on a reference to its value.

```csharp
//Good
var stream = File.Create(path);
var customers = new Dictionary();

//Bad
System.IO.FileStream stream = File.Create(path);
Dictionary customers = new Dictionary();
```

> Why: Removes clutter, particularly with complex generic types. Type is easily detected with Visual Studio tooltips.

## Namespaces

-[3.1](#namespaces--naming) **Naming**: Organize namespaces with a clearly defined hierarchy

```csharp
// Examples
namespace Company.Product.Module.SubModule
{
}
namespace Product.Module.Component
{
}
namespace Product.Layer.Module.Group
{
}
```

## Objects

## Classes

-[5.1](#classes--naming) **Naming**:

```csharp

```

-[5.2](#classes--case) **Case**:

```csharp

```

## Interfaces

-[6.1](#interfaces--naming) **Naming**:

```csharp

```

-[6.2](#interfaces--case) **Case**:

```csharp

```

## Declerations

## Abbreviations

## Methods

-[9.1](#methods--naming) **Naming**:

```csharp

```

-[9.2](#methods--case) **Case**:

```csharp

```

-[9.3](#methods--arguments) **Case**:

```csharp

```

-[9.3.1](#methods--arguments--naming) **Naming**

```csharp

```

-[9.3.2](#methods--arguments--case) **Case**

```csharp

```

#### 1. Do use PascalCasing for class names and method names:

```csharp
public class ClientActivity
{
  public void ClearStatistics()
  {
    //...
  }
  public void CalculateStatistics()
  {
    //...
  }
}
```

**_Why: consistent with the Microsoft's .NET Framework and easy to read._**

**[⬆ back to top](#table-of-contents)**

#### 2. Do use camelCasing for method arguments and local variables:

```csharp
public class UserLog
{
  public void Add(LogEvent logEvent)
  {
    int itemCount = logEvent.Items.Count;
    // ...
  }
}
```

**_Why: consistent with the Microsoft's .NET Framework and easy to read._**

#### 3. Do not use Hungarian notation or any other type identification in identifiers

```csharp
// Correct
int counter;
string name;
// Avoid
int iCounter;
string strName;
```

**_Why: consistent with the Microsoft's .NET Framework and Visual Studio IDE makes determining types very easy (via tooltips). In general you want to avoid type indicators in any identifier._**

#### 4. Do not use Screaming Caps for constants or readonly variables:

```csharp
// Correct
public const string ShippingType = "DropShip";
// Avoid
public const string SHIPPINGTYPE = "DropShip";
```

**_Why: consistent with the Microsoft's .NET Framework. Caps grab too much attention._**

**[⬆ back to top](#table-of-contents)**

#### 5. Use meaningful names for variables. The following example uses seattleCustomers for customers who are located in Seattle:

```csharp
var seattleCustomers = from customer in customers
  where customer.City == "Seattle"
  select customer.Name;
```

**_Why: consistent with the Microsoft's .NET Framework and easy to read._**

#### 6. Avoid using Abbreviations. Exceptions: abbreviations commonly used as names, such as Id, Xml, Ftp, Uri.

```csharp
// Correct
UserGroup userGroup;
Assignment employeeAssignment;
// Avoid
UserGroup usrGrp;
Assignment empAssignment;
// Exceptions
CustomerId customerId;
XmlDocument xmlDocument;
FtpHelper ftpHelper;
UriPart uriPart;
```

**_Why: consistent with the Microsoft's .NET Framework and prevents inconsistent abbreviations._**

#### 7. Do use PascalCasing for abbreviations 3 characters or more (2 chars are both uppercase):

```csharp
HtmlHelper htmlHelper;
FtpTransfer ftpTransfer;
UIControl uiControl;
```

**_Why: consistent with the Microsoft's .NET Framework. Caps would grab visually too much attention._**

#### 8. Do not use Underscores in identifiers. Exception: you can prefix private fields with an underscore:

```csharp
// Correct
public DateTime clientAppointment;
public TimeSpan timeLeft;
// Avoid
public DateTime client_Appointment;
public TimeSpan time_Left;
// Exception (Class field)
private DateTime _registrationDate;
```

**_Why: consistent with the Microsoft's .NET Framework and makes code more natural to read (without 'slur'). Also avoids underline stress (inability to see underline)._**

**[⬆ back to top](#table-of-contents)**

#### 9. Do use predefined type names (C# aliases) like `int`, `float`, `string` for local, parameter and member declarations. Do use .NET Framework names like `Int32`, `Single`, `String` when accessing the type's static members like `Int32.TryParse` or `String.Join`.

```csharp
// Correct
string firstName;
int lastIndex;
bool isSaved;
string commaSeparatedNames = String.Join(", ", names);
int index = Int32.Parse(input);
// Avoid
String firstName;
Int32 lastIndex;
Boolean isSaved;
string commaSeparatedNames = string.Join(", ", names);
int index = int.Parse(input);
```

**_Why: consistent with the Microsoft's .NET Framework and makes code more natural to read._**

#### 11. Do use noun or noun phrases to name a class.

```csharp
public class Employee
{
}
public class BusinessLocation
{
}
public class DocumentCollection
{
}
```

**_Why: consistent with the Microsoft's .NET Framework and easy to remember._**

**[⬆ back to top](#table-of-contents)**

#### 12. Do prefix interfaces with the letter I. Interface names are noun (phrases) or adjectives.

```csharp
public interface IShape
{
}
public interface IShapeCollection
{
}
public interface IGroupable
{
}
```

**_Why: consistent with the Microsoft's .NET Framework._**

#### 13. Do name source files according to their main classes. Exception: file names with partial classes reflect their source or purpose, e.g. designer, generated, etc.

```csharp
// Located in Task.cs
public partial class Task
{
}
// Located in Task.generated.cs
public partial class Task
{
}
```

**_Why: consistent with the Microsoft practices. Files are alphabetically sorted and partial classes remain adjacent._**

#### 14. Do organize namespaces with a clearly defined structure:

```csharp
// Examples
namespace Company.Product.Module.SubModule
{
}
namespace Product.Module.Component
{
}
namespace Product.Layer.Module.Group
{
}
```

**_Why: consistent with the Microsoft's .NET Framework. Maintains good organization of your code base._**

**[⬆ back to top](#table-of-contents)**

#### 15. Do vertically align curly brackets:

```csharp
// Correct
class Program
{
  static void Main(string[] args)
  {
    //...
  }
}
```

Add in single line return if

```csharp
  if(true)
    return true;
```

**_Why: Microsoft has a different standard, but developers have overwhelmingly preferred vertically aligned brackets._**

#### 16. Do declare all member variables at the top of a class, with static variables at the very top.

```csharp
// Correct
public class Account
{
  public static string BankName;
  public static decimal Reserves;
  public string Number { get; set; }
  public DateTime DateOpened { get; set; }
  public DateTime DateClosed { get; set; }
  public decimal Balance { get; set; }
  // Constructor
  public Account()
  {
    // ...
  }
}
```

**_Why: generally accepted practice that prevents the need to hunt for variable declarations._**

#### 17. Do use singular names for enums. Exception: bit field enums.

```csharp
// Correct
public enum Color
{
  Red,
  Green,
  Blue,
  Yellow,
  Magenta,
  Cyan
}
// Exception
[Flags]
public enum Dockings
{
  None = 0,
  Top = 1,
  Right = 2,
  Bottom = 4,
  Left = 8
}
```

**_Why: consistent with the Microsoft's .NET Framework and makes the code more natural to read. Plural flags because enum can hold multiple values (using bitwise 'OR')._**

**[⬆ back to top](#table-of-contents)**

#### 18. Do not explicitly specify a type of an enum or values of enums (except bit fields):

```csharp
// Don't
public enum Direction : long
{
  North = 1,
  East = 2,
  South = 3,
  West = 4
}
// Correct
public enum Direction
{
  North,
  East,
  South,
  West
}
```

**_Why: can create confusion when relying on actual types and values._**

#### 19. Do not use an "Enum" suffix in enum type names:

```csharp
// Don't
public enum CoinEnum
{
  Penny,
  Nickel,
  Dime,
  Quarter,
  Dollar
}
// Correct
public enum Coin
{
  Penny,
  Nickel,
  Dime,
  Quarter,
  Dollar
}
```

**_Why: consistent with the Microsoft's .NET Framework and consistent with prior rule of no type indicators in identifiers._**

**[⬆ back to top](#table-of-contents)**

#### 20. Do not use "Flag" or "Flags" suffixes in enum type names:

```csharp
// Don't
[Flags]
public enum DockingsFlags
{
  None = 0,
  Top = 1,
  Right = 2,
  Bottom = 4,
  Left = 8
}
// Correct
[Flags]
public enum Dockings
{
  None = 0,
  Top = 1,
  Right = 2,
  Bottom = 4,
  Left = 8
}
```

**_Why: consistent with the Microsoft's .NET Framework and consistent with prior rule of no type indicators in identifiers._**

#### 21. Do use suffix EventArgs at creation of the new classes comprising the information on event:

```csharp
// Correct
public class BarcodeReadEventArgs : System.EventArgs
{
}
```

**_Why: consistent with the Microsoft's .NET Framework and easy to read._**

#### 22. Do name event handlers (delegates used as types of events) with the "EventHandler" suffix, as shown in the following example:

```csharp
public delegate void ReadBarcodeEventHandler(object sender, ReadBarcodeEventArgs e);
```

**_Why: consistent with the Microsoft's .NET Framework and easy to read._**

#### 23. Do not create names of parameters in methods (or constructors) which differ only by the register:

```csharp
// Avoid
private void MyFunction(string name, string Name)
{
  //...
}
```

**_Why: consistent with the Microsoft's .NET Framework and easy to read, and also excludes possibility of occurrence of conflict situations._**

**[⬆ back to top](#table-of-contents)**

#### 24. DO use two parameters named sender and e in event handlers. The sender parameter represents the object that raised the event. The sender parameter is typically of type object, even if it is possible to employ a more specific type.

```csharp
public void ReadBarcodeEventHandler(object sender, ReadBarcodeEventArgs e)
{
  //...
}
```

**_Why: consistent with the Microsoft's .NET Framework_**

**_Why: consistent with the Microsoft's .NET Framework and consistent with prior rule of no type indicators in identifiers._**

#### 25. Do use suffix Exception at creation of the new classes comprising the information on exception:

```csharp
// Correct
public class BarcodeReadException : System.Exception
{
}
```

**_Why: consistent with the Microsoft's .NET Framework and easy to read._**

#### 26. Do use suffix Any, Is, Have or similar keywords for boolean identifier :

```csharp
// Correct
public static bool IsNullOrEmpty(string value) {
    return (value == null || value.Length == 0);
}
```

**_Why: consistent with the Microsoft's .NET Framework and easy to read._**

## Offical Reference

1. [MSDN General Naming Conventions](<http://msdn.microsoft.com/en-us/library/ms229045(v=vs.110).aspx>)
2. [DoFactory C# Coding Standards and Naming Conventions](http://www.dofactory.com/reference/csharp-coding-standards)
3. [MSDN Naming Guidelines](http://msdn.microsoft.com/en-us/library/xzf533w0%28v=vs.71%29.aspx)
4. [MSDN Framework Design Guidelines](http://msdn.microsoft.com/en-us/library/ms229042.aspx)

**[⬆ back to top](#table-of-contents)**
