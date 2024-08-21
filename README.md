# JS-Lecture

## Variáveis

Variáveis em programação são contêineres que armazenam valores em espaços de memória. Em JavaScript há quatro formas de declararmos uma variável. Abaixo é listado estas quatro formas.
- Declarar utilizando var
- Declarar utilizando let
- Declarar utilizando const
- Declarar diretamente sem nenhuma palavra reservada antes.

Exemplo 1:<br>
>  x = 10;

Exemplo 2:<br>
> var palavra = 'Casa';

Exemplo 3:<br>
> verdadeiro = true;

Exemplo 4:<br>
> const pi = 3.1415

### Let vs Var

Podemos declarar variáveis com o let e o var. Esse foi apresentadado recentemente à comunidade de desenvolvedores de JS. Por isso, algums navegadores mais antigos como o Internet Explorer podem não aceitar variáveis declaradas com let. Basicamente variáveis declaradas com let têm escopo de bloco. Neste sentido, elas não podem ser acessadas fora deles, diferente de variáveis declaradas com var. O exemplo abaixo reproduz bem esta situação.

```
{
  let teste = "teste";
}
console.log(teste);
```

Neste caso, um erro é apresentado pois a variável teste não existe fora do bloco criado. Se ao invés de let usarmos o var todo o código funciona perfeitamente. 
Por isso dizemos que variáveis declarada com var tem escopo global. Uma outra característica interessante é que a variável criada com let não pode ser declarada novamente (Redeclare), mas pode ser reatribuída (Reassign).

```
{
  let teste = "teste";
  let teste = "teste1";
}
SyntaxError: Identifier 'teste' has already been declared
```


### Exemplo com const
Declarar variáveis com const traz mais restrições. Aqui apresento um exemplo de uma das grandes diferenças entre JS e outras linguagens: a ideia de bloco. Podemos criar várias variáveis com const dentro de blocos sem apresentar qualquer tipo de erro, isso pois, const, assim como let, tem escopo de bloco.
```
const pi = 3.14;
{
  const pi = 3;
}
{
  const pi = 3.1416
}
```

## Operadores

Os operadores em JS são parecidos com os operadores em outras linguagens. Diferente de Python que usa as palavras reservadas and e or, em JS usamos & e | || também) para representar estes operadores lógicos. Um operador que achei interessante foi o ===. Não vi nenhum equivalente deste operador em qualquer outra linguagem. Este comparador compara o valor e o tipo do dado. Abaixo é apresentado uma diferença entre == e ===.
```
(true == true); -> true
(true == 1); -> true
(true == 'true'); -> true

(true === true); -> true
(true === 1); -> false
(true === 'true'); -> false
```

Com relação aos operadores matemáticos, há grande semelhança também. Podemos usar ** para potencialição, assim como Math.pow(x,2).

```
var x = 2;
console.log(x**3);
console.log(Math.pow(x,3));
```



## Tipos de Dados

JavaScritp apresenta alguns tipos de dados primitivos:
- Number  -> let numero = 1.23
- String  -> var nome = 'Magno'
- Boolean -> let verificador = true
- Array   -> const estacoes = ['Primavera', 'Verão', 'Outono', 'Inverno']
- Objeto  -> var carro = {nome: 'Fiat Uno', cor: 'Vermelho', ano: 2020}
- Date    -> let data = new Date('2024-08-13')
- BigInt  -> let x = BigInt('11111111111111111111111111111111111111111111111111111111')

Interessante notar como JS lida com operações com diferentes tipos de dados. As operações são realizadas da esquerda para a direita

```
let x = 16 + 4 + 'Nome';
console.log(x)
-> 20Nome
```

```
let x = 'Nome' + 16 + 4;
console.log(x)
-> Nome164
```

Diferente de linguagens como Java que apresentam diferentes tipos de números (int, float, double), JS apresenta apenas o tipo number (64-bit ponto flutuante). O tipo BigInt é utilizado para armazenar números inteiros com valores muito elevado. 


## Objetos

Em JS podemos instanciar objetos com mecanismos parecidos com a criação de classes que existem em linguagens como Python e Java. Geralmente inicia-se um objeto com const, porém seus atributos e valores podem ser modificados. O que não pode ser modificado é o objeto como um todo.

```
const aluno = {nome: 'Magno', idade: '29', matricula:'1234567'}
const.nome = 'Magno Leal'
const.nota = 7.0
```

Podemos também instanciar um objeto através de new Object()

```
const carro = new Objet()
carro.nome = 'Uno'
carro.ano = 2010
```
Algo interessante dentro desta linguagem é que podemos definir métodos dentro da estrutura de criação do objeto conforme mostra o código abaixo.

```
const pessoa = {
    nome: 'Magno',
    idade: 12,
    acao: function(){
        return this.nome + this.idade
    }
}

```
Podemos deletar uma propriedade de um objeto através da palavra reservada delete.

```
const pessoa = {
    nome: 'Magno',
    idade: 12,
    acao: function(){
        return this.nome + this.idade
    }
}

delete pessoa.idade;
console.log(pessoa)
{ nome: 'Magno', acao: [Function: acao] }

```
Podemos também aninhar objetos dentro de outros objetos.

```
const pessoa = {
    nome: 'Magno',
    idade: 12,
    acao: function(){
        return this.nome + this.idade
    },
    disciplinas: {
        nome: 'Português',
        periodo: 2,
    }
}


```
Por fim, podemos criar uma função construtura de objetos. Com esta função, podemos instanciar vários objetos de um mesmo tipo.

```
function Carro(nome, marca, cor, ano){
    this.nome = nome
    this.marca = marca
    this.cor = cor
    this.ano = ano
}

const uno = new Carro('Uno', 'Fiat', 'Amarelo',2010)
const corsa = new Carro('Corsa', 'Chevrolet', 'Branco',2000)
const palio = new Carro('Palio', 'Fiat', 'Preto',2010)
const siena = new Carro('Siena', 'Fiat', 'branco',2019)


```
Podemos também acessar os atributos de um objeto através de um loop for ou while

```
function Carro(nome, marca, cor, ano){
    this.nome = nome
    this.marca = marca
    this.cor = cor
    this.ano = ano
}

const uno = new Carro('Uno', 'Fiat', 'Amarelo',2010)
const corsa = new Carro('Corsa', 'Chevrolet', 'Branco',2000)
const palio = new Carro('Palio', 'Fiat', 'Preto',2010)
const siena = new Carro('Siena', 'Fiat', 'branco',2019)

let vetor = [uno, corsa, palio, siena]
for(let p in vetor){
    for(let i in vetor[p]){
        console.log(vetor[p][i])
    }
    
}

```

## Eventos

Podemos interagir com elementos presentes em uma página HTML utlizando JavaScript. Existem diferentes métodos que podem gerar diferentes modificações na página.
O <b>getElementById</b> é o mais comum deles. O código abaixo combina este método com o <b>onclick()</b>.

```
<button id="botao1" value="botao1" onclick="funcao1(this)">Botão</button>
    <script>
        botao = document.getElementById("botao1");
        function funcao1(botao){
            botao.innerHTML = "Funciona!";
        }
    </script>

```
O event <b>onchange</b> é utilizado quando selecionamos um valor em um select, por exemplo.

```
 <select id="select"  onchange="funcao2()">
        <option value="A">Aline</option>
        <option value="B">Bianca</option>
        <option value="C">Carla</option>
        <option value="D">Dario</option>
    </select>

    <p id="aluno"></p>

...
function funcao2(){
            var selecionado = document.getElementById("select").value;
            document.getElementById("aluno").innerHTML=selecionado

            
        }

```

Onmouseover é um event que muda alguma coisa quando o mouse passa por cima do elemento.

```
    <button onmouseover="this.style.color='#FF0000'">Mouseover</button>

```

## Numbers

Diferentes de linguagens como Jave, JS tem apenas um típo de número: number. Quando quisermos representar números grandes ou pequenos podemos escrevê-los da seguinte maneira:

```
let x = 1.2e5;
let y = 1.2e-5;

```
JS os números são armazenadados com 64-bit de ponto flutuante. Engraçado, JS pode fazer uma conversão entre String e Number caso a operação abaixo seja executada:

```
let x = '200';
let y = '2';
let z = x/y;
console.log(z) => 100

```

O error NaN (Not a Number) aparece quando quisermos fazer operações com strings que não podem ser convertidas em números com números. Mas NaN é também um tipo de número. 

```
let x = '200';
let y = 'uva';
let z = x/y;
console.log(z) => NaN

```

Um outro tipo de número interessante da classe number  é Infinity (ou -Infinity). Este número aparece em divisões por zero ou quando um loop ultrapasse o valor do maior número possível.

```
let x = 2;
let y = 0;
console.log(x/y) => Infinity

```

