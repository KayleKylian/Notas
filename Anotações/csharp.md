# Anotações Gerais sobre C#
Anotações simples e diretas sobre C#, com foco em simplicidade e clareza.

## Descrição
C# é uma linguagem orientada a objetos(OOP), imperativa, e estaticamente tipada, contando com o suporte da plataforma de desenvolvimento .NET, desenvolvida e mantida pela Microsoft, proprietária tanto da linguagem, quanto da plataforma.
___

## Escopo de um programa
O escopo de um programa é tudo que ele tem, precisa, para ser executado, e no .NET, nós temos:
- Importações: Referentes aos módulos necessários para o funcionamento do programa, por exemplo: um módulo para a escrita\leitura de arquivos JSON.
- Namespace: São separações lógicas, internas do programa, diferente da separação física, que é em arquivos, pastas.
- Classe
- Método Principal (Método `Main`)
As importações são feitas através de namespaces.
___
## Namespace
Como citado, o namespace é a divisão lógica de um programa, diferentemente de uma divisão física, que se dá por meio de pastas, arquivos.
Semelhante a pastas ou arquivos, que não se pode ter um com o mesmo nome, no namespace não é diferente, onde não se pode ter uma classe com o mesmo nome no mesmo namespace.
Uma das diretrizes é que o namespace tenha o mesmo nome que sua pasta e que haja somente um namespace e classe por arquivo.
É possível reutilizar namespaces e conter um namespace dentro de outro utilizando o `.`, e.g.
```cs
# Cadastro.cs
namespace Cadastro
{
    # bla bla bla...
}
```
```cs
# Pessoa.cs
namespace Cadastro.Pessoa
{
    # bla bla bla...
}
```
___
## Variáveis
**As variáveis são divididas em dois tipos, variáveis de referência, ou variáveis de valor**  

- As variáveis de referência(ou instância) não contém o valor em sí, elas possuem somente o identificador do local de armazenamento do valor, sendo um exemplo desse tipo, as classes.  
- Já as variáveis de valor, armazenam em sí mesmo seus referidos valores, como um exemplo, uma variável do tipo `int`

*Variáveis podem ter níveis de acessibilidade*  

### Nomenclatura
Para nomes de variáveis, segue-se o padrão de nomenclatura camelCase, onde se inicia a primeira palavra em minúsculas, e todas as subsequentes a primeira letra em maiúscula.  

Entretanto há outros estilos de nomenclatura, como e.g., o padrão snake_case, onde todas as palavras são em minúsculas, porém separadas entre sublinhados( _ ).

___

## Tipos de dados
Há diversos tipos de dados para as mais variadas situações, por exemplo, para casos do tipo monetário, usa-se o tipo decimal por conta de sua maior precisão de ponto flutuante.

1. String - Define-se usando aspas duplas e a *keyword* `string`, também conhecida como *cadeia de caracteres* ou *literal*, e.g.:
```cs
string minhaVariávelLiteral = "Minha string";
```

2. Char - Enquanto uma string é uma cadeia de caracteres, o tipo `char` é unicamente um caractere, e define-se usando aspas simples, contrário do tipo string, e.g.: 
```cs
char minhaVariávelChar = 'a';
```

3. Inteiro - Define-se usando explicitamente números e usando a *keyword* `int`, e.g.: 
```cs
int minhaVariávelInteira = 15;
```

4. Double - Define-se de modo semelhante ao tipo Inteiro, com a exceção de que suporta números com ponto flutuante, com uma precisão de até 15 à 17 dígitos e usa-se a *keyword* `double`(opcionalmente, adiciona-se a letra `d` após o número), e.g.: 
```cs
double minhaVariávelDouble = 15.25;
```

5. Decimal - Igualmente ao tipo double, suporta ponto flutuante com uma precisão de 28 à 29 dígitos, e usa-se a *keyword* `decimal` e especificar com a letra `m` após o número para declarar de modo explícito ao compilador que se trata de um número decimal,  e.g.: 
```cs
decimal minhaVariávelDecimal = 15.25m;
```

6. Float - Igual ao decimal, porém com uma precisão de ponto flutuante de somente 6 à 9 dígitos, e usa-se a *keyword* `float` e diferentemente do decimal, usa-se a letra `f`, e.g.: 
```cs
float minhaVariávelFloat = 15.25f;
```

___

## Níveis de Acessibilidade
**Os níveis de acessibilidade definem o escopo onde determinada variável, função, ou classe é assecível.**

- `public` - Nível de acesso público, podendo ser acessada de qualquer lugar
- `private` - Nível de acesso privado, onde só pode ser acessada dentro da mesma classe
- `private protected` - Nível de acesso privado protegido, é acessível dentro de tipos derivados da classe recipiente, mas somente em seu assemblie recipiente.
- `protected` - Nível de acesso protegido, semelhante ao private, porém pode ser acessada de classes que herdem de seu *pai*
- `internal` - Nível de acesso interno, acessível somente em arquivos no mesmo assemblie.
- `protected internal` - Nível de acesso interno protegido, igual ao internal, com a diferença sendo que é acessível de outro assemblie a partir de tipos que derivem de seu tipo base.
___

## Funções
Funções são determinados blocos de códigos a serem executados sempre que a função for chamada, sua principal funcionalidade é evitar o D.R.Y (Dont Repeat Yourself)  

### Argumentos (ou Parâmetros)
Argumentos são passados na chamada da função, normalmente necessários para sua correta execução
*Argumentos são passados entre parênteses, e.g.*:
```cs
class Person
{
    System.Console.WriteLine(Argumento);
}
```

### Tipo de Retorno
Dependendo do retorno da função, deve-se utilizar diferentes palavras-chaves(keywords)

- Para retornos do tipo string, usa-se a *keyword* `string`
- Para retornos do tipo int, usa-se a *keyword* `int`
- Para retornos do tipo booleano, usa-se a *keyword* `bool`
- Para retornos do tipo decimal, usa-se a *keyword* `decimal`
- Para retornos do tipo double, usa-se a *keyword* `double`
- Para retornos vazios, onde não se retorna nada, usa-se a *keyword* `void`

e.g.:
```cs
public string MeuMetodo()
{
    return "Essa é uma string";
}
```

___

## Classes
As classes são agrupamentos de características comuns e relacionadas, e serve de molde para a criação de objetos, e.g.:
```cs
class Person {}
```
Os nomes das classes seguem o nome dos arquivos em que estão.

### Encapsulamento
Encapsulamento é o ato de esconder dados sensíveis do usuário, e evitar alterações indevidas.
Para alcançar isso, é possível:
* Declarar campos e variáveis como `private`
* Prover métodos `get` e `set` publicos, através de propriedades, para acessar e atualizar o valor de um campo privado.

### Membros
Os membros de um tipo(uma classe, um struct ou um registro) incluem todos os métodos, campos, constantes e propriedades.
No C#, não existem variáveis globais ou métodos como em outras linguagens, como o python.

A lista a seguir inclui todos os vários tipos de membros que podem ser declarados em uma classe, uma struct ou em um registro:   

- Campos
- Constantes
- Propriedades
- Métodos
- Construtores
- Eventos
- Finalizadores
- Indexadores
- Operadores
- Tipos aninhados

#### Propriedades
Propriedades são um dos membros de uma classe que provém um mecanismo flexível para as classes para expor campos privados.

Uma propriedade possui dois acessores: um acessor get(que permite acessar um campo privado), e um acessor set(que permide atualizar o valor de um campo privado).

```cs
class Person
{
    private string name;

    public string Name // Na definição de uma propriedade, é comum atribuir o mesmo nome da variável, porém com a primeira letra maiúscula.
    {
        get { return name; } // É possível omitir o return, pois o próprio compilador efetuará a escrita dele, porém você pode otimizar e definir seu próprio estilo.
        set 
        { 
            if(value != "")
            {
                name = value;
            } 
        } // Desse modo, você pode definir regras para o uso.
    }
}
```

#### Campos/Atributos
Campos são variáveis internas da classe, que armazenam valores referentes a ela, que acompanham sua criação e possivelmente definem seu comportamento, e.g.:
```cs
class Person
{
    string name; // Campo ou Atributo
    int age; // Campo ou Atributo
}
```

#### Construtor
Um construtor é uma função com o mesmo nome da classe que é executado no momento em que a classe for instanciada, e.g.:
```cs
class Person
{
    public Person()
    {
        // Construtor
    }
}
```

#### Métodos
Métodos são funções específicas de uma classe, que resolvem determinado problema relacionado ao objetivo original da classe, e.g.:
```cs
class Person
{
    public string Cumprimento()
    {
        return "Olá, é bom te conhecer";
    }
}
```

##### Sobrecarga de Método
Pode-se nomear mais de um método com o mesmo nome, porém seu número de argumentos deve diferir, e.g.:

```cs
public void MeuMetodo()
{
    bla bla bla
}

public void MeuMetodo(argumento)
{
    bla bla bla
}

public void MeuMetodo(arg1, arg2)
{
    bla bla bla
}
```

### Herança
Classes, porém não structs dão suporte ao conceito de herança. Uma classe que deriva de outra classe, chamada de classe base(ou pai), contém automaticamente todos os membros públicos, internos e protegidos da classe base, exceto seus construtores e finalizadores.   

As classes podem ser declaradas como `abstract`, o que significa que um ou mais dos seus métodos não tem nenhuma implementação. Embora as classes abstratas não podem ser instanciadas diretamente, elas servem como classes bases para outras clases que fornecem a implementação ausente.   
As classes também podem ser declaradas como `sealed` para impedir que outras classes herdem delas.
___

## Interface
Classes, structs, e registros podem implementar várias interfaces, um exemplo simples, seria tratá-los como contratos, onde, caso um tipo a implemente, ele deve, portanto implementar todos os métodos definidos na interface.
___
## Tipos

### Tipos genéricos
Classes, structs e registros podem ser definidos com um ou mais parâmetros de tipo. 