# The Delta Studio Backend C# Style Guide

## Table of Contents

1. [Convention Table](#convention-table)
2. [Types](#types)
3. [Namespaces](#namespaces)
4. [Objects](#objects)
5. [Classes](#classes)
6. [Interfaces](#interfaces)
7. [Identifiers](#identifiers)
8. [Abbreviations](#abbreviations)
9. [Methods & Constructors](#methods--constructors)
10. [Enums](#enums)
11. [Miscellaneous](#miscellaneous)
12. [Resources](#resources)

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

-[2.1](#types--primitives) **Primitives**:

-[2.1.1](#types--primitives--naming) **Naming**:

- Single word primitives are declared with no caps.
- Multiple word primitives are declared as descriptive as possible with meaningful names.
- Boolean primitives are declared with the "any", "has" and "is" keywords.

-[2.1.2](#types--primitives--case) **Case**:

- Single word primitive variables are declared with lower case.
- Multiple word primitive variables are declared in camelCase.
- Do not use screaming caps (uppercase).

-[2.1.3](#types--primitives--declaration) **Declaration**:

Primitive types are declared using their type and not a reference to their type.

```csharp
//Good
int index = 100;
string timeSheet;
bool isCompleted;

//Bad
var index = 100;
var timeSheet;
```

Do not use Hungarian notation or any type declaration to declare primitive types.

```csharp
//Good
int counter;
string name;
//Bad
int iCounter;
string strName;
```

> Why? Consistent with the Microsoft's .NET Framework and Visual Studio IDE makes determining types very easy.

**[⬆ back to top](#table-of-contents)**

-[2.1.4](#types--primitives--access) **Access**:

When accessing a type's static members use the .NET Framework type names

```csharp
//Good
string commaSeparatedNames = String.Join(", ", names);
int index = Int32.Parse(input);

//Bad
string commaSeparatedNames = string.Join(", ", names);
int index = int.Parse(input);
```

> Why? Consistent with the Microsoft's .NET Framework and makes code more natural to read.

-[2.2](#types--complex) **Complex**:

-[2.2.1](#types--complex--naming) **Naming**:

- Use plurals when declaring types with multiple sub types.

```csharp
var vowels = new char[] { 'a', 'e', 'i', 'o', 'u' }
var cars = new List<Car>();
```

-[2.2.2](#types--complex--case) **Case**:

Case sensitivity is the same as for primitive types.

-[2.2.3](#types--complex--declaration) **Declaration**:

Complex types are declared using a reference to their type.

```csharp
//Good
var stream = File.Create(path);
var customers = new Dictionary();

//Bad
System.IO.FileStream stream = File.Create(path);
Dictionary customers = new Dictionary();
```

> Why? Removes clutter, particularly with complex generic types and Visual Studio IDE makes determining types very easy.

## Namespaces

-[3.1](#namespaces--naming) **Naming**:

Organize namespaces with a clearly defined hierarchy

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

**[⬆ back to top](#table-of-contents)**

## Objects

-[4.1](#objects--naming) **Naming**:

- Single word objects are named with an uppercase.
- Multiple word objects are declared as descriptive as possible with meaningful names.
- User noune or noun phrases to name an object.

-[4.2](@objects--case) **Case**:

Use PascalCase when naming objects.

```csharp
var userAddressDetails = new UserAddressDetails();
```

> Why? Consistent with the Microsoft's .NET Framework and easy to read.

-[4.3](#objects--creation) **Creation**:

Use object intialisers to simplify object creation.

```csharp
//Good
var user = new User(){
  FirstName = "Dirk",
  LastName = "Mosters",
  "Email" = "dirk@thedelta.io"
};

//Bad
var user = new User();
user.FirstName = "Dirk";
user.LastName = "Mostert";
user.Email = "dirk@thedelta.io";
```

## Classes

-[5.1](#classes--naming) **Naming**:

Naming convention is the same as for Objects.

-[5.2](#classes--case) **Case**:

Case sensitivity is the same as for Objects.

-[5.3](#classes--membervariables) **Member Variables**:

- All member variables are declared at the top of the class.
- Static variables are declared at the very top.
- The constructor of the class comes after the member variables.

```csharp
public class Account
{
  public static string BankName;
  public static decimal Reserves;
  public string Number { get; set; }
  public DateTime DateOpened { get; set; }
  public DateTime DateClosed { get; set; }
  public decimal Balance { get; set; }

  public Account()
  {
    // ...
  }
}
```

> Why? Generally accepted practice that prevents the need to hunt for variable declarations.

## Interfaces

-[6.1](#interfaces--naming) **Naming**:

Interfaces take the name of the class they are referencing prefixed with the letter I.

```csharp
public class UserAssetholdingService()
{
  public async void Method()
  {

  }
  //
}

public interface IUserAssetholdingService()
{
  void Method();
}
```

> Why? Consistent with the Microsoft's .NET Framework and easy to read.

-[6.2](#interfaces--case) **Case**:

Case sensitivity is the same as for classes except for the prefix I.

```csharp
//Good
public interface IUserAssetholdingService()
{

}
//Bad
public interface Iuserassetholdingservice()
{

}
public interface iUserAssetholdingService()
{

}
```

**[⬆ back to top](#table-of-contents)**

## Identifiers

-[7.1](#identifiers--naming) **Naming**

- Do not use underscores when declaring public identifiers.
- Private identifiers can be prefixed with an underscore.
- Identifiers are declared using camelCase.

```csharp
//Good
public DateTime clientAppointment;
private string _clientName;
//Bad
public TimeSpan time_Left;
```

> Why? Consistent with the Microsoft's .NET Framework and makes code more natural to read (without 'slur'). Also avoids underline stress (inability to see underline).

## Abbreviations

- Avoid using abbreviations except abbreviations commonly used in names such as Id, Xml, Ftp, Uri etc.
- PascalCase applies to abbreviations longer than 2 characters.
- Method arguments can be abbreviated.

```csharp
//Good
UserGroup userGroup;
Assignment employeeAssignment;
//Bad
UserGroup usrGrp;
Assignment empAssignment;
// Exceptions
CustomerId customerId;
XmlDocument xmlDocument;
FtpHelper ftpHelper;
UriPart uriPart;
```

**[⬆ back to top](#table-of-contents)**

## Methods & Constructors

-[9.1](#methods--constructors--naming) **Naming**:

Methods are named as descriptively as possible.

```csharp
public string GetFirstNameOfUser(User user)
{
  return user.FirstName;
}
```

-[9.2](#methods--constructors--case) **Case**:

Methods use CamelCase.

```csharp
//Good
public decimal CalculateWeightedAverageCost(decimal unitBalance, decimal transactionValue, decimal oldWAC)
{
  //
}
//Bad
public decimal calculateWeightedAverageCost(decimal unitBalance, decimal transactionValue, decimal oldWAC)
{
  //
}

```

> Why? consistent with the Microsoft's .NET Framework and easy to read.

-[9.3](#methods--constructors--arguments) **Arguments**:

- Do not name arguments such that only the case is different.
- Arguments can be abbreviated.
- Arguments are in camelCase.

```csharp
//Good
public double CalculateAverage(double num1, double num2, double num3)
{
  return (num1 + num2 + num3) / 3;
}

public class User
{
  public string FirstName { get;set; }
  public string LastName { get;set; }
  public string Email { get;set; }
  public int Age { get; set; }

  public User(string nme, string surnme, string em, double dob)
  {
    FirstName = nme;
    LastName = surnme;
    Email = em;
    Age = DateTime.Year - dob.Year
  }
}

//Bad
private void SomeFunction(string name, string Name)
{
}
```

> Why? Consistent with the Microsoft's .NET Framework and easy to read, and also excludes possibility of occurrence of conflict situations.

**[⬆ back to top](#table-of-contents)**

## Enum

-[10.1](#enums--naming) **Naming**:

Non bitfield enums are named using a singular.

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

> Why? Consistent with the Microsoft's .NET Framework and makes the code more natural to read. Plural flags because enum can hold multiple values (using bitwise 'OR').

-[10.2](#enums--declaration) **Declaration**:

- Do not explicitly specify a type of an enum.

```csharp
//Good
public enum Direction
{
  North,
  East,
  South,
  West
}

//Bad
public enum Direction : long
{
  North = 1,
  East = 2,
  South = 3,
  West = 4
}
```

> Why? Can create confusion when relying on actual types and values..

- Do not use an "Enum" suffix in enum type names.

```csharp
//Good
public enum Coin
{
  Penny,
  Nickel,
  Dime,
  Quarter,
  Dollar
}

// Bad
public enum CoinEnum
{
  Penny,
  Nickel,
  Dime,
  Quarter,
  Dollar
}
```

> Why> Consistent with the Microsoft's .NET Framework and consistent with prior rule of no type indicators in identifiers.

- Do not use "Flag" or "Flags" suffixes in enum type names.

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

> Why: Consistent with Microsoft's .NET Framework and consistent with prior rule of no type indicators in identifiers.

## Miscellaneous

-[11.1](#miscellaneous--brackets) **Vertical Allign Brackets**:

```csharp
//Good
class Program
{
  static void Main(string[] args)
  {
  }
}

//Bad
public class TradeException : Exception { public TradeException(string msg) : base(msg) { } }
```

> Why? Developers have overwhelmingly preferred vertically aligned brackets.

-[11.2](#miscellaneous--if) **Ifs with one return**:

Single line return if if statement has only one line.

```csharp
if(number > 1)
  return true;
```

> Why? Looks cleaner.

**[⬆ back to top](#table-of-contents)**

-[11.3](#miscellaneous--eventargs) **EventArgs**:

Use suffix EventArgs at creation of the new classes comprising the information on event.

```csharp
public class BarcodeReadEventArgs : System.EventArgs
{
}
```

> Why? Consistent with Microsoft's .NET Framework and easy to read.

-[11.4](#miscellaneous--event-handlers) **Event Handlers**:

- Name event handlers (delegates used as types of events) with the "EventHandler" suffix.

```csharp
public delegate void ReadBarcodeEventHandler(object sender, ReadBarcodeEventArgs e);
```

> Why? Consistent with Microsoft's .NET Framework and easy to read.

- Use two parameters named sender and e in event handlers. The sender parameter represents the object that raised the event. The sender parameter is typically of type object, even if it is possible to employ a more specific type.

```csharp
public void ReadBarcodeEventHandler(object sender, ReadBarcodeEventArgs e)
{
}
```

> Why? Consistent with Microsoft's .NET Framework

-[11.5](#miscellaneous--exceptions) **Exceptions**:

Use suffix Exception at creation of the new classes comprising the information of the exception.

```csharp
public class BarcodeReadException : System.Exception
{
}
```

> Why? Consistent with Microsoft's .NET Framework and easy to read.

**[⬆ back to top](#table-of-contents)**

## Resources

1. [MSDN General Naming Conventions](<http://msdn.microsoft.com/en-us/library/ms229045(v=vs.110).aspx>)
2. [DoFactory C# Coding Standards and Naming Conventions](http://www.dofactory.com/reference/csharp-coding-standards)
3. [MSDN Naming Guidelines](http://msdn.microsoft.com/en-us/library/xzf533w0%28v=vs.71%29.aspx)
4. [MSDN Framework Design Guidelines](http://msdn.microsoft.com/en-us/library/ms229042.aspx)

**[⬆ back to top](#table-of-contents)**
