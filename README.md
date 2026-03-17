# Miniguia-java-oo-notebooklm
Desafio DIO -  Lupo - Primeiros Passos com Inteligência Artificial

1. Miniguia-java-oo-notebooklm

📑 Contexto e Objetivos
O foco é o aprendizado de Programação Orientada a Objetos (POO) em Java aplicado a um Estudo de Caso real.

Objetivo: Consolidar conceitos de classes, objetos, herança e polimorfismo através da análise guiada por IA.

📚 Curadoria de Fontes
Liste os arquivos que você subiu no NotebookLM:

PDF 1: Introdução a Java e Orientação a Objetos (Teoria).

PDF 2: Estudo de Caso [Nome do Caso] (Prática).

(Opcional) Adicione um link para a documentação oficial da Oracle sobre Java como terceira fonte.

2. Engenharia de Prompts (Cicatrizes de Prompt)

• #Pergunta (Prompt)
"Com base no PDF de Java, explique o conceito de Polimorfismo usando exemplos do PDF de Estudo de Caso."
• Intenção
Relacionar teoria e prática.
• Resultado/Dificuldade
A IA foi genérica. Tive que pedir para detalhar o código.

{
	O **polimorfismo**, um dos pilares da Programação Orientada a Objetos, é definido como a capacidade de um mesmo método apresentar comportamentos diferentes. No Java, este conceito é implementado principalmente de duas formas: Polimorfismo de Tempo de Compilação (Sobrecarga de Método) e Polimorfismo de Tempo de Execução (Sobrescrita de Método).

Utilizando o estudo de caso do e-commerce "Amantes das Cervejas", podemos explicar esses conceitos da seguinte forma:

### 1. Polimorfismo de Tempo de Compilação (Sobrecarga ou Overloading)
A sobrecarga ocorre quando múltiplos métodos na mesma classe possuem o **mesmo nome, mas parâmetros diferentes** (em quantidade ou tipo).

*   **Exemplo do Estudo de Caso:** O sistema permite que o cliente realize buscas por diferentes critérios, como o fabricante, o nome da cerveja ou a faixa de preço.
*   **Aplicação em Java:** Na implementação, poderíamos ter vários métodos chamados `pesquisarCerveja()`. Um método receberia apenas uma `String nome`, outro receberia `String fabricante` e um terceiro poderia receber `double precoMin, double precoMax`. O compilador decide qual método chamar com base nos argumentos fornecidos pelo usuário no momento da busca.

### 2. Polimorfismo de Tempo de Execução (Sobrescrita ou Overriding)
A sobrescrita acontece quando uma subclasse fornece uma **implementação específica** para um método que já foi definido em sua superclasse. O método que será executado é determinado apenas durante a execução, com base no tipo real do objeto.

*   **Exemplo do Estudo de Caso:** O processo de pagamento varia dependendo da escolha do cliente: se for via cartão de crédito, o sistema solicita autorização à operadora; se for via boleto, o sistema emite o documento.
*   **Aplicação em Java:** Poderíamos ter uma superclasse genérica chamada `Pagamento` com um método `processarPagamento()`. As subclasses `PagamentoCartao` e `PagamentoBoleto` herdariam de `Pagamento` e **sobrescreveriam** o método `processarPagamento()` para executar suas lógicas específicas (validar dados do cartão vs. gerar código de barras).

Este conceito está estritamente ligado à **Generalização**, representada nos diagramas de caso de uso, onde elementos "filhos" herdam e especializam características de elementos "base". No estudo de caso, isso permite que o sistema trate diferentes formas de pagamento de maneira uniforme, chamando o mesmo método `processarPagamento()`, enquanto o Java garante que a ação correta seja executada para cada tipo de transação.
}

• #Pergunta (Prompt)
"Com base no PDF de Java, explique o conceito de herança usando exemplos do PDF de Estudo de Caso."
• Intenção
Relacionar teoria e prática.
• Resultado/Dificuldade
A IA foi genérica. Tive que pedir para detalhar o código.

{
	A **herança** é um dos quatro pilares da Programação Orientada a Objetos e consiste no processo em que uma classe adquire todas as propriedades (variáveis) e comportamentos (métodos) de outra. Esse conceito permite criar uma nova classe baseada em uma já existente, promovendo a **reutilização de código** e evitando a duplicidade.

No contexto do estudo de caso e da modelagem de sistemas, a herança está diretamente ligada ao relacionamento de **Generalização**, onde um elemento "herdeiro" (filho) possui particularidades em relação a um elemento "base" (pai) mais genérico.

Abaixo, explicamos como a herança pode ser aplicada usando exemplos do e-commerce "Amantes das Cervejas":

### 1. Herança entre Atores (Usuários)
O estudo de caso identifica diferentes papéis que interagem com o sistema, como o **Cliente**, o **Gerente** e o **Funcionário**.
*   **Aplicação:** Em Java, poderíamos ter uma classe pai chamada `Usuario` (ou `Pessoa`) contendo atributos comuns como `nome`, `telefone` e `CPF`.
*   **Especialização:** As classes `Cliente` e `Funcionario` usariam a palavra-chave **`extends`** para herdar esses atributos da classe `Usuario`. O `Gerente` poderia ser uma subclasse de `Funcionario`, herdando suas características básicas, mas adicionando comportamentos específicos, como o login com senha de administrador.

### 2. Herança em Formas de Pagamento
O sistema permite que o cliente selecione diferentes formas de pagamento para finalizar a compra.
*   **Aplicação:** Poderíamos definir uma superclasse genérica chamada `Pagamento`.
*   **Especialização:** As classes `PagamentoCartao` e `PagamentoBoleto` herdariam de `Pagamento`. Enquanto a classe base conteria o valor total calculado pelo sistema, as subclasses teriam atributos específicos: `PagamentoCartao` teria dados como número e operadora, enquanto `PagamentoBoleto` focaria na emissão do documento.

### Principais Regras e Benefícios no Java:
*   **Palavra-chave `extends`:** É utilizada para estabelecer a relação de herança entre a subclasse (filho) e a superclasse (pai).
*   **Acesso a membros:** A subclasse pode acessar métodos e variáveis da classe pai (exceto se forem privados), podendo inclusive utilizar a palavra-chave **`super`** para invocar comportamentos imediatos da classe superior.
*   **Herança Simples:** O Java não suporta herança múltipla de classes (uma classe ter dois pais), garantindo que cada classe herde diretamente de apenas uma superclasse para evitar ambiguidades.

Ao aplicar a herança no estudo de caso, o desenvolvedor garante que funções comuns, como o cálculo de preço total ou o armazenamento de dados básicos do cliente, não precisem ser reescritas para cada variação do sistema, seguindo o objetivo de **evitar a duplicação** de lógica.
}

• #Pergunta (Prompt)
"Liste todos os termos técnicos do PDF 2 e crie uma tabela comparativa."
• Intenção
Extração de dados.
• Resultado/Dificuldade
Funcionou bem, mas precisei corrigir a definição de 'Interface'.

{


	Com base no conteúdo do documento sobre conceitos de Java (PDF 2), os principais **termos técnicos** extraídos são os seguintes:

### Lista de Termos Técnicos
*   **Encapsulamento (Encapsulation):** Ocultação de detalhes internos de uma classe e exposição apenas de funcionalidades necessárias através de métodos `get` e `set`.
*   **Herança (Inheritance):** Processo pelo qual uma subclasse (filha) adquire propriedades e comportamentos de uma superclasse (pai).
*   **Polimorfismo (Polymorphism):** Capacidade de um método apresentar comportamentos diferentes através de **Sobrecarga (Overloading)** ou **Sobrescrita (Overriding)**.
*   **Abstração (Abstraction):** Processo de esconder a implementação e mostrar apenas a funcionalidade usando classes abstratas ou **Interfaces**.
*   **Classe e Objeto:** A classe define a estrutura e comportamento (planta), enquanto o objeto é a instância real física da classe.
*   **Construtor (Constructor):** Método invocado automaticamente na criação de um objeto para inicializar variáveis; pode ser padrão ou parametrizado.
*   **Palavras-chave reservadas:**
    *   **`this`:** Refere-se à instância atual da classe.
    *   **`super`:** Invoca variáveis, métodos ou construtores da classe pai imediata.
    *   **`static`:** Define membros que pertencem à classe e não a instâncias individuais, economizando memória.
    *   **`final`:** Impede alterações em variáveis (constantes), métodos (impede sobrescrita) ou classes (impede herança).
*   **Wrapper Classes:** Classes que encapsulam tipos primitivos (como `Integer` para `int`), permitindo o uso de **Autoboxing** e **Unboxing**.
*   **Type Casting:** Conversão de tipos de dados, podendo ser implícita (**Widening**) ou explícita (**Narrowing**).
*   **Exceções (Exceptions):** Eventos que interrompem a execução do programa, tratados com blocos **`try`**, **`catch`**, **`finally`** e a cláusula **`throws`**.
*   **Collections Framework:** Estrutura para gerenciar grupos de objetos, incluindo **ArrayList**, **HashSet** e **HashMap**.

### Tabela Comparativa de Coleções (Collections Framework)
A tabela abaixo compara as três principais estruturas de dados apresentadas no documento:

| Característica | ArrayList | HashSet | HashMap |
| :--- | :--- | :--- | :--- |
| **Interface Implementada** | List | Set | Map |
| **Estrutura de Dados** | Array Dinâmico | Tabela Hash | Pares Chave-Valor em Tabela Hash |
| **Duplicatas** | Permitidas | Não Permitidas | Chaves: Não / Valores: Permitidos |
| **Ordem de Inserção** | Preservada (Indexada) | Não Preservada | Não Preservada |
| **Acesso por Índice** | Permitido | Não Permitido | Não Permitido (Usa chaves) |
| **Valores Nulos** | Múltiplos permitidos | Apenas um permitido | Uma Chave Nula / Múltiplos Valores Nulos |
| **Uso Ideal** | Quando a ordem e o acesso indexado são necessários | Quando elementos únicos são exigidos | Quando mapeamento chave-valor é necessário |
| **Complexidade (Busca)** | O(n) (Linear) | O(1) (Via Hashing) | O(1) para `get(key)` |

### Comparação de Polimorfismo: Sobrecarga vs. Sobrescrita
Outra comparação técnica relevante fornecida pelo material:

| Característica | Sobrecarga (Overloading) | Sobrescrita (Overriding) |
| :--- | :--- | :--- |
| **Localização** | Na mesma classe | Entre classes com relação de herança |
| **Parâmetros** | Devem ser diferentes | Devem ser exatamente iguais |
| **Tipo de Polimorfismo** | Tempo de Compilação | Tempo de Execução |
| **Anotação @Override** | Não requerida | Recomendada |
}


3. Exemplo na Pratica. 

Com base nos conceitos apresentados nos documentos de Java e no estudo de caso de e-commerce, aqui está um exemplo de código que ilustra **Herança** e as duas formas de **Polimorfismo** (sobrecarga e sobrescrita):

```java
// HERANÇA: Classe base genérica conforme o estudo de caso
class Pagamento {
    double valorTotal;

    // Construtor para inicializar o valor
    Pagamento(double valorTotal) {
        this.valorTotal = valorTotal;
    }

    // Método que será alvo de POLIMORFISMO DE TEMPO DE EXECUÇÃO (Sobrescrita)
    void processarPagamento() {
        System.out.println("Processando pagamento genérico de R$ " + valorTotal);
    }
}

// HERANÇA: Classe filha que adquire propriedades da classe pai usando 'extends'
class PagamentoCartao extends Pagamento {
    
    PagamentoCartao(double valorTotal) {
        super(valorTotal); // Invoca o construtor da classe pai
    }

    // POLIMORFISMO DE TEMPO DE EXECUÇÃO (Method Overriding): 
    // A subclasse fornece uma implementação específica para o método da superclasse
    @Override
    void processarPagamento() {
        System.out.println("Solicitando autorização à operadora para o valor de R$ " + valorTotal);
    }

    // POLIMORFISMO DE TEMPO DE COMPILAÇÃO (Method Overloading):
    // Mesmo nome de método, mas parâmetros diferentes (tipo ou quantidade)
    void validarCartao(String numero) {
        System.out.println("Validando cartão número: " + numero);
    }

    void validarCartao(String numero, int cvv) { // Sobrecarga do método acima
        System.out.println("Validando cartão: " + numero + " com código de segurança: " + cvv);
    }
}

// Outra aplicação de HERANÇA para o cenário de boleto
class PagamentoBoleto extends Pagamento {
    
    PagamentoBoleto(double valorTotal) {
        super(valorTotal);
    }

    // Sobrescrita para o comportamento específico de emitir boleto
    @Override
    void processarPagamento() {
        System.out.println("Gerando boleto bancário no valor de R$ " + valorTotal);
    }
}

public class Main {
    public static void main(String[] args) {
        // Exemplo de POLIMORFISMO (Capacidade de um método apresentar comportamentos diferentes)
        
        // Objeto do tipo Pagamento referenciando um PagamentoCartao
        Pagamento pg1 = new PagamentoCartao(150.00); 
        
        // Objeto do tipo Pagamento referenciando um PagamentoBoleto
        Pagamento pg2 = new PagamentoBoleto(150.00);

        // O método executado é determinado em tempo de execução com base no tipo real do objeto
        pg1.processarPagamento(); // Saída: Solicitando autorização à operadora...
        pg2.processarPagamento(); // Saída: Gerando boleto bancário...

        // Exemplo de Sobrecarga (Overloading) chamado explicitamente
        PagamentoCartao cartao = new PagamentoCartao(100.0);
        cartao.validarCartao("1234-5678"); // Chama a versão com 1 parâmetro
        cartao.validarCartao("1234-5678", 123); // Chama a versão com 2 parâmetros
    }
}
```

### Explicação dos Conceitos no Código:

1.  **Herança (`extends`):** As classes `PagamentoCartao` e `PagamentoBoleto` herdam os atributos (como `valorTotal`) e métodos da classe `Pagamento`, evitando a duplicação de código.
2.  **Polimorfismo de Tempo de Execução (Sobrescrita/Overriding):** O método `processarPagamento` existe na classe pai, mas cada classe filha possui sua própria "versão". No `main`, o Java decide qual versão chamar dependendo se o objeto é um cartão ou um boleto.
3.  **Polimorfismo de Tempo de Compilação (Sobrecarga/Overloading):** O método `validarCartao` possui duas assinaturas diferentes dentro da mesma classe (uma recebe apenas o número e outra recebe o número e o CVV). O compilador sabe qual usar pela quantidade de argumentos passados.


4. Glossário de Conceitos:

Classe: O molde/planta do objeto.
Objeto: A instância real da classe.
Herança: Reuso de comportamento de classes pai.
