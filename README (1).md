# LINQ em C#

Este repositório contém exemplos e explicações sobre o uso do **LINQ (Language Integrated Query)** em C#. LINQ permite consultar coleções de dados (como listas, arrays, objetos, bancos de dados, XML, etc.) de forma elegante, concisa e fortemente tipada.

## 📚 O que é LINQ?

LINQ é uma funcionalidade da linguagem C# que integra consultas diretamente na linguagem, permitindo manipulação de dados de maneira declarativa, como em SQL, mas dentro do código C#.

## 🚀 Vantagens

- Código mais limpo e legível
- Fortemente tipado (erros são detectados em tempo de compilação)
- Integração com diferentes fontes de dados
- Redução de loops manuais (foreach)

## 🧩 Exemplos Básicos

### 1. Consulta em uma lista de inteiros

```csharp
int[] numeros = { 1, 2, 3, 4, 5, 6 };

var pares = from n in numeros
            where n % 2 == 0
            select n;

foreach (var numero in pares)
{
    Console.WriteLine(numero);
}
```

### 2. LINQ com sintaxe de método

```csharp
var pares = numeros.Where(n => n % 2 == 0);

foreach (var numero in pares)
{
    Console.WriteLine(numero);
}
```

### 3. Filtrando e ordenando uma lista de objetos

```csharp
class Produto
{
    public string Nome { get; set; }
    public double Preco { get; set; }
}

List<Produto> produtos = new List<Produto>
{
    new Produto { Nome = "Mouse", Preco = 50.00 },
    new Produto { Nome = "Teclado", Preco = 100.00 },
    new Produto { Nome = "Monitor", Preco = 800.00 }
};

var resultado = produtos
    .Where(p => p.Preco > 100.00)
    .OrderBy(p => p.Nome);

foreach (var p in resultado)
{
    Console.WriteLine($"{p.Nome} - R${p.Preco}");
}
```

## 🔎 Principais Operadores LINQ

| Categoria         | Operadores                                 |
|------------------|--------------------------------------------|
| Restrição        | `Where`                                    |
| Projeção         | `Select`, `SelectMany`                     |
| Ordenação        | `OrderBy`, `OrderByDescending`             |
| Agrupamento      | `GroupBy`                                  |
| Junção           | `Join`, `GroupJoin`                        |
| Quantidade       | `Count`, `Sum`, `Average`, `Min`, `Max`    |
| Elemento         | `First`, `FirstOrDefault`, `Single`, etc.  |
| Conjuntos        | `Distinct`, `Union`, `Intersect`, `Except` |
| Conversão        | `ToList`, `ToArray`, `ToDictionary`         |

## 🧠 Dicas

- Use `var` para simplificar declarações.
- Use `FirstOrDefault` com cuidado: pode retornar `null`.
- Combine LINQ com expressões lambda para maior flexibilidade.
- Prefira `Any()` a `Count() > 0` por performance.

## 📦 Requisitos

- .NET SDK 6.0 ou superior
- Visual Studio, VS Code ou outro editor compatível com C#

## 🤝 Contribuição

Sinta-se à vontade para enviar exemplos, melhorias ou correções via pull request!

---

> Criado por **Thiago Haubrick da Cruz** — focado em aprender, compartilhar e evoluir com C# e .NET 🚀