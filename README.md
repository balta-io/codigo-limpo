Clean Code ou código limpo se refere a um conjunto de boas práticas na escrita de software que você pode aplicar para obter uma maior legibilidade e manutenabilidade do seu código.

![Clean Code](https://baltaio.blob.core.windows.net/static/images/articles/clean-code_share.jpg "Clean Code")

## Índice
- [Índice](#índice)
- [O que é o Clean Code?](#o-que-é-o-clean-code)
- [Regras gerais](#regras-gerais)
  - [Siga as convenções](#siga-as-convenções)
  - [KISS](#kiss)
  - [Regra do escoteiro](#regra-do-escoteiro)
  - [Causa raiz](#causa-raiz)
- [Regras de design](#regras-de-design)
  - [Mantenha dados de configuração em alto nível](#mantenha-dados-de-configuração-em-alto-nível)
    - [Exemplo](#exemplo)
  - [Polimorfismo no lugar de IFs](#polimorfismo-no-lugar-de-ifs)
    - [Exemplo](#exemplo-1)
  - [Mult-thread](#mult-thread)
    - [Exemplo](#exemplo-2)
  - [Separe os códigos mult-thread](#separe-os-códigos-mult-thread)
    - [Exemplo](#exemplo-3)
  - [Utilize Async como sufixo](#utilize-async-como-sufixo)
  - [Evite configurações desnecessárias](#evite-configurações-desnecessárias)
    - [Exemplo](#exemplo-4)
  - [Utilize injeção de dependência](#utilize-injeção-de-dependência)
    - [Exemplo](#exemplo-5)
  - [Lei de Demeter](#lei-de-demeter)
    - [Exemplo](#exemplo-6)
- [Regras sobre entendimento do código](#regras-sobre-entendimento-do-código)
  - [Seja consistente](#seja-consistente)
    - [Exemplo](#exemplo-7)
  - [Utilize variáveis concisas](#utilize-variáveis-concisas)
    - [Exemplo](#exemplo-8)
  - [Obsessão primitiva](#obsessão-primitiva)
    - [Exemplo](#exemplo-9)
  - [Evite dependências lógicas](#evite-dependências-lógicas)
    - [Exemplo](#exemplo-10)
  - [Evite condicionais negativas](#evite-condicionais-negativas)
    - [Exemplo](#exemplo-11)
- [Regras de nomes](#regras-de-nomes)
  - [Escolha nomes descritivos](#escolha-nomes-descritivos)
    - [Exemplo](#exemplo-12)
  - [Faça distinções significantes](#faça-distinções-significantes)
    - [Exemplo](#exemplo-13)
  - [Utilize nomes pronunciáveis e buscáveis](#utilize-nomes-pronunciáveis-e-buscáveis)
    - [Exemplo](#exemplo-14)
  - [Evite uso excessivo de strings](#evite-uso-excessivo-de-strings)
    - [Exemplo](#exemplo-15)
  - [Não use prefixo ou caracteres especiais](#não-use-prefixo-ou-caracteres-especiais)
    - [Exemplo](#exemplo-16)
- [Regras para funções ou métodos](#regras-para-funções-ou-métodos)
  - [Pequenas e com apenas um objetivo](#pequenas-e-com-apenas-um-objetivo)
    - [Exemplo](#exemplo-17)
  - [Utilize nomes descritivos](#utilize-nomes-descritivos)
    - [Exemplo](#exemplo-18)
  - [Opte por poucos parâmetros](#opte-por-poucos-parâmetros)
    - [Exemplo](#exemplo-19)
  - [Cuidado com efeitos colaterais](#cuidado-com-efeitos-colaterais)
    - [Exemplo](#exemplo-20)
  - [Não tome decisões desnecessárias](#não-tome-decisões-desnecessárias)
    - [Exemplo](#exemplo-21)
- [Regras de comentários](#regras-de-comentários)
  - [Um código bom é expressivo](#um-código-bom-é-expressivo)
  - [Não seja redundante](#não-seja-redundante)
    - [Exemplo](#exemplo-22)
  - [Não feche os comentários](#não-feche-os-comentários)
    - [Exemplo](#exemplo-23)
  - [Evite códigos comentados](#evite-códigos-comentados)
    - [Exemplo](#exemplo-24)
  - [Inteção](#inteção)
    - [Exemplo](#exemplo-25)
  - [Esclarecimento](#esclarecimento)
    - [Exemplo](#exemplo-26)
  - [Consequências](#consequências)
    - [Exemplo](#exemplo-27)
- [Estrutura do código](#estrutura-do-código)
  - [Separe conceitos verticalmente](#separe-conceitos-verticalmente)
    - [Exemplo](#exemplo-28)
  - [Declare variáveis próximas de seu uso](#declare-variáveis-próximas-de-seu-uso)
    - [Exemplo](#exemplo-29)
  - [Agrupe funcionalidades similares](#agrupe-funcionalidades-similares)
    - [Exemplo](#exemplo-30)
  - [Declare funções de cima para baixo](#declare-funções-de-cima-para-baixo)
    - [Exemplo](#exemplo-31)
  - [Mantenha poucas e curtas linhas](#mantenha-poucas-e-curtas-linhas)
    - [Exemplo](#exemplo-32)
  - [Não use alinhamento horizontal](#não-use-alinhamento-horizontal)
    - [Exemplo](#exemplo-33)
  - [Use os espaços em branco corretamente](#use-os-espaços-em-branco-corretamente)
    - [Exemplo](#exemplo-34)
  - [Não quebre a identação](#não-quebre-a-identação)
    - [Exemplo](#exemplo-35)
- [Objetos e estruturas](#objetos-e-estruturas)
  - [Esconda estruturas internas](#esconda-estruturas-internas)
    - [Exemplo](#exemplo-36)
  - [Opte por estrutura de dados](#opte-por-estrutura-de-dados)
    - [Exemplo](#exemplo-37)
  - [Evite usar dados e objetos juntos](#evite-usar-dados-e-objetos-juntos)
  - [Instanciar poucas variáveis](#instanciar-poucas-variáveis)
    - [Exemplo](#exemplo-38)
  - [Classe base não deve saber sobre suas derivadas](#classe-base-não-deve-saber-sobre-suas-derivadas)
    - [Exemplo](#exemplo-39)
  - [Mais métodos, menos tomadas de decisão](#mais-métodos-menos-tomadas-de-decisão)
    - [Exemplo](#exemplo-40)
  - [Evite métodos estáticos](#evite-métodos-estáticos)
- [Testes](#testes)
  - [Um assert por teste](#um-assert-por-teste)
  - [Legível](#legível)
    - [Exemplo](#exemplo-41)
  - [Rápido](#rápido)
    - [Exemplo](#exemplo-42)
  - [Independentes](#independentes)
    - [Exemplo](#exemplo-43)
  - [Repetitível](#repetitível)
    - [Exemplo](#exemplo-44)
- [Code smells](#code-smells)
  - [Rigidez](#rigidez)
  - [Fragilidade](#fragilidade)
  - [Imobilidade](#imobilidade)
  - [Complexidade desnecessária](#complexidade-desnecessária)
  - [Repetição desnecessária](#repetição-desnecessária)
  - [Opacidade](#opacidade)
- [Fontes](#fontes)

## O que é o Clean Code?

Por que estamos falando tanto sobre código limpo (Clean Code) e por que isto é tão importante para nós? De fato a manutenção de um software é tão importante quanto sua construção.

Como relatado por Robert C. Martin em seu livro clássico, *Clean Code*, um Best Seller da nossa área, algumas práticas e visões são importantíssimas para mantermos a *vida* do nosso software.

> **IMPORTANTE** Este artigo não descarta a leitura do livro, que é muito mais denso e profundo sobre o assunto.

As empresas investem milhões em softwares todo ano, mas com tantas mudanças no time e nas tecnologias, como fazer este investimento durar? Como garantir uma boa manutenção, durabilidade, vida ao software? Segundo Uncle Bob, as práticas abaixo são o caminho.


## Regras gerais
### Siga as convenções
Se você começou agora em um projeto ou acabaram de definir suas convenções, siga-as! Se utilizam por exemplo constantes em maiúsculo, enumeradores com **E** como prefixo, não importa! Siga sempre os padrões do projeto.

### KISS
Mantenha as coisas simples! Este conceito vem até de outro livro, e particularmente acho que é a base de uma boa solução. Normalmente tendemos a complicar as coisas que poderiam ser muito mais simples.

Então, Keep It Stupid Simple (Mantenha isto estupidamente simples - KISS)!

### Regra do escoteiro
"Deixe sempre o acamapamento mais limpo do que você encontrou!" O mesmo vale para nosso código. Devolva (Check in) sempre o código melhor do que você o obteve. Se todo desenvolvedor no time tiver esta visão, e devolver um pedacinho de código melhor do que estava antes, em pouco temos teremos uma grande mudança.

### Causa raiz
Sempre procure a causa raiz do problema, nunca resolva as coisas superficialmente. No dia-a-dia, na correria, tendemos a corrigir os problemas superficialmente e não adentrar neles, o que muitas vezes causa o re-trabalho!

Tente sempre procurar a causa raiz e resolver assim o problema de uma vez por todas!

## Regras de design

### Mantenha dados de configuração em alto nível

Algo que toda aplicação tem são suas configurações, como as conhecidas **ConnectionStrings**. Tente sempre deixar estas configurações ou o *parse* delas em um nível mais alto possível.

Evite sobrescrever configurações em métodos dentro de **Controllers** ou algo do tipo. Se possível, mantenha esta passagem no método principal, no início da aplicação e não mexa mais nisto!

#### Exemplo

Em diversas aplicações que trabalho, crio sempre uma classe **Settings** no projeto base e depois no **Startup** das aplicações populo ela com as configurações. Isto garante que não teremos estas configurações sendo escritas em todo lugar e também que não precisaremos do **IConfiguration** que fica no **ASP.NET** em projetos que não são Web.

<small>**MeuProjeto.Domain**</small>
```csharp
public static class Settings {
    public static string ConnectionString { get; set; }
}
```

<small>**MeuProjeto.Api**</small>
```csharp
public Startup(IConfiguration configuration)
{
    Configuration = configuration;
    Settings.ConnectionString = Configuration.GetConnectionString("connectionString");
}
```

<small>**MeuProjeto.Infra**</small>
```csharp
using(var connection = new SqlConnection(Settings.ConnectionString)) {
    ...
}
```

### Polimorfismo no lugar de IFs

Um **IF** ou condicional, como o nome diz, traz uma tomada de decisão a nossa aplicação, o que implica no aumento da complexidade da mesma. No geral devemos evitar o uso excessivo destes.

Nestes cenários, opte sempre pelo [polimorfismo](https://balta.io/blog/orientacao-a-objetos) ao invés de tomar decisão em todo método que cria. 

#### Exemplo

Vamos tomar como base uma classe **Pagamento**, onde temos pagamento via Boleto ou Cartão de Crédito, porém nos pagamentos via Boleto, caso o dia do vencimento seja sábado ou domingo (Final de semana), o mesmo pode ser pago no próximo dia útil.

> **IMPORTANTE** Esta regra não está 100% correta ou eficiente, é apenas uma demonstração

```csharp
public class Pagamento {
    public bool PodeSerPago() {
        if(tipo == ETipoPagamento.Boleto)
        {
            if(vencimento.Day != IsWeekend())
                return true;
        }

        if(tipo == ETipoPagamento.CartaoCredito)
            ...
    }
}
```

Note que temos duas tomadas de decisão dentro do método **PodeSerPago**, onde a primeira se refere apenas a pagamentos do tipo Boleto. Caso hajam mais formas de pagamento futuramente, como tratariamos este código? Encheriamos de **IF**?

A solução mais plausível é derivar da classe base **Pagamento** criando o **PagamentoBoleto** que sobrescreve o método **PodeSerPago**, dando uma nova funcionalidade a ele.

```csharp
public class Pagamento {
    public virtual bool PodeSerPago() {
        ...
    }
}

public class PagamentoBoleto : Pagamento {
    public override bool PodeSerPago() {
        if(vencimento.Day != IsWeekend())
            return true;
    }
}
```

### Mult-thread

Sempre que necessário utilize processamento em Threads separadas. Já temos suporte a multi-threads e paralelismo no C# faz um bom tempo e o próprio Async/Await já ajudam nisso.

#### Exemplo

<small><strong>Sem async/await</strong></small>

```csharp
[HttpGet("cursos")]
public IActionResult Index([FromServices] IContentRepository repository)
{
    ViewBag.Courses = repository.GetContents(EContentType.Course);
    return View();
}
```

<small><strong>Com async/await</strong></small>

```csharp
[HttpGet("cursos")]
public async Task<IActionResult> Index([FromServices] IContentRepository repository)
{
    ViewBag.Courses = await repository.GetContentsAsync(EContentType.Course);
    return View();
}
```

### Separe os códigos mult-thread

Seguindo o mesmo exemplo acima, é uma boa prática manter o que é assíncrono separado do que é síncrono, para não forçar um método a ser ou não assíncrono por conta de outro trecho de código.

#### Exemplo

```csharp
public async Task<IEnumerable<Model>> GetAsync()
{
    var model = new Model();
    model.Courses = await _context.Courses.ToListAsync();
    model.Tags = _context.Courses.ToList(); // Não async
    
    return model;
}
```

### Utilize Async como sufixo

Se um método é assíncrono, utilize sempre o sufixo **async** para identificá-lo.

```csharp
public async Task<IEnumerable<Model>> GetAsync()
```

### Evite configurações desnecessárias

Evite deixar configurações no sistema só por que alguém ainda não definiu como aquilo deve ser. Isto polui o código e traz uma complexidade desnecessária.

#### Exemplo
```csharp
public void ConfiguraUsoMySql() 
{
    // ainda não sabemos se vamos ou não suportar MySQL também
    throw new NotImplementedException();
}
```

### Utilize injeção de dependência

Sempre que possível utilize [injeção de dependência](https://balta.io/blog/dependency-injection), ele vai tornar seu código mais limpo e desacoplado.

#### Exemplo
[![Dependency Injection](https://img.youtube.com/vi/va9wX68lAfA/0.jpg)](https://www.youtube.com/watch?v=va9wX68lAfA "Dependency Injection")


### Lei de Demeter

A Lei de Demeter (LoD) ou princípio do menor conhecimento é um princípio que prega os seguintes pontos.

 * Cada unidade deve ter conhecimento limitado sobre outras unidades: apenas unidades próximas se relacionam. 
 * Cada unidade deve apenas conversar com seus amigos.
 * Não fale com estranhos, apenas fale com seus amigos imediatos

#### Exemplo

```csharp
public class Order() 
{ 
    public Discount Discount { get; set; }
}

public class Discount() 
{ 
    public decimal Amount { get; set; }

    public void Apply() { ... }
}
```

<small><strong>Mau exemplo</strong></small>

```csharp
public class OrderHandler() 
{
    var order = new Order();
    order.Discount.Apply(); // <-
}
```

<small><strong>Bom exemplo</strong></small>

```csharp
public class Order() 
{ 
    public Discount Discount { get; set; }

    public void Place() 
    {
        Discount?.Apply();
    }
}

public class OrderHandler() 
{
    var order = new Order();
    order.Place();
}
```

## Regras sobre entendimento do código

### Seja consistente
Se você executa algo de uma forma, execute todo o resto desta mesma forma. Seja consistente na forma com que aplica o código. Siga sempre o padrão definido.


#### Exemplo
```csharp
// Codificando em inglês
public class CustomerRepository { ... }

// Agora mudou para "portuglês"
public class ProdutoRepository { ... }

// Agora é português
public class RepositorioUnidadeMedida { ... }
```

```csharp
// Utilizou sufixo ASYNC no método assíncrono
public async Task<Product> GetAsync() { ... }

// Agora não usou mais =/
public async Task<Course> Get() { ... }
```

### Utilize variáveis concisas

Opte por variáveis concisas, mesmo que resultem em um nome maior. Elas devem ser auto-explicativas, sem a necessidade de comentários ou informações adicionais.

#### Exemplo
```csharp
// Total do que?
decimal total = 0;

// Total do carrinho de compras
decimal shoppingCartTotal = 0;
```

### Obsessão primitiva

No dia-a-dia tendemos a nos focar apenas em tipos primitivos (Built-in), causando uma obsessão pelos mesmos. Podemos criar e usar objetos de valor (Value Objects) para suprir melhor esta necessidade.

#### Exemplo

<small><strong>Mau exemplo</strong></small>

```csharp
public class Customer 
{
    public string Email { get; set; }

    public Customer 
    {
        // Valida E-mail
    }
}

public class Employee 
{
    public string Email { get; set; }

    public Customer 
    {
        // Valida E-mail novamente
    }
}
```

<small><strong>Bom exemplo</strong></small>

```csharp
// Value Object
public class Email 
{
    public string Address { get; set; }

    public Email 
    {
        // Valida E-mail
    }
}

public class Customer 
{
    public Email Email { get; set; }
}

public class Employee 
{
    public Email Email { get; set; }
}
```

### Evite dependências lógicas

Não escreva métodos cujo funcionamento correto dependa de algo contido em sua classe.

#### Exemplo

<small><strong>Mau exemplo</strong></small>

```csharp
public class Student 
{
    public bool IsSubscriber { get; set; }

    public void Xpto() 
    {
        if(IsSubscriber)
            ... // Só executa se for assinante   
    }
}
```

<small><strong>Bom exemplo</strong></small>

```csharp
public class Student 
{
    ...
}

public class Subscriber : Student
{
    public void Xpto() 
    {
        ...        
    }
}
```

### Evite condicionais negativas

No C# a negação é dada por um sinal de exclamação (**!**) que muitas vezes pode ser imperceptível, ocasionando na má leitura do código.

#### Exemplo

```csharp
// Evite
if(!IsSubscriber) { ... }

// Utilize
if(IsSubscriber) { ... }
```

## Regras de nomes

### Escolha nomes descritivos

Esolher bons nomes para classes, variáveis e métodos é essencial para um código limpo. Lembre-se que se você precisa explicar seu código, então algo pode ser melhorado nele.

#### Exemplo
```csharp
// Evite
var x = 256;

// Duração do que? Qual a métrica?
int duration = 25;

// Muito mais expressivo
int durationInMinutes = 25;
```

### Faça distinções significantes

Utilize sempre nomes nos quais quem estiver lendo seu código possa diferenciar seu significado de outros possíveis nomes.

#### Exemplo
```csharp
// Evite
var salario = 7500M;

// Tem um significado maior
var salarioEmReais = 7500M;
```

### Utilize nomes pronunciáveis e buscáveis

Evite utilizar nomes difíceis de pronunciar ou inventar nomes e conveções para variáveis, classes e métodos. Lembre-se sempre da linguagem ubíquoa e da importância dela no código.

#### Exemplo
```csharp
// Evite
var strTexto = "Meu texto aqui";

// Evite
public void GenerateBoletoInLote() {}

// Evite
public void Cadastry() {}
```

### Evite uso excessivo de strings

Quem nunca perdeu horas procurando um BUG que era apenas um problema de comparação de string? Evite digitar a mesma string várias vezes, utilize constantes para isto.

#### Exemplo

```csharp
// Evite
if(environment == "PROD")
    ...

// Utilize
const string ENV = "PROD";

if(environment == ENV)
    ...
```

### Não use prefixo ou caracteres especiais

Não utilize prefixo com o tipo da variável, classe ou método e NUNCA use espaços ou caracteres especiais nestes itens.

#### Exemplo

```csharp
// Evite
public class clsCustomer { ... }

// Evite
string strNome = "André";

// Evite
var situação - "Pendente";
```

## Regras para funções ou métodos

### Pequenas e com apenas um objetivo

Mantenha suas funções ou métodos o menor possível. É mais fácil ter métodos menores e reutilizáveis do que tudo dentro de um método só.

#### Exemplo

```csharp
// Evite
public void RealizarPedido() 
{ 
    // Cadastra o cliente
    // Aplica o desconto
    // Atualiza o estoque
    // Salva o pedido
}

// Utilize
public void SaveCustomer() { ... }
public void ApplyDiscount() { ... }
public void UpdateInventoy() { ... }
public void PlaceOrder() { ... }
```

### Utilize nomes descritivos

A mesma regra dos nomes anteriormente vista aqui se aplica para este cenário. Mantenha nomes concisos, sem caracteres especiais.

#### Exemplo

```csharp
// Evite
// Calcular o que?
public void Calcular() { ... }

// Utilize
// Calcula o ICMS
public void CalcularICMS() { ... }
```

### Opte por poucos parâmetros

Evite exigir muitos parâmetros para construção do objeto, assim como use e abuse dos **Optional Parameters** do C#.

#### Exemplo

```csharp
// Evite
public void SaveCustomer(string street, string number, string neighborhood, string city, string state, string country, string zipCode) { ... }

// Melhorando
public void SaveCustomer(Address address) { ... }
```

### Cuidado com efeitos colaterais

Evite que uma função altere valores de outra classe sem ser a dela. Isto é chamado de efeito colateral.

#### Exemplo

```csharp
// Evite
public class Order 
{
    public decimal Total { get; set; }
}

var order = new Order();

// Qualquer um fora da classe Order 
// pode atualizar seu total
order.Total = 250; 
```

```csharp
// Utilize
public class Order 
{
    public decimal Total { get; private set; }

    public void CalculateTotal() { ... }
}

var order = new Order();

// Total é privado, ninguém de fora consegue 
// modificá-lo, evitando efeitos colaterais
order.Total = 250; // ERRO
```

### Não tome decisões desnecessárias

Não utilize os famosos "flags" para tomar decisões dentro dos métodos, divida-os em vários métodos ou até mesmo outras classes.

#### Exemplo

```csharp
// Evite
public class CustomerRepository 
{
    public void CreateOrUpdate(Customer customer, bool create)
    {
        if(create)
            ...
        else
            ...
    }
}
```

```csharp
// Utilize
public class CustomerRepository 
{
    public void Create(Customer customer) { ... }
    public void Update(Customer customer) { ... }
}
```

## Regras de comentários

### Um código bom é expressivo

Teoricamente, se você precisa comentar uma parte do seu código, é por que algo está errado com ele, ele não está expressivo o suficiente.

### Não seja redundante

Evite comentários que não fazem sentido algum ao contexto ou cenário.

#### Exemplo

```csharp
// Evite

// Função principal do sistema
public void Main() { ... }
```

### Não feche os comentários

Não há necessidade de fechar os comentários.

#### Exemplo

```csharp
// Evite

// Comentário // <- Desnecessário
public void Main() { ... }
```

### Evite códigos comentados

Não deixe sujeira em seu código, ao invés de deixar algo comentado, remova ele. Hoje temos versionadores de código, você pode "voltar no tempo" facilmente.

#### Exemplo

```csharp
// Evite
public void MinhaFuncao() 
{ 
    // string texto = "1234";
    // public void Metodo() {... }
}
```

### Inteção

Um bom uso de comentários é sobre a intenção de um método, classe ou variável (Variável nem tanto).

#### Exemplo

```csharp
// Utilize

// Retorna a lista de produtos inativos
// para o relatório de fechamento mensal
public IList<Product> ObtemProdutosInativos() 
{ 
    ...
}
```

### Esclarecimento

Outro uso interessante para os comentários são esclarecimentos sobre o código.

#### Exemplo

```csharp
// Utilize
public void CancelarPedido() 
{ 
    // Caso o pedido já tenha sido enviado
    // ele não pode mais ser cancelado.
    if(DataEnvio > DateTime.Now)
    {
        AddNotification("O pedido já foi enviado e não pode ser cancelado");
    }
}
```

### Consequências

Podemos utilizar comentários para alertar sobre trechos do código que podem ter consequências mais sérias. Neste caso recomendo o uso de um comentário em XML mais elaborado.

#### Exemplo

```csharp
// Utilize

/// <summary>
/// ATENÇÃO: Este método cancela o pedido e estorna o pagamento
/// </summary>
public void CancelarPedido() 
{ 
    ...
}
```

## Estrutura do código

### Separe conceitos verticalmente

Mantenha uma estrutura de pastas saudável e organizada. Não precisa criar uma pasta para cada arquivo, mas pode haver uma separação por contexto ou feature.

#### Exemplo

* MeuApp
   * MeuApp.Domain
     * MeuApp.Domain.Contexts
       * MeuApp.Domain.Contexts.PaymentContext
         * MeuApp.Domain.Contexts.PaymentContexts.Entities
         * MeuApp.Domain.Contexts.PaymentContexts.ValueObjects
         * MeuApp.Domain.Contexts.PaymentContexts.Enums
       * MeuApp.Domain.Contexts.AccountContext
         * MeuApp.Domain.Contexts.AccountContext.Entities
         * MeuApp.Domain.Contexts.AccountContext.ValueObjects
         * MeuApp.Domain.Contexts.AccountContext.Enums


### Declare variáveis próximas de seu uso

Não crie todas as variáveis juntas, no começo da class ou método, defina-as próximas de onde serão utilizadas.

#### Exemplo
```csharp
// Evite
var total = 0;

public void CreateCustomer() { ... }

public void CreateOrder() { ... }

public void UpdateCustomer() { ... }

public void CalculateTotal() 
{ 
    total = 250; // <- Só é utilizada aqui
}
```

```csharp
// Utilize
public void CreateCustomer() { ... }

public void CreateOrder() { ... }

public void UpdateCustomer() { ... }

var total = 0;
public void CalculateTotal() 
{ 
    total = 250;
}
```

### Agrupe funcionalidades similares

Se uma função pertence a um grupo dentro de um objeto, mantenha-as sempre por perto.

#### Exemplo

```csharp
// Evite
public void CreateCustomer() { ... } 

public void CheckInventory() { ... }

public void CreateOrder() { ... }

public void UpdateCustomer() { ... }

public void CalculateTotal() { .. }
```

```csharp
// Utilize
public void CreateCustomer() { ... } 
public void UpdateCustomer() { ... }

public void CheckInventory() { ... }
public void CreateOrder() { ... }
public void CalculateTotal() { .. }
```

### Declare funções de cima para baixo

Ordenar as funções também é importante. Além da sua ordem de grandeza, suas assinaturas também devem ter uma boa oganização.

#### Exemplo

```csharp
// Utilize
public void CreateCustomer(string name) { ... } 

public void CreateCustomer(string name, int age) { ... } 

public void CreateCustomer(string name, int age, Address address) { ... } 

public void CreateCustomer(string name, int age, Address address, bool active) { ... } 
```

### Mantenha poucas e curtas linhas

Evite funções com linhas longas ou muitas linhas. Não existe um número correto, mas com certeza quanto mais código em uma função, mais difícil de mantê-la será.

#### Exemplo
```csharp
// Utilize
public void CreateCustomer(string name) 
{ 
    var customer = new Customer(name);
    _repository.Customers.Add(customer);
    _repository.SaveChanges();
} 
```

### Não use alinhamento horizontal

Não há necessidade de alinhar horizontalmente variáveis, constantes ou mesmo propriedades.

#### Exemplo
```csharp
// Evite
private   Long            requestParsingTimeLimit;
protected Request         request;
private   FitNesseContent context;
this.context =            context;
input =                   s.getInputStream()
requestParsingTimeLimit = 900;
```

### Use os espaços em branco corretamente

Utilize espaço em branco para associar ou não itens relacionados. Uma boa IDE já fará este trabalho por você.

#### Exemplo
```csharp
// Utilize
private void meuMetodo(String parametro) {
  variavel++;
  int outraVariavel = algumArray.length();
  total += algumMetodo();
  outraClasse.algumMetodo(variavel, total);
  outroMetodo(total);
}
```

### Não quebre a identação

Este item dispensa comentários. Um código não identado não pode ser enviado para o projeto.

#### Exemplo
```csharp
// Evite
public class MinhaClasse{
var valor=12;
Console.WriteLine(valor);
}
```

## Objetos e estruturas

### Esconda estruturas internas

Este tópico abrange uma discussão extensa. Esconder a estrutura de um objeto, ou seja, privar as propridades relacioadas a dados dele, vai sempre trazer resultados positivos e negativos.

Particularmente, gosto de tornar os <code>SET</code> privados, mas não é uma regra do meu código e não aplico em todas as propriedades. Como consequência, sempre precisamos de mais métodos para manipulação destes valores.

Se os dados não fazem sentido para os objetos externos, não há discussão, mantenha-os privados.

#### Exemplo

```csharp
public class NotificationContext
{
    private List<string> _notifications;

    public void Add(string notification) 
    {
        _notifications.Add(notification);
    }

    public bool IsValid() => _notifications.Any();

    public IEnumerable Notifications { get => _notifications.AsEnumerable(); }
}
```


### Opte por estrutura de dados

Estruturas de dados representam a forma como os dados são organizados, podendo ser uma <code>class</code> ou um <code>struct</code>. Normalmente associamos as <code>struct</code> mais a estrutura de dados do que as classes, mas podemos estruturar dados com qualquer uma delas.

A diferença é que ao usar <code>class</code> (OOP) temos recursos como abstração, herança, polimorfismo, dentre outros.

Particularmente acho que a segmentação em objetos de valor é um ponto chave neste item.

#### Exemplo
```csharp
// Usando estruturas
public struct Email 
{
    public Email(string address) 
    { 
        // Permite apenas E-mails hotmail, gmail, yahoo...
    }

    public string Address { get; private set; }
}

public class Customer
{
    public Email Email { get; private set; }
}
```

```csharp
// Usando classes
public class Email 
{
    public Email(string address) 
    { 
        // Permite qualquer tipo de E-mail
    }

    public string Address { get; private set; }
}

public class CommonEmail : Email
{
    public Email(string address) 
        : base(address)
    { 
        // Permite apenas E-mails hotmail, gmail, yahoo...
    }        
}

public class Customer
{
    public Email Email { get; private set; }
}
```

> Nos dois casos temos estruturas representando um E-mail como objeto de valor, porém no segundo cenário, podemos criar extensões e ter uma maior flexibilidade.

### Evite usar dados e objetos juntos

Este é outro ponto polêmico que muitos interpretam como manter nos objetos apenas propriedades enquanto seus comportamentos ficam em outros objetos.

Particularmente acho que a essência de um objeto é justamente o agrupamento de variáveis e funções (Propriedades e métodos). Neste ponto eu sempre mantenho os comportamentos nas entidades.

Em relação a manter parte com <code>object</code> e parte com <code>struct</code> eu confesso que a maior parte dos meus casos eu uso apenas o <code>object</code>. Pode ser vício ou puro comodismo, mas acho estranho esta mistura.

Talvez uma abordagem que aplique estes conceitos de uma forma legal seja novamente o uso dos **value objects**.

```csharp
// Objeto de valor, representa um endereço, sua estrutura de dados
public class Address
{
    public string ZipCode { get; set; }
    public string Street { get; set; }
    public string Number { get; set; }
    public string Neighborhood { get; set; }
    public string City { get; set; }
    public string State { get; set; }
    public string Country { get; set; }
}

// Objeto do cliente... com seus comportamentos
public class Customer
{
    public Address BillingAddress { get; private set; }
    public Address ShippingAddress { get; private set; }

    public void ChangeBillingAddress(Address address) { ... }
    public void ChangeShippingAddress(Address address) { ... }
}
```

### Instanciar poucas variáveis

Evite instanciar muitas variáveis nos objetos e seus métodos. Faz uso maior das propriedades se possível.

#### Exemplo
```csharp
public class ShoppingCart
{
    public decimal Total { get; private set; }

    public decimal CalculateTotal()
    {
        var total = 0; // Desnecessário
        foreach(var item in Items)
            total += item.Price;
    }
}
```

```csharp
// Melhorando
public class ShoppingCart
{
    public decimal Total { get; private set; }

    private decimal CalculateTotal()
    {        
        foreach(var item in Items)
            Total += item.Price;
    }
}
```

### Classe base não deve saber sobre suas derivadas

Uma classe não deve saber sobre detalhes dos seus filhos. Nas verdade isto me soa tão estranho que não vejo um cenário onde uma classe pai consiga saber detalhes de seus filhos.

#### Exemplo

```csharp
// N/A
```

### Mais métodos, menos tomadas de decisão

Já comentamos bastante isto na parte de OOP dos cursos, mas fica aqui o reforço, sempre opte por ter mais métodos, mais sobrecargas do que tomadas de decisão.

#### Exemplo
```csharp
// Evite
public class Order
{
    public void Pay(CreditCard card)
    {
        if(card == null)
            // Pagamento via boleto

        // Pagamento via cartão
    }
}
```

```csharp
// Utilize
public class Order
{
    public void Pay()
    {
        // Pagamento via boleto
    }

    public void Pay(CreditCard card)
    {
        // Pagamento via cartão de crédito
    }
}
```

### Evite métodos estáticos

Classes e métodos estáticos são difíceis de gerenciar, além de serem compartilhados entre a aplicação como um todo. Imagina que você tem uma classe estática que tem uma lista de notificações, esta lista seria compartilhada entre todas as requisições (Diversos usuários) em seu sistema.

```csharp
// Evite
public static class NotificationContext
{
    public static IList<Notification> Notifications { get; set;}
}
```

```csharp
// Utilize
public class NotificationContext
{
    public IList<Notification> Notifications { get; set;}
}
```

## Testes

### Um assert por teste
Utilize um e apenas um <code>assert</code> por teste. Mais de um assert pode confundir você e comprometer a escrita do seu teste.

```csharp
// Evite
[TestMethod]
public void ShouldReturnTrue 
{
    Assert.AreEqual(true);
    Assert.AreEqual(1);
}
```

```csharp
// Utilize
[TestMethod]
public void ShouldReturnTrue 
{
    Assert.AreEqual(true);
}
```

### Legível
Trate seus testes como parte fundamental do seu código, não secundária. Os testes tem que ser organizados e bem escritos assim como o resto do seu software.

#### Exemplo
```csharp
// N/A
```

### Rápido

Um dos objetivos principais de um teste é cobrir uma pequena porção do nosso código. Normalmente estendemos esta ideia para a maior parte do código possível, ocasionando uma ampla gama de testes de unidade.

Dados estes testes, os mesmo são executados antes da publicação das nossas aplicações, garantindo que não enviaremos nada com bugs para produção.

Porém, em cenários mais críticos, o tempo dos deploys (Publicações) é extremamente importante, e se nossos testes demoram muito, podem impactar negativamente nisto.

#### Exemplo

```csharp
// N/A
```

### Independentes

Os testes não devem depender de entidades externas, nem de outros testes. Neste exemplo, volto a salientar o uso do DI e DIP.

#### Exemplo
[![Dependency Injection](https://img.youtube.com/vi/va9wX68lAfA/0.jpg)](https://www.youtube.com/watch?v=va9wX68lAfA "Dependency Injection")


### Repetitível

Devemos ter a possibilidade de repetir o mesmo teste, mas com parâmetros diferentes.

#### Exemplo
```csharp
[TestMethod]
[DataRow("email@valido.com", "email@balta.io")]
public void ShouldValidateEmail(string email)
{
    Assert.IsTrue(new Email(email).IsValid());
}
```

## Code smells

Code Smells são alguns sintomas que podemos identificar e que nos remetem a uma má aplicação do Clean Code de uma forma geral.

### Rigidez

Seu software é difícil de mudar. Qualquer mudança, por mínima que seja, causa uma cascata de outras mudanças.

### Fragilidade

Uma simples mudança quebra seu software em diversos locais. É o famosos "cobre o pé, descobre a cabeça".

### Imobilidade
Você não consegue reutilizar partes do seu código em outros projetos por que isto requer um esforço gigantes. Em resumo, tudo está muito acoplado.

### Complexidade desnecessária
Você usa padrões e arquiteturas que tornam seu código mais burocrático do que efetivo. É o famoso "e se", onde pensamos em tudo que o software pode ter um dia e já "deixamos tudo pronto".

"E se eu quiser voar com meu carro um dia?", bem, se um dia você quiser voar, aí você constrói as asas, mas se não vai precisar voar agora, foca em construir apenas o carro.

### Repetição desnecessária
Você precisa repetir o mesmo código em diversos lugares.

### Opacidade
Seu código é difícil de entender.

## Fontes
* [Post em Inglês](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29)
* [Livro Clean Code](https://www.amazon.com.br/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM)

<div role="main" id="blog-s1-clean-code-a64fc4d3ec431e108e34"></div>
<script type="text/javascript" src="https://d335luupugsy2.cloudfront.net/js/rdstation-forms/stable/rdstation-forms.min.js"></script>
<script type="text/javascript"> new RDStationForms('blog-s1-clean-code-a64fc4d3ec431e108e34', 'UA-48664517-12').createForm();</script>
