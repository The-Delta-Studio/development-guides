# The Delta Studio Backend Guide

This guide documents eveything needed to work within The Delta Backend team, including tools, templates, style guides, commonly used packages and 3rd party software.

## Templates

Below are a list of templates commonly used templates.

- (Dotnet core 3.1 C# API)[https://github.com/The-Delta-Studio/tds-dotnet-core-3.1-api-template]
- (Dotnet core 2.1 C# API)[https://github.com/The-Delta-Studio/tds-api-template]

- (Dotnet core AWS Lambda function)[https://github.com/The-Delta-Studio/tds-func-lambda-di-ef-template]

## Style guides

- [C#](/c_sharp)

## Commonly used tools

### [Identity](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity?view=aspnetcore-3.1&tabs=visual-studio)

ASP.NET Core package that supports user handeling. Manages users, passwords, profile data, roles, claimes, ect.

### [Sendgrid](https://sendgrid.com/)

Integratable email distrobution service enable our APIs to send emails with dynamically populated data.

#### Notes/Lessons

1. Emails can sometime be quite delayed which may cause issues.
2. Accounts need to be 'warmed up'. This is done by sending multible small batches of emails over a period of days. The purpose of this is to prevent the 'account' being blocked by email providers (when larger volumes of emails are sent) causing emails to not reach the intended recipients.

### [Hangfire](https://docs.hangfire.io/en/latest/)

A framework that allows tasks or processes to be offloaded to background proccessing. Support recurring, delayed, fire-and-forget, and more.

### [Swagger](https://swagger.io/solutions/api-documentation/)

Swagger is a API documentation handler that helps generate usefull API documentation dirrectly from the API code.

#### Aditional Documentation

- Implementation (guide)[https://docs.microsoft.com/en-us/samples/aspnet/aspnetcore.docs/getstarted-swashbuckle-aspnetcore/?tabs=visual-studio] for effective API documentation.

### [Retool](https://docs.retool.com/docs)

A tool that can be used to quickly and easerly create a Frontend that can interact with an API or database. Often used to create admin portals.