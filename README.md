# Guia Java Básico que precisa saber antes de Orientação a Objetos

Um guia com informações da linguagem e sintaxe de comandos **Java** básicos e mais utilizados.

Como um guia básico, vale ressaltar que não cobre todas as funcionalidades disponiveis na linguagem.

**[Tutoriais Oficiais para Consultas mais Especificas](https://docs.oracle.com/javase/tutorial/java/index.html)**

A maioria das informações foram absorvidas do curso " **[Java COMPLETO Programação Orientada a Objetos +Projetos](https://www.udemy.com/course/java-curso-completo/learn/lecture/10566104#content)** " na Udemy.

## Restrições e Convenções
```java
    Nomes de variáveis:
        Não pode começar com dígito: 1hora, 24horas, 4fun 
        Não pode usar acentos: conexão, número
        Não pode ter espaço em branco: cadastrar pessoa, pagar com cartao
        
        Não recomendado utilizar abreviações: qtd, n, tipoPgmt
        Use nomes que tenha significado: tipoDePagamento

    Convenções:
        lowerCamelCase: pagarComCartaoDeCredito
            - Pacotes
            - Atributos
            - Métodos
            - Variáveis e parâmetros

        PascalCase: CortadorDeGrama
            - Classes
```
## Comentários
```java
    // < Comentário de linha

    /* 
    * Comentário
    * De
    * Bloco
    */

    Os * dentro do bloco são opcionais.
```
## Tipos e Valores Defaults
```java
    Tipos Primitivos:
        boolean: false
        byte, short, int, long:  0
        float, double: 0.0
        char: \u0000

    Tipos Especiais:
        String: ""
```
## Casting
```java
Para fazer casting em Java basta colocaar o tipo entre parênteses antes do valor.
    Sintaxe:
        Tipo Identificador = (Tipo para Casting) Valor;
    Ex:
        int x = (int) 2.5; // x = 2

    ‎Ampliação do Casting (automaticamente) - convertendo um tipo menor em um tamanho de tipo maior‎
    byte -> short -> char -> int -> long -> float -> double

        int myInt = 9;
        double myDouble = myInt; // 9.0 -- Casting automático de int para double

    ‎Estreitando o Casting (manualmente) - convertendo um tipo maior em um tipo de tamanho menor‎
    double -> float -> long -> int -> char -> short -> byte

        double myDouble = 9.0;
        int myInt = (int) myDouble; // Casting manual de double para int

    - REF: https://www.w3schools.com/java/java_type_casting.asp
```
## Caracteres Especiais
```java
    \n Quebra de linha (newline ou linefeed) 
    \r Retorno de carro (carriage return) 
    \b Retrocesso (backspace) 
    \t Tabulação (horizontal tabulation) 
    \f Nova página (form feed) 
    \' Aspas simples (apóstrofo) 
    \" Aspas 
    \\ Barra invertida (“\”) 
    \u233d Caractere unicode de código 0x233d (hexadecimal)
```
## Locale
```java
    import java.util.Locale;

    Locale BRAZIL = new Locale("pt","BR"); - Instânciar com o Locale BR
    Locale.setDefault(BRAZIL); - Definir o Locale
    Locale.setDefault(Locale.US); - Alguns Locale já são padrões e não precisa instânciar
```
## Scanner
```java
    import java.util.Scanner;

    Scanner sc = new Scanner(System.in); - Construir a instância

    char resposta = sc.next().charAt(0); - Ler apenas o primeiro caractere
    char resposta = sc.next(); - Ler apenas a primeira palavra
    char resposta = sc.nextLine(); - Ler uma String
    char resposta = sc.nextInt(); - Ler um número inteiro
    char resposta = sc.nextDouble(); - Ler um número decimal

    sc.close(); - Destruir a instância
```
## Math
```java
    Math.pow(2, 2) | 2 elevado a potencia de 2
    Math.sqrt(18) | raiz quadrada de 18
    Math.abs(-29.234) | Número absoluto de -29.234
    Math.log(123) | log de 123
    Math.max(1123, 456) | retorna o maior de 2 números = 1123
    Math.min(1123, 456) | retorna o menor de 2 números = 456
    Math.floor(123.5647) | retorna o valor sem contar as casas após a virgula = 123.0
    Math.random() | retorna um valor randomico entre 0.0 e 1.0
    Math.round(12.6) | retorna um número inteiro arredondado | 12.6 = 13 | 12.5 = 13 | 12.4 = 12
    Math.sin(14.5) | retorna o seno
    Math.cos(26.98) | retorna o cosseno
    Math.tan(332.54) | retorna a tangente
    ...
    
    - REF: https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html
```
## Strings
```java
    Prints
        println(); Print Line | Concatenação + para usar variáveis
            System.out.println("Texto aqui " + variavel + " mais texto");
        
        printf(); Print formatado | use os tipos abaixo para formatar uma variável
            %s tipo String | System.out.printf("%s", variavelString);
            %c tipo char | System.out.printf("%c", variavelChar);
            %d tipo int | System.out.printf("%d", variavelInt);
            %f tipo float e double / %.2f < 2 = número de casas decimais | System.out.printf("%.2f", variavelDouble);
        
        print(); Sem formatação e Concatenação, apenas um parâmetro, cursor fica na mesma linha.
            System.out.print("Apenas um parâmetro");
            System.out.print(12345678);

    Funções
        Formatar: toLowerCase(), toUpperCase(), trim()
            String str = " Um Texto Qualquer ";
            
            System.out.println(str.toLowerCase()); //  um texto qualquer 
            System.out.println(str.toUpperCase()); //  UM TEXTO QUALQUER 
            
            String x = str.trim(); // Remove os espaços

            System.out.println("-" + str + "-"); // - Um Texto Qualquer -
            System.out.println("-" + x + "-"); // -Um Texto Qualquer-
        
        Recortar: substring(inicio), substring(inicio, fim)
            String str = "123456789";
            System.out.println(str.substring(3)); // 456789
            System.out.println(str.substring(3, 7)); // 4567

        Substituir: replace('char', 'char'), replace("string", "string")
            String str = "uma string qualquer";
            System.out.println(str.replace('a', 'X')); // umX string quXlquer
            System.out.println(str.replace("qualquer", "nova")); // uma string nova

        Buscar: *1 indexOf("string" ou 'char'), *2 lastIndexOf("string" ou 'char')
            *1 Retorna o índice da string ou do caractere
            *2 Retorna o índice da última string ou do último caractere
            
            String str = "uma palavra";
            índice        012345678910

            System.out.println(str.indexOf('a')); // 2
            System.out.println(str.lastIndexOf('a')); // 10

            System.out.println(str.indexOf("uma")); // 0
            System.out.println(str.indexOf(" ")); // 3
            System.out.println(str.lastIndexOf("palavra")); // 4

        Split: split("delimitador") // separa as palavras em um vetor
            String str = "um texto qualquer";
            // índice     0  1     2

            String x[] = str.split(" "); // separa quando acha um espaço em branco

            System.out.println(x[0]); // um
            System.out.println(x[1]); // texto
            System.out.println(x[2]); // qualquer
```
## Operadores
```java
    Aritméticos
        +, -, *, /, %
        
    Lógicos
        &&, ||, !
        
    Condicionais
        >, <, >=, <=, !=, ==
        
    Atribuição
        =
        
    Atribuição cumulativa
        +=, -=, *=, /=, %=
        
    Incrementador e Decrementador
        ++ e --
        
    Bitwise: Operadores que checam binários
        &(AND): Quando TODAS as condições são verdadeiras
            (true & true & true & true) // Verdadeiro
            (true & true & false & true) // Falso
            (true & false & true & true) // Falso
            
        |(OR): Quando PELO MENOS UMA das condições é verdadeira
            (true | false | true | true) // Verdadeiro
            (false | false | false | true) // Verdadeiro
            (false | false | false | false) // Falso
            
        ^(XOR - Ou exclusivo): Quando APENAS uma das condições é verdadeira
            (false ^ false ^ false ^ true) // Verdadeiro
            (true ^ false ^ false ^ true) // Falso
        
        Conversões Binárias:
                89    = 0101 1001
                60    = 0011 1100
            (89 & 60) = 0001 1000 = 24
            (89 | 60) = 0111 1101 = 125
            (89 ^ 60) = 0110 0101 = 101

            if ((89 & 60) == 24) // Verdadeiro

            Obs: para passar um binário direto para uma variável utilize 0b antes do valor:
                int x = 0b1011001; // 89
                System.out.println(0b100000); // 32             
```
## If Else
```java
    If com apenas um comando não precisa de chaves {}
        if (condicao)
            comando;

    If com mais de um comando usa-se chaves como delimitadores {}
        if (condicao) {
            comando
            comando
            ...
            comando
        }

    If com Else
        if (condicao) {
            comando
            comando
            ...
            comando
        } else {
            comando
        }

    If com Else If
        if (condicao) {
            comando
            comando
            ...
            comando
        } else if (condicao) {
            comando
            comando
        } else {
            comando
        }
```
## Switch Case
```java
    switch (var) {
        case condicao1:
            comando;
            break;
        case condicao2:
            comando;
            break;
        case condicao3:
            comando;
            break;
        default:
            comando;
            break;
    }  
```
## Expressão Condicional Ternária
```java
    ( condicao ) ? valor_se_verdadeiro : valor_se_falso;

    Pode ser usada atribuindo valor a uma variável ou em uma saída
        Ex: 
            System.out.println(( 1 == 1 ) ? "Verdadeiro" : "Falso");
        Ou:
            String resultado =  ( 1 == 1 ) ? "Verdadeiro" : "Falso";
```
## While
```java
    Utilizado para quando não se sabe exatamente a quantidade de vezes que o problema irá se repetir

    while ( condicao )
        comando;
    
    Ou:
    
        while ( condicao ) {
            comando
            comando
            comando
        }
    
    Ex:
        int x = 0;
        while( x < 10 )
            x++;
```
## Do While
```java
    O bloco é executado pelo menos 1 vez, pois a verificação condicional só é feita no final.

    do {
        comando
    } while (condicao);

    Ex:
        char resposta;
        Scanner sc = new Scanner(System.in);
        
        do {
            System.out.print("Deseja repetir (s/n)? ");
            resposta = sc.next().charAt(0);
        } while (resposta == 's');

        sc.close();
```
## For
```java
    Utilizado quando se sabe exatamente a quantidade de vezes que o problema irá se repetir
    
    for (inicializador; condicao; manipulador)
        comando;
    
    Ou:

    for (inicializador; condicao; manipulador) {
        comando
        comando
    }

    Ex:
        for (int i = 0; i < 10; i++)
            System.out.println(i);


    -For Each-
        for (Tipo Apelido : Colecao)
            comando

        Ex:
            String[] frutas = {"pera", "maçã", "banana"};
            for (String fruta : frutas)
                System.out.println(fruta);
```
## Funções ou Métodos
```java
    Sintaxe:
        [Encapsulamento] [Tipo] [Identificador] (Tipo Parametro) {
            Bloco de comandos
            return; // O retorno depende do Tipo do método
        }

    Identificadores utilizam o padrão lowerCamelCase

    Modificadores de acesso são:
        public
        protected // Padrão caso nenhum modificador for declarado
        private
    Tipos de retorno:
        Primitivos
        Objeto
        Coleção
        Vazio // (Void) não retorna nada


        Ex:
            public int soma(int a, int b) {
                return a + b;
            }

        Ex de chamada de método:
            int resultado = soma(10, 20) // resultado = 30

        Obs:
            No método também é possivél utilizar a palavra reservada static que define um método estático. Este método é um método da classe e não da instância(Objeto) mas isso será visto em O.O.

            Utilizado por exemplo quando você quer criar um contador de quantas vezes essa classe foi instânciada.

            public static int contador() {
                contador++;
            }
```
## Vetores e Matrizes
```java
Sintaxe:
    Tipo[] Identificador = {valor1, valor2, ..., nVALOR};
    Ou:
    Tipo[] Identificador = new Tipo[TAMANHO DO VETOR];

    Ex:
        String[] frutas = {"pera", "maçã", "banana"};
        Ou:
        String[] frutas = new String[3]; // Cria um vetor de 3 posições com valores Default  
        
        // Para acessar e modificar valores \/
        frutas[0] = "pera";
        frutas[1] = "maçã";
        frutas[2] = "banana";
        System.out.println(frutas[0]); // pera
        System.out.println(frutas[1]); // maçã
        System.out.println(frutas[2]); // banana

        Para adicionar uma matriz basta colocar dois ou mais colchetes dependendo da dimensão da matriz
        String[][] alimentos = new String[2][3]; // Matriz 2/3
        alimentos[0][0] = "pera";
        alimentos[0][1] = "maçã";
        alimentos[0][2] = "banana";
        alimentos[1][0] = "arroz";
        alimentos[1][1] = "feijão";
        alimentos[1][2] = "macarrão";
```
## Listas
```java
import java.util.List;

Sintaxe:
    List<TIPO WRAPPER> Identificador = new CLASSE DE IMPLEMENTACAO<>();
    // CLASSES DE IMPLEMENTACAO: AbstractList, AbstractSequentialList, ArrayList, AttributeList, CopyOnWriteArrayList, LinkedList, RoleList, RoleUnresolvedList, Stack, Vector

    Ex:
        List<String> frutas = new ArrayList<>(); // import java.util.ArrayList;

    Operações:
        add(0, "pera") // adiciona pera na posição 0
        add(1, "uva") // adiciona uva na posição 1
        add(2, "abacaxi")  // adiciona abacaxi na posição 3
        add("morango") // Adiciona morango na primeira posição disponivel
        remove(1) // remove o item uva da posição 1
        clear() // limpa a Lista
        contains("abacaxi") // Retorna true se contem abacaxi na lista
        get(2) // retorna abacaxi o valor do item na posição 2
        set(2, "mamão") // Modifica o item na posição 2
        isEmpty() // Retorna se a lista está vazia
        size() // Retorna o tamanho a lista

        - Consulte o link abaixo para outras operações.

    - REF: https://docs.oracle.com/javase/10/docs/api/java/util/List.html
```
## Palavras Reservadas
```java
Modificadores de acesso:
    private: acesso apenas dentro da classe

    protected: acesso por classes no mesmo pacote e subclasses

    public: acesso de qualquer classe

Modificadores de classes, variáveis ou métodos:
    abstract: classe que não pode ser instanciada ou método que precisa ser implementado por uma subclasse não abstrata

    class: especifica uma classe

    extends: indica a superclasse que a subclasse está estendendo

    final: impossibilita que uma classe seja estendida, que um método seja sobrescrito ou que uma variável seja reinicializada

    implements: indica as interfaces que uma classe irá implementar

    interface: especifica uma interface

    native: indica que um método está escrito em uma linguagem dependente de plataforma, como o C

    new: instancia um novo objeto, chamando seu construtor

    static: faz um método ou variável pertencer à classe ao invés de às instâncias

    strictfp: usado em frente a um método ou classe para indicar que os números de ponto flutuante seguirão as regras de ponto flutuante em todas as expressões

    synchronized:indica que um método só pode ser acessado por uma thread de cada vez

    transient: impede a serialização de campos

    volatile:indica que uma variável pode ser alterada durante o uso de threads

Controle de fluxo dentro de um bloco de código:
    break: sai do bloco de codigo em que ele está

    case: executa um bloco de código dependendo do teste do switch

    continue:pula a execução do código que viria após essa linha e vai para a próxima passagem do loop

    default:executa esse bloco de codigo caso nenhum dos teste de switch-case seja verdadeiro

    do:executa um bloco de código uma vez, e então realiza um teste em conjunto com o while para determinar se o bloco deverá ser executado novamente

    else: executa um bloco de código alternativo caso o teste if seja falso

    for:usado para realizar um loop condicional de um bloco de código

    if: usado para realizar um teste lógico de verdadeiro o falso

    instanceof: determina se um objeto é uma instância de determinada classe, superclasse ou interface

    return: retorna de um método sem executar qualquer código que venha depois desta linha (também pode retornar uma variável)

    switch:indica a variável a ser comparada nas expressões case

    while: executa um bloco de código repetidamente enquanto a condição for verdadeira

Tratamento de erros:
    assert: testa uma expressão condicional para verificar uma suposição do programador

    catch: declara o bloco de código usado para tratar uma exceção

    finally:bloco de código, após um try-catch, que é executado independentemente do fluxo de programa seguido ao lidar com uma exceção

    throw:usado para passar uma exceção para o método que o chamou

    throws: indica que um método pode passar uma exceção para o método que o chamou

    try: bloco de código que tentará ser executado, mas que pode causar uma exceção

Controle de pacotes:
    import:importa pacotes ou classes para dentro do código

    package: especifica a que pacote todas as classes de um arquivo pertencem

Primitivos:
    boolean:um valor indicando verdadeiro ou falso

    byte: um inteiro de 8 bits (signed)

    char: um caracter unicode (16-bit unsigned)

    double: um número de ponto flutuante de 64 bits (signed)

    float: um número de ponto flutuante de 32 bits (signed)

    int: um inteiro de 32 bits (signed)

    long: um inteiro de 64 bits (signed)

    short: um inteiro de 32 bits (signed)

Variáveis de referência:
    super: refere-se a superclasse imediata

    this: refere-se a instância atual do objeto

Retorno de um método:
    void: indica que o método não tem retorno

Palavras reservadas não utilizadas:
    const: Não utilize para declarar constantes; use public static final

    goto: não implementada na linguagem Java por ser considerada prejudicial

Literais reservados:
    De acordo com a Java Language Specification, null, true e false são tecnicamente chamados de valores literais, e não keywords. Se você tentar criar algum identificador com estes valores, você também terá um erro de compilação.

REF: http://www.linhadecodigo.com.br/artigo/83/as-52-palavras-reservadas-do-java.aspx
```
