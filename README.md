# 🎓 SistemaAcadêmico

Projeto desenvolvido em aula com o objetivo de **compreender o funcionamento de Migrations utilizando C# e Entity Framework Core** em um sistema simples conectado a um **banco de dados relacional**.

O sistema foi criado apenas para **fins educacionais**, ajudando a entender como funciona o processo de:

- Criação de Models
- Criação de banco de dados através do código
- Controle de alterações no banco usando **Migrations**
- Integração entre **ASP.NET MVC**, **Entity Framework Core** e **SQL Server**

---

# 📚 Objetivo do Projeto

O projeto **SistemaAcadêmico** foi desenvolvido para demonstrar como uma aplicação pode utilizar **Entity Framework Core** para gerenciar um banco de dados relacional através de código.

Durante o desenvolvimento, foram aplicados conceitos importantes como:

- Programação Orientada a Objetos
- Mapeamento objeto-relacional (ORM)
- Criação de banco de dados via migrations
- Geração automática de controllers e views

---

# 🛠 Tecnologias Utilizadas

Este projeto utiliza as seguintes tecnologias:

| Tecnologia | Descrição |
|-----------|----------|
| **C#** | Linguagem principal utilizada no projeto |
| **ASP.NET MVC** | Framework para desenvolvimento web |
| **Entity Framework Core** | ORM utilizado para comunicação com banco de dados |
| **SQL Server** | Banco de dados relacional |
| **.NET CLI** | Ferramenta de linha de comando do .NET |
| **ASP.NET Code Generator** | Ferramenta para geração automática de Controllers e Views |

---

# 🏗 Estrutura Básica do Projeto

O projeto segue a estrutura padrão de aplicações **ASP.NET MVC**.

```
SistemaAcademico
│
├── Controllers
│
├── Models
│
├── Views
│
├── Data
│   └── ApplicationDbContext
│
├── Migrations
│
└── Program.cs
```

### Descrição das pastas

| Pasta | Função |
|------|------|
| **Models** | Representam as entidades do banco de dados |
| **Controllers** | Contêm a lógica de controle da aplicação |
| **Views** | Interface visual exibida ao usuário |
| **Data / DbContext** | Responsável pela comunicação com o banco |
| **Migrations** | Guarda o histórico de alterações do banco de dados |

---

# 🗄 Entity Framework Core e Migrations

As **Migrations** são responsáveis por controlar as alterações na estrutura do banco de dados.

Elas permitem que o banco seja **criado e atualizado automaticamente a partir dos Models da aplicação**.

---

# ⚙ Criar uma Migration

Para gerar uma migration, utilize o **Console do Gerenciador de Pacotes NuGet** no Visual Studio:

```
Ferramentas → Gerenciador de Pacotes NuGet → Console
```

Comando:

```powershell
Add-Migration NomeDaMigration
```

### Exemplo

```powershell
Add-Migration CriacaoInicial
```

Esse comando irá:

- Criar a pasta **Migrations**
- Gerar arquivos com instruções de criação do banco

---

# 🗄 Atualizar ou Criar o Banco de Dados

Após gerar a migration, é necessário aplicá-la ao banco.

```powershell
Update-Database
```

Esse comando irá:

- Criar o banco de dados caso ele não exista
- Criar tabelas baseadas nos **Models**
- Aplicar alterações pendentes

---

# ⚙ Ferramentas .NET CLI

A **.NET CLI** permite executar ferramentas diretamente pelo terminal.

### Verificar ferramentas instaladas globalmente

```bash
dotnet tool list -g
```

| Parâmetro | Significado |
|----------|-------------|
| `dotnet tool` | Gerencia ferramentas do .NET |
| `list` | Lista ferramentas instaladas |
| `-g` | Mostra ferramentas instaladas globalmente |

---

# 📦 Criar Manifesto de Ferramentas

Para instalar ferramentas **localmente no projeto**, é necessário criar um manifesto.

Execute o comando dentro da pasta do projeto:

```bash
dotnet new tool-manifest
```

Isso irá criar o arquivo:

```
.config/dotnet-tools.json
```

Esse arquivo guarda as ferramentas utilizadas no projeto.

---

# ⚙ Instalar Ferramenta de Code Generation

Ferramenta utilizada para gerar automaticamente **Controllers e Views**.

```bash
dotnet tool install dotnet-aspnet-codegenerator --version 9.0.0
```

---

# 🧩 Gerar Controllers Automaticamente

Caso necessário, é possível gerar controllers via terminal.

Comando:

```bash
dotnet aspnet-codegenerator controller \
-name NomeController \
-m NomeModel \
-dc ApplicationDbContext \
--relativeFolderPath Controllers \
--useDefaultLayout \
--referenceScriptLibraries
```

---

# 📖 Exemplo Utilizado em Aula

```bash
dotnet aspnet-codegenerator controller \
-name CursosController \
-m Curso \
-dc ApplicationDbContext \
--relativeFolderPath Controllers \
--useDefaultLayout \
--referenceScriptLibraries
```

Esse comando cria automaticamente:

- Controller
- Views CRUD
- Integração com Model
- Integração com DbContext

---

# 🎯 Conclusão

O projeto **SistemaAcadêmico** foi criado com o objetivo de demonstrar na prática como funciona o uso de **Migrations no Entity Framework Core** em aplicações ASP.NET.

Com ele foi possível aprender conceitos importantes como:

- Criação de banco de dados via código
- Controle de alterações com migrations
- Estrutura de projetos ASP.NET MVC
- Integração entre aplicação e banco relacional

Este projeto serve como **base de estudo para compreender o funcionamento do Entity Framework e desenvolvimento com ASP.NET MVC**.
