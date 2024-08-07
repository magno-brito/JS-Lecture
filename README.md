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



## Testando




