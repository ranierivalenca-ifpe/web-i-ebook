# Desenvolvimento para Web I

1. Introdução
    1. O que é arquitetura cliente-servidor
    1. O que é o protocolo HTTP
    1. O que é PHP
1. Conceitos básicos de PHP
    1. Variáveis
    1. Condicionais
    1. Laços de repetição
    1. Funções
    1. Arrays e laços
    1. Strings
    1. Gerando HTML com PHP
1. CRUD com PHP
    1. O que é CRUD
    1. CRUD usando arquivos CSV
    1. CRUD usando banco de dados MySQL
    1. Implementação de autenticação em operações CRUD
1. Autenticação e sessão com PHP
    1. Cookies
    1. Sessões
    1. Autenticação
    1. Integração de autenticação com as operações CRUD
1. API's com PHP
    1. O que é uma API
    1. Como criar uma API com PHP
    1. Como consumir uma API com PHP
    1. Implementação de autenticação em chamadas de API
1. Svelte como framework front-end
    1. O que é o Svelte
    1. Como instalar o Svelte
    1. Como criar componentes com Svelte
    1. Como consumir APIs com Svelte
    1. Implementação de autenticação em chamadas de API do Svelte para PHP
1. Conclusão
    1. Recapitulando os conceitos aprendidos
    1. Próximos passos para se aprofundar no assunto.

----

## Introdução

### **O que é a arquitetura cliente-servidor**
A arquitetura cliente-servidor é um modelo de computação em que existem dois componentes principais: o cliente e o servidor. O cliente é responsável por solicitar serviços ou informações ao servidor, enquanto o servidor é responsável por fornecer esses serviços ou informações.

O cliente pode ser qualquer dispositivo, como um computador, celular ou tablet, que possa se conectar à rede e enviar solicitações ao servidor. Já o servidor é geralmente um computador com capacidade de processamento e armazenamento maior, que está sempre ligado e conectado à rede.

Existem diferentes tipos de arquitetura cliente-servidor, como a arquitetura de duas camadas, três camadas e N-camadas. Na arquitetura de duas camadas, o cliente se comunica diretamente com o banco de dados, enquanto na arquitetura de três camadas o cliente se comunica com o servidor, que por sua vez se comunica com o banco de dados.

A arquitetura cliente-servidor é amplamente utilizada na construção de sistemas distribuídos, como sistemas web, aplicativos de celular, sistemas de gerenciamento de banco de dados e sistemas de arquivos. Ela permite que o cliente acesse os recursos do servidor de forma fácil e segura, enquanto o servidor gerencia e protege esses recursos.

### **O que é o protocolo HTTP**

HTTP (Hypertext Transfer Protocol) é um protocolo de comunicação utilizado na internet para transmitir dados entre clientes e servidores. Ele é responsável por estabelecer uma conexão entre o cliente e o servidor e garantir que as informações sejam transmitidas de forma correta e segura.

O protocolo HTTP funciona através de métodos, também conhecidos como verbos, que indicam a ação a ser realizada pelo servidor. Os métodos mais comuns são:

GET: solicita uma informação ou recurso do servidor. É o método utilizado para carregar uma página web ou baixar um arquivo.
POST: envia uma informação ou recurso para o servidor. É o método utilizado para enviar formulários ou fazer upload de arquivos.
PUT: atualiza uma informação ou recurso no servidor.
DELETE: apaga uma informação ou recurso do servidor.
Além dos métodos, o protocolo HTTP também utiliza cabeçalhos (headers) para transmitir informações adicionais, como a autorização do usuário, tipo de conteúdo e localização do recurso.

Um exemplo de como o protocolo HTTP funciona é ao acessar uma página web. Quando digitamos o endereço de uma página no navegador (por exemplo, "https://www.example.com"), o navegador envia uma solicitação GET para o servidor daquele endereço. O servidor então responde com o HTML da página, junto com outras informações como imagens, scripts e estilos, que são baixados pelo navegador e exibidos na tela.

Outro exemplo é quando preenchemos um formulário e clicamos no botão "enviar". O navegador envia uma solicitação POST para o servidor, contendo as informações preenchidas no formulário e o servidor processa essas informações e envia uma resposta de volta ao navegador.

Exemplo de uma solicitação HTTP GET:

```
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.82 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: pt-BR,pt;q=0.9,en-US;q=0.8,en;q=0.7
```


Exemplo de uma resposta HTTP para a solicitação acima:

```
HTTP/1.1 200 OK
Date: Mon, 24 Jan 2022 18:00:00 GMT
Server: Apache/2.4.29 (Ubuntu)
Last-Modified: Mon, 24 Jan 2022 10:00:00 GMT
Accept-Ranges: bytes
Content-Length: 60
Content-Type: text/html

<html>
<head>
<title>Example Web Page</title>
</head>
<body>
Welcome to the Example Web Page!
</body>
</html>
```

Neste exemplo, o cliente envia uma solicitação GET para o arquivo "index.html" no servidor "www.example.com". O servidor responde com o código de status HTTP "200 OK", indicando que a solicitação foi bem-sucedida, e o corpo da resposta contém o HTML da página solicitada.

Na solicitação, além do método GET, há informações como o "host" e "User-Agent" são cabeçalhos (headers) da requisição, eles contém informações adicionais sobre o cliente e a solicitação.

Na resposta, há informações como "Server", "Content-Type", "Date" são cabeçalhos (headers) da resposta, eles contém informações adicionais sobre o servidor e a resposta.

### **O que é PHP**

PHP é uma linguagem de programação de script open-source, especialmente projetada para o desenvolvimento web. Ela é utilizada principalmente no lado do servidor para criar páginas dinâmicas e aplicativos web.

PHP é uma linguagem de alto nível, o que significa que ela se assemelha mais à linguagem humana do que à linguagem de máquina. Isso facilita a escrita e a manutenção do código. PHP também suporta vários tipos de dados, estruturas de controle e bibliotecas prontas para uso, o que torna ainda mais fácil desenvolver aplicativos web.

Uma das principais vantagens do PHP é a sua integração com o banco de dados MySQL, um dos mais populares no mundo. Isso permite a criação de aplicativos que armazenam e recuperam dados do usuário, como sistemas de gerenciamento de conteúdo (CMS) e fóruns de discussão.

PHP também é compatível com a maioria dos sistemas operacionais e servidores web, como Windows, Linux e MacOS, e Apache e Nginx. Isso significa que é possível desenvolver e executar aplicativos PHP em uma ampla variedade de ambientes.

Alguns exemplos de aplicativos construídos com PHP incluem o WordPress, o Drupal, o Joomla e o Magento, estes são alguns dos CMS mais populares do mundo, e o Facebook, o qual é escrito em PHP.

----

## Conceitos básicos de PHP

### **Variáveis**

Variáveis em programação são espaços de armazenamento na memória do computador que podem conter valores. Elas permitem que os programadores armazenem e acessem dados de forma dinâmica durante a execução do código.

Em PHP, as variáveis são identificadas pelo sinal de dólar "$" seguido pelo nome da variável. O nome da variável pode conter letras, números e underscores, mas deve começar com uma letra ou underscore.

Exemplos de declaração de variáveis em PHP:

```php
$name = "John Doe";
$age = 25;
$is_student = true;
```

Em PHP, as variáveis não precisam ser declaradas explicitamente antes de serem usadas, e o tipo da variável é inferido automaticamente pelo valor atribuído. No exemplo acima, a variável $name é do tipo string, $age é do tipo inteiro e $is_student é do tipo booleano.

É possível também atribuir valores a uma variável de diversas formas, como por exemplo, através de cálculos:

``` php
$a = 5;
$b = 10;
$c = $a + $b;
```


Além disso, é possível também trabalhar com variáveis de diferentes tipos e realizar operações entre elas, como por exemplo:

``` php
$name = "Lucas";
$age = 30;
$result = $name . " tem " . $age . " anos";
```

É importante lembrar que em PHP é necessário prestar atenção na tipagem das variáveis, pois algumas operações não podem ser realizadas entre variáveis de tipos diferentes.

### **Condicionais**

Condicionais são estruturas de controle em programação que permitem tomar decisões baseadas em certas condições. Elas são usadas para executar uma ação específica se determinada condição for verdadeira, e outra ação se for falsa.

Em PHP, a estrutura condicional mais comum é o "if-else". Ela é usada para testar uma condição e executar um trecho de código se a condição for verdadeira, e outro trecho de código se a condição for falsa.

Exemplo de uso de "if-else" em PHP:

``` php
$age = 25;
if ($age >= 21) {
    echo "Você é maior de idade";
} else {
    echo "Você é menor de idade";
}
```

Neste exemplo, a condição é se a variável $age é maior ou igual a 21. Se for verdade, o código dentro do bloco "if" será executado, e a mensagem "Você é maior de idade" será exibida. Caso contrário, o código dentro do bloco "else" será executado e a mensagem "Você é menor de idade" será exibida.

Além do "if-else", existem outras estruturas condicionais como o "switch-case" e o "ternary operator", que são usadas em situações específicas.

O "switch-case" é uma estrutura condicional que testa o valor de uma variável e executa um bloco de código correspondente ao valor testado. Ele é útil quando há várias condições diferentes a serem testadas.

Exemplo de uso de "switch-case" em PHP:

```php
$day = "Monday";
switch ($day) {
    case "Monday":
        echo "Hoje é Segunda-feira";
        break;
    case "Tuesday":
        echo "Hoje é Terça-feira";
        break;
    default:
        echo "Não sei qual é o dia de hoje";
}
```


Neste exemplo, o valor da variável $day é comparado com os valores das "cases" dentro do "switch". Se a variável $day for igual a "Monday", o código dentro do primeiro case será executado e a mensagem "Hoje é Segunda-feira" será exibida. Se a variável $day for igual a "Tuesday", o código dentro do segundo case será executado e a mensagem "Hoje é Terça-feira" será exibida.

Já o "ternary operator" é uma forma abreviada de escrever uma condição "if-else" em uma única linha. Ele é composto por uma condição seguida de "?" e do valor a ser atribuído se a condição for verdadeira, seguido de ":" e do valor a ser atribuído se a condição for falsa.

Exemplo de uso do "ternary operator" em PHP:

``` php
$age = 25;
$is_adult = ($age >= 18) ? true : false;
```

Neste exemplo, a condição é se a variável $age é maior ou igual a 18. Se for verdade, o valor "true" será atribuído à variável $is_adult, caso contrário será atribuído "false".

Em resumo, as condicionais são fundamentais para a programação, pois permitem que os programadores tomem decisões baseadas em certas condições e execute trechos de códigos de acordo com essas decisões, dando flexibilidade e controle sobre a lógica do programa.

### **Laços de repetição**

Laços de repetição, também conhecidos como loops, são estruturas de controle em programação que permitem executar um bloco de código várias vezes. Eles são usados para automatizar tarefas repetitivas e processar conjuntos de dados.

Em PHP, existem três tipos de laços de repetição: "for", "while" e "do-while".

O laço "for" é usado quando se sabe quantas vezes o código deve ser executado. Ele é composto por três partes: a inicialização da variável de controle, a condição de parada e a operação de incremento ou decremento.

Exemplo de uso do laço "for" em PHP:

``` php
for ($i = 1; $i <= 10; $i++) {
    echo $i . " ";
}
```

Neste exemplo, a variável $i é inicializada com o valor 1, a condição de parada é quando $i for menor ou igual a 10, e a operação de incremento é $i++. O código dentro do loop será executado 10 vezes, imprimindo os números de 1 a 10.

O laço "while" é usado quando não se sabe quantas vezes o código deve ser executado, mas existe uma condição para que o loop seja interrompido. Ele é composto por uma única condição de parada.

Exemplo de uso do laço "while" em PHP:

```php
$i = 1;
while ($i <= 10) {
    echo $i . " ";
    $i++;
}
```


Neste exemplo, a condição de parada é quando $i for menor ou igual a 10. O código dentro do loop será executado até que a condição de parada seja verdadeira, imprimindo os números de 1 a 10. A operação de incremento é feita dentro do loop, usando $i++.

O laço "do-while" é semelhante ao "while", mas a diferença é que o código dentro do loop é executado pelo menos uma vez, independentemente da condição de parada.

Exemplo de uso do laço "do-while" em PHP:

```php
$i = 1;
do {
    echo $i . " ";
    $i++;
} while ($i <= 10);
```

Neste exemplo, a condição de parada é quando $i for menor ou igual a 10. O código dentro do loop será executado pelo menos uma vez, e continuará sendo executado até que a condição de parada seja verdadeira, imprimindo os números de 1 a 10. A operação de incremento é feita dentro do loop, usando $i++.

Em resumo, os laços de repetição são fundamentais para a programação, pois permitem automatizar tarefas repetitivas e processar conjuntos de dados de forma eficiente. Cada tipo de laço tem suas particularidades e utilidades, e é importante escolher a melhor opção de acordo com a necessidade do seu programa.

### **Funções**

Funções em programação são conjuntos de instruções que realizam uma tarefa específica e podem ser chamadas várias vezes durante a execução do código. Elas permitem organizar o código de forma modular, reutilizando trechos de código e tornando-o mais legível e fácil de manter.

Em PHP, as funções são definidas usando a palavra-chave "function", seguida do nome da função e parênteses. Dentro dos parênteses, podem ser definidos os parâmetros da função. O código a ser executado pela função deve ser inserido dentro de chaves {}.

Exemplo de uma função simples em PHP:

```php
function greet($name) {
    echo "Hello, $name!";
}
```

Neste exemplo, a função "greet" recebe um parâmetro $name e imprime uma saudação com esse nome. A função pode ser chamada várias vezes passando diferentes nomes como argumento:

```php
greet("John");
greet("Jane");
```

Além disso, as funções podem também retornar valores usando a palavra-chave "return". O valor retornado pode ser armazenado em uma variável ou usado como argumento de outra função.

Exemplo de uma função que retorna o quadrado de um número:

```php
function square($number) {
    return $number * $number;
}
```

Neste exemplo, a função "square" recebe um parâmetro $number e retorna o seu valor multiplicado por ele mesmo. A função pode ser chamada várias vezes passando diferentes números como argumento e o resultado pode ser armazenado em uma variável ou usado como argumento de outra função:

```php
$result = square(5);
echo $result; // 25
$result = square(3);
echo $result; // 9
```

Em resumo, as funções são fundamentais para a programação, pois permitem organizar o código de forma modular, reutilizando trechos de código e tornando-o mais legível e fácil de manter. Elas também possibilitam passar parâmetros e retornar valores, possibilitando a interação com outras partes do programa.

### **Arrays e laços**

Arrays em programação são estruturas de dados que permitem armazenar uma coleção de valores, geralmente relacionados entre si. Eles podem ser usados para armazenar uma lista de nomes, números, objetos, entre outros tipos de dados.

Em PHP, os arrays são declarados usando a palavra-chave "array()" ou usando colchetes "[]". Os elementos do array são separados por vírgulas e podem ser acessados usando um índice numérico ou uma chave associativa.

Exemplo de um array simples em PHP:

```php
$numbers = array(1, 2, 3, 4, 5);
```

Neste exemplo, o array $numbers armazena uma lista de números inteiros. Os elementos do array podem ser acessados usando um índice numérico:

```php
echo $numbers[0]; // 1
echo $numbers[1]; // 2
```

Os arrays também podem ser associativos, onde cada elemento é associado a uma chave.

```php
$person = array("name" => "John", "age" => 25, "address" => "New York");
```

Neste exemplo, o array $person armazena informações de uma pessoa, associando cada informação a uma chave específica, como "name", "age" e "address". Os elementos do array podem ser acessados usando as chaves associativas:

```php
echo $person["name"]; // "John"
echo $person["age"]; // 25
```

É comum usar laços de repetição, como "for" ou "foreach", para iterar sobre os elementos de um array e realizar alguma ação.

O laço "for" pode ser usado para iterar sobre os índices numéricos de um array:

```php
$numbers = array(1, 2, 3, 4, 5);
for ($i = 0; $i < count($numbers); $i++) {
    echo $numbers[$i] . " ";
}
```

Neste exemplo, o laço "for" é usado para iterar sobre os índices numéricos do array $numbers, imprimindo cada elemento.

Já o laço "foreach" é específico para arrays e permite iterar sobre os valores de um array sem precisar se preocupar com os índices:

```php
$person = array("name" => "John", "age" => 25, "address" => "New York");
foreach ($person as $key => $value) {
    echo "$key: $value" . " ";
}
```

Neste exemplo, o laço "foreach" é usado para iterar sobre os valores do array $person, imprimindo cada chave e valor associado.

Em resumo, os arrays e laços de repetição são ferramentas poderosas na programação, permitindo armazenar e trabalhar com conjuntos de dados de forma eficiente. Laços de repetição específicos para arrays como "foreach" permitem iterar sobre os valores de forma simples e legível, sem precisar se preocupar com os índices.

### **Strings**

Strings em programação são uma sequência de caracteres que podem ser usadas para representar texto, palavras, frases, entre outros tipos de conteúdo. Em PHP, as strings podem ser declaradas usando aspas simples (' ') ou aspas duplas (" ").

Exemplo de uma string simples em PHP:

```php
$name = "John Doe";
```

Neste exemplo, a variável $name é atribuída com a string "John Doe".

Strings em PHP podem ser concatenadas usando o operador de ponto (.) ou a função ".":

```php
$first_name = "John";
$last_name = "Doe";
$full_name = $first_name . " " . $last_name;
```

ou

```php
$full_name = "$first_name $last_name";
```

Neste exemplo, as variáveis $first_name e $last_name são concatenadas para formar a string $full_name "John Doe".

Além disso, o PHP fornece uma variedade de funções para manipular strings, como funções para encontrar e substituir partes de uma string, extrair partes de uma string, calcular o tamanho de uma string, entre outras.

Exemplo de algumas funções para manipulação de strings em PHP:

```php
$sentence = "The quick brown fox jumps over the lazy dog.";

// função strlen() retorna o tamanho da string
echo strlen($sentence); // 43

// função strpos() retorna a posição da primeira ocorrência de uma substring
echo strpos($sentence, "fox"); // 16

// função str_replace() substitui todas as ocorrências de uma substring por outra
echo str_replace("fox", "cat", $sentence); // "The quick brown cat jumps over the lazy dog."

// função substr() retorna uma parte de uma string a partir de uma posição e tamanho específicos
echo substr($sentence, 16, 3); // "fox"
```

Em resumo, as strings são fundamentais na programação, pois permitem representar e manipular texto de diversas formas. O PHP oferece uma variedade de funções para manipulação de strings, tornando-o fácil de encontrar, substituir, extrair e calcular o tamanho de uma string.

### **Gerando HTML com PHP**

Gerar HTML com PHP é uma técnica comum na programação web, pois permite dinamicamente criar conteúdo HTML usando a lógica de programação. Isso permite que o conteúdo da página seja gerado dinamicamente, baseado em dados do banco de dados ou em outras fontes de dados.

Um exemplo simples de como gerar HTML com PHP é criando uma lista não ordenada (ul) com uma série de itens (li) :

```php
<ul>
    <?php
    $items = array("item1", "item2", "item3");
    foreach ($items as $item) {
        echo "<li>$item</li>";
    }
    ?>
</ul>
```

Neste exemplo, o array $items é criado no PHP e é iterado com um laço "foreach". Dentro do laço, cada item é impresso como um elemento de lista (li) dentro de uma lista não ordenada (ul).

O código acima pode ser reescrito de diversas formas:

```php
echo "<ul>";
$items = array("item1", "item2", "item3");
foreach ($items as $item) {
    echo "<li>$item</li>";
}
echo "</ul>";
```

```php
$items = array("item1", "item2", "item3");
$list = "<ul>";
foreach ($items as $item) {
    $list .= "<li>$item</li>";
}
$list .= "</ul>";
echo $list;
```

```php
<?php
$items = array("item1", "item2", "item3");
?>
<ul>
<?php foreach ($items as $item): ?>
    <li><?php echo $item ?></li>
<?php endforeach ?>
</ul>
```

```php
<?php
$items = array("item1", "item2", "item3");
?>
<ul>
<?php foreach ($items as $item): ?>
    <li><?= $item ?></li>
<?php endforeach ?>
</ul>
```

Ou seja, existem várias formas de se escrever o mesmo código, cada uma com suas vantagens e desvantagens, e é importante escolher a melhor opção para cada caso.

Outro exemplo é gerar uma tabela dinamicamente com dados do banco de dados:

```php
<table>
    <tr>
        <th>ID</th>
        <th>Name</th>
        <th>Age</th>
    </tr>
    <?php
    $conn = mysqli_connect("host", "user", "password", "database");
    $result = mysqli_query($conn, "SELECT * FROM users");
    while ($row = mysqli_fetch_assoc($result)) {
        echo "<tr>";
        echo "<td>" . $row['id'] . "</td";
        echo "<td>" . $row['name'] . "</td>";
        echo "<td>" . $row['age'] . "</td>";
        echo "</tr>";
    }
    mysqli_close($conn);
    ?>
</table>
```

Neste exemplo, a tabela é gerada dinamicamente lendo os dados de uma tabela do banco de dados. A conexão com o banco de dados é feita usando a função mysqli_connect() e a consulta SQL é executada com a função mysqli_query(). O resultado da consulta é percorrido com o laço while e para cada linha retornada, as informações são inseridas em uma linha da tabela (tr), usando elementos de células de tabela (td).

Em resumo, gerar HTML com PHP é uma técnica importante na programação web, pois permite criar conteúdo dinamicamente com base em dados de diversas fontes e usando a lógica de programação. Isso permite criar páginas web mais flexíveis e dinâmicas, adaptando-se a diferentes situações e usuários.

----

## CRUD com PHP

### **O que é CRUD**

