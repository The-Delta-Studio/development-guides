# The Delta Studio Backend Guide

*This guide documents eveything needed to work within The Delta Backend team, including tools, templates, style guides, commonly used packages and 3rd party software.*

## Templates

*Commonly used templates developed and maintained by employees of The Delta Studio.*

- [Dotnet core 3.1 C# API](https://github.com/The-Delta-Studio/tds-dotnet-core-3.1-api-template)
- [Dotnet core 2.2 C# API](https://github.com/The-Delta-Studio/tds-api-template)
- [Dotnet core AWS Lambda function with dipendancy injection](https://github.com/The-Delta-Studio/tds-func-lambda-di-ef-template)
- [Dotnet core AWS Lambda function](https://github.com/The-Delta-Studio/tds-func-lambda-template)

## Style guides

*The Delta Studio style guides based on best practices.*

- [C#](/c_sharp)

## Commonly used tools

*Tools often used at The Delta with devepor notes and documentation compiled and derived from extensive use.*

#### [Identity](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity?view=aspnetcore-3.1&tabs=visual-studio)

ASP.NET Core package that supports user handeling. Manages users, passwords, profile data, roles, claimes, ect.

#### [Swagger](https://swagger.io/solutions/api-documentation/)

Swagger is a API documentation handler that helps generate usefull API documentation dirrectly from the API code.

##### Aditional

- Implementation [guide](https://docs.microsoft.com/en-us/samples/aspnet/aspnetcore.docs/getstarted-swashbuckle-aspnetcore/?tabs=visual-studio) for effective API documentation.


#### [Sendgrid](https://sendgrid.com/)

Integratable email distribution service enable our APIs to send emails with dynamically populated data. 

##### Notes/Lessons

1. **DELAYED SENDING:** Emails can sometime be quite delayed which may cause issues.
2. **ACCOUNT WARMUP:** Accounts need to be 'warmed up'. This is done by sending multiple small batches of emails over a period of days. The purpose of this is to prevent the 'account' being blocked by email providers (when larger volumes of emails are sent) causing emails to not reach the intended recipients.

##### Aditional

- C# client [library](https://www.nuget.org/packages/Sendgrid/) to aid integration.

#### [Hangfire](https://docs.hangfire.io/en/latest/)

A framework that allows tasks or processes to be offloaded to background proccessing. Support recurring, delayed, fire-and-forget, and more.

##### Aditional

- C# [package](https://www.nuget.org/packages/Hangfire/)

#### [Retool](https://docs.retool.com/docs)

A tool that can be used to quickly and easily create a Frontend that can interact with an API or database. Often used to create admin portals.

#### [PugPdf](https://www.npmjs.com/package/pug-pdf)

Package to handle PDFs, in particular HTML to PDF conversions.

##### Notes/Lessons

1. PDF handling can cause majour headaches if packages are not chosen with care.

##### Additional

- Example docker [file](/example-files/YomaDockerFile) with Pug PDF issue fixes contained.

___