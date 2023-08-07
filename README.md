# API Simples em .NET 6 que roda como uma AWS Lambda quando publicada na AWS

Este projeto é um exemplo de uma API simples em ASP.NET 6 WEB API e o objetivo foi de transformar uma API funcional em uma AWS Lambda com o mínimo de alterações possíveis.

Para isso utilizei a biblioteca "Amazon.Lambda.AspNetCoreServer.Hosting" que permite que o ASP.NET Core seja executado em uma função do AWS Lambda quando implantado. Quando executado local, o funcionamento é de uma API normal.

A linha responsável por tornar a API compatível com a AWS Lambda é a seguinte (se encontra no arquivo 'Program.cs'):

```csharp
builder.Services.AddAWSLambdaHosting(LambdaEventSource.HttpApi);
```

## Pré-requisitos

Certifique-se de ter os seguintes softwares instalados em sua máquina:

- [.NET 6 SDK](https://dotnet.microsoft.com/download/dotnet/6.0)
- Um editor de código de sua escolha (recomendado: Visual Studio)

## CI/CD

Qualquer commit na branch `main` dispara um pipeline realiza o build e deploy da API na AWS como uma Lambda Function.


