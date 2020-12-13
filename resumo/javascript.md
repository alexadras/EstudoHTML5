# JavaScript (js)

​	É um linguagem de programação que está em conformidade com o **ECMAScript spefication**. Ela foi criada originalmente para o rodar no **Netscape web browser** onde **era chamada de LiveScript** antes do nome JavaScript. Ela foi difundida quando foi adotado pela **Microsoft** um engenharia reversa do interpretador de código Navigator do Netscape chamado **JScript**.

​	Foi lançada em 1995 e criada por **Brendan Eich** 

Javascript é:

- De auto-nível (high-level)
- Interpretada em tempo de execução (just-in-time JIT)
- Multiparadigma 
- De tipagem dinâmica(onde uma mesma variável pode assumir vários tipos)
- Orientação a objeto 
- Funciona a partir da interação com os elementos HTML

# ECMAScript (ES)

É uma **linguagem de proposito geral e padronizada** para que o código funcione da mesma forma em várias plataformas. **Serve como base para outras linguagens** como: JavaScript, SpiderMonkey, V8, ActionScript, JScript, QtScript, Google Apps Script .

Ele é administrado pelo comitê TC39.

A última especificação ECMAScript é a ES2018.

## [Babel](https://babeljs.io/)

![img](https://d33wubrfki0l68.cloudfront.net/7a197cfe44548cc1a3f581152af70a3051e11671/78df8/img/babel.svg)

É um transformador de código JavaScript, que traduz a especificação mais recente  para uma mais antiga que **funcione em Web browsers mais antigos**. 

## TypeScript

```typescript
class Person {
    private name: string;
    private age: number;
    private salary: number;

    constructor(name: string, age: number, salary: number) {
        this.name = name;
        this.age = age;
        this.salary = salary;
    }

    toString(): string {
        return `${this.name} (${this.age}) (${this.salary})`; // As of version 1.4
    }
}
```

É um **superset** ( um super grupo, possui mais função além do próprio JS) de JavaScript, que adiciona Tipo estático(static typing), possuindo interfaces, deixando o JavaScript mais parecido com C/C++ e relacionados.

O TypeScript é compilado e retorna um condigo JavaScript equivalente. 

---

## Hello world

```javascript
alert("hello world")
```

## Conceitos JavaScript ES2018

Alguns conceitos relevantes no código JavaScript:

### Currying 

​	É o processo de transformar uma função com **vários argumentos** em uma função com apenas um único argumento que **retorna outra função** que aceita outro argumento e assim por diante. Exemplo:

```javascript
// uma função sem currying
function soma(a,b){
    return a+b;
}
soma(1,2) //1+2 = 3
soma(1,3) //1+3 = 4

// A mesma função usando currying
function soma(a){
    return function(b){
        return a +b;
    }
}
soma1 = soma(1) // salva a função com a=1
soma1(2) //1+2 = 3
soma1(3) //1+3 = 4

```

### Hoisting

É o uso do elemento antes de sua declaração. Existe dois tipos de hosting;

-  **variável**: O uso da variável antes de sua declaração e atribuição de valor. Nesse caso a variável armazena o valor *underfined*. Por exemplo:

  ```javascript
  console.log(text); // exibe underfined
  text = "a"
  console.log(text); // exibe "a"
  ```

- **função**: Onde uma função é usada antes de sua declaração. Nesse caso **a função é clamada normalmente**, como se estive-se sido declarada antes. Exemplo:

  ```javascript
  log('iu'); // exibe 'iu'
  function log(t){
      console.log(t)
  }	
  ```

### String literal 

```javascript
'${var1} oi ${var2}';
// é equivalente à
var1 + ' oi ' + var2;
```

## Tipos e variáveis

- **var**: uma variável de *escopo global ou de função*, dependendo de onde foi declarado;
- **let:** é uma variável  de *escopo de bloco*, onde ela é valida somente no bloco (entre {}) que foi declarada; 
- **const:** Cria uma variável que Não permite que seu valor seja alterado.

### Tipos primitivos 

- string: Texto
- number: número 
- boolean: verdadeiro (true) ou falso (false)
- null: Nulo 
- undefined: variável não definida
- symbol: Criar um símbolo
- Object:  Objeto
- Function: função ou método
- array: vetor, é um tipo de objeto especifico;

### Operador spread 

Ele "abre" os elementos de um objeto. Exemplo:

```javascript
var lista = [1,2,3,4]
var num = [0, ...lista, 5, 6 ]; 
alert(num) //exibe: 0,1,2,3,4,5,6
// pode usar em funções também
function f(a,b,c){}
var argumentos = [3,2,1]
f(...argumentos);  // é equivalente a: f(3,2,1)
```

## Estruturas de repetição

- for
- while
- do..while
- for..in: passa por todos os índices de um objeto 
- for.. of: passa por todos os elementos de um objeto 
- continue 
- break

----
# Orientação a objeto no JavaScript

O JavaScript é uma linguagem orientada a objeto, onde tudo é um objeto:

- `Object` é uma objeto com o construtor `Objetct()`:
  - [mais sobre](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Trabalhando_com_Objetos) os objetos na documentação oficial;

```javascript
nomeDoObjeto.nomeDaPropriedade; // acesso a uma prorpiedade de um objeto 
//outro exemplo:
var meuCarro = new Object();
meuCarro.fabricacao = "Ford";
meuCarro.modelo = "Mustang";
meuCarro.ano = 1969;
//as propriedades tb podem ser acessardas por meio da notação de colchetes:
meuCarro["fabricacao"] = "Ford";
meuCarro["modelo"] = "Mustang";
meuCarro["ano"] = 1969;
//para inicializar um objeto se usa essa estrutura
var obj = { propriedade_1:   valor_1,   // propriedade_# pode ser um identificador...
            2:            valor_2,   // ou um numero...
            // ...,
            "propriedade n": valor_n }; // ou uma string
```

- `Array` é uma objeto com o construtor `Array()`. [Veja mais sobre](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Indexed_collections) na documentação oficial. As declarações a seguir arrays equivalentes:

```javascript
var arr = new Array(elemento0, elemento1, ..., elementoN);
var arr = Array(elemento0, elemento1, ..., elementoN);
var arr = [elemento0, elemento1, ..., elementoN];
```

- `Function` é uma objeto com o construtor `Function()`. [Veja mais](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Fun%C3%A7%C3%B5es) na documentação oficial.

```javascript
// uma função que retorna(return) o quadrado de um número
function square(numero) { 
  return numero * numero; 
}
```



##  Herança

 Existem várias maneiras de se  **estender um objeto**(fazer com que os _derivados (filhos)_ possuíssem o que o objeto _base (ou pai)_ possui). O mais comum é o **subtipo que é uma copia implícita** de todos os campos do objeto base, assim todos as operações do pai são aplicáveis ao filho. Outra maneira é o **protótipo** (no caso do JavaScript por exemplo) onde **nada é copiado**, as propriedades são somente ___delegadas___.

​	Todos os objetos em JS possuem a propriedade protótipo, essa propriedade é implementada através do nome ` __proto__`. E **nunca** use esta propriedade diretamente ou associe outro valor a ela ela faz parte do funcionamento do objeto.

### prototype

​	Funções também possuem uma propriedade chamada `protptype` que é diferente da `__proto__`. Todos os objetos JS herdam propriedades e métodos de um protótipo. Assim **conseguimos alterar as propriedades ou métodos de objetos**. Exemplo:

```javascript
// declarando a função construtora do objeto P
function P(a){
    this.a = a; 
}
P.prototype.b = "b" // adicionando uma propriedade 
const ab = new P("a"); // declarando um objeto
> oi.b // pedindo o propriedade b  
< "b"
// assim retorna a propriedade adicionanda por meio do prototype
```

​	**Não é recomendado modificar (apesar de possível) os objetos nativos**, pois possivelmente vai criar muitos bugs e comportamentos indesejados em projetos maiores. 

### .constructor

​	É uma propriedade dos objetos que aponta para a função construtora que criou inicialmente o objeto

### Exemplo de uso:

```javascript
const myText = String("hello prototype")

// o __proto__ aponta para o mesmo local que o prototype da função contrutora String
console.log(myText.__proto__.split === String.prototype.split);
//True

// 
console.log(myText.constructor === String);
//true
```

### _new_

​	Cria um novo objeto, herdando o `.prototype` da função construtora. Mas ele cria somente se a função construtora não possui retorno(return), exemplo:

```javascript
function Pessoa(name){ // função geradora
    this.name = name;
    return{
        name: 'test'
    };
}
> const guilherme = new Pessoa("Guilherme");
> guilherme
< {name: 'test'} 
```

### instanceof

​	Verifica se um objeto é herdado de outro. Por exemplo, usando o exemplo a cima:

```javascript
> guilherme instanceof Pessoa
< true 
> guilherme instanceof Function 
< false
```

### .call

​	Com o uso do `.call` um objeto pode usar métodos pertencente a outro objeto. Exemplo:

```javascript
var person = {
    fullName: function(){
        return '${this.firstName} ${this.lastName}' 
    }
}
var person1 = {
    firstName: "Alex",
    lastName: "Terolti"
}
person.fullName.call(person1); // vai retornar Alex Terolti
/// Exemplo com funções com argumentos 
var person = {
  fullName: function(city, country) {
    return this.firstName + " " + this.lastName + "," + city + "," + country;
  }
}
var person1 = {
  firstName:"Alex",
  lastName: "Terolti"
}
person.fullName.call(person1, "Sinop", "Mato Grosso");
```



## Classes (class)

​	É uma **simplificação da herança de protótipos**, deixando de fácil uso e mais parecido com linguagens como Java ou C/C++. Na maioria dos casos o uso das classes torna o código bem menor. Foi adicionado na versão **ES6**.  Exemplo de uso:

```javascript
// Sem classes 
function Animal(nPatas){
    this.nPatas = nPatas;
}
function Cachorro(morde){
    Animal.call(this.4)
    this.morde = morde;
}
const pug = new Cachorro(false)
> pug
< Cachorro{nPatas> 4, morde: false}

// com classes 
class Animal {
    constructor(nPatas){
        this.npatas = nPatas;
    }
}
class Cachorro extends Animal{
    construtor(morde){
        super(4);
        this.morde = morde;
    }
}
const pug = new Cahorro(false)
> pug
< Cachorro{nPatas> 4, morde: false}
```



## Modificadores de acesso

​	O javaScript atualmente não tem controle de acesso, **mas vai ser lançado logo,logo** na versão ES12, atualmente (2020) implementado no Node.js .

​	Isso serve para controlar o acesso das propriedades de um objeto de forma a torna-lo isolado do sistema, aumentando a segurança.

- Atributo privado: `#name`, a variável name é privada.

## Encapsulamento

​	**Serve para ocultar detalhes do funcionamento interno**, como em uma capsula. 

## Static

​	Acessar propriedades **sem instanciar**.

