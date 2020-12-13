# Design Patterns

São **soluções generalistas para problemas recorrentes** durante o desenvolvimento de um um software. **Se trata de uma definição de alto nível**  de como um problema comum pode ser sulocionado.



### Patter Language

![img](https://upload.wikimedia.org/wikipedia/en/thumb/e/e6/A_Pattern_Language.jpg/220px-A_Pattern_Language.jpg) 

Surgiu com o livro *patter language-Christopher Alexander, Sara Ishikowa e Murray Silverstein,* lançado em 1978*.* Nele são descritos 253 tipos de problemas/desafios de projetos. 

### Formato de um pattern:

- ​	Nome
- ​	exemplo de uso
- ​	Contexto de aplicação
- ​	Problema que pretende resolver
- ​	Solução que resolve o problema

### Tipo de Patterns

​	A teoria sobre deign patterns foi evoluindo onde foi definido categorias de patterns:

- ​	**Pattern de Criação:** Ajuda a tornar o sistema independente de como seus objetos são criados. Patterns famosos desse tipo:
  - ​		Abstract 	Factory
  - ​		Builder
  - ​		Factory 	Method
  - ​		Prototype
  - ​		Singleton
- ​	**Pattern Estruturais:** Se preocupam com a forma como classes e objetos são compostos para formar estruturas maiores. Patterns famosos desse tipo:
  - ​		Adapter 	 	
  - ​		Bridge
  - ​		Composite
  - ​		Decarator
  - ​		Facade
  - ​		Business 	Delegate
  - ​		Flyweight
  - ​		Proxy
- ​	**Patterns Comportamentais:** Se concentra nos algoritmos e atribuições de resoponsabilidade entre os objetos.  Patterns famosos desse tipo:
  - ​		Chain 	off Responsibility
  - ​		Command
  - ​		Inerpreter 	 	
  - ​		Iterator
  - ​		Mediator
  - ​		Observer
  - ​		State
  - ​		Strategy 	 	
  - ​		Template 	Method
  - ​		Visitor

### Os patterns mais utilizados em JavaScript

- **Factory:** Quando uma função retornam um objeto sem a necessidade de chamá-la com ***new,*** são chamados de **funções Factory** (Factory functions):

```javascript
// função que não é Factory
function User(){
    this.name: 'Alex';
    this.lastName: 'terolti';
}
const user1 = new User(); // Usa o new

// função que é Factory
function User(){
    return{
        name: 'Alex',
        lastName: 'Terolti'
    }
}
const user1 = User(); 
```

- ​	**Singleton**: Ela cria  **uma única instância** de uma função, assim toda vez retorna essa instância quando for necessário utiliza-la. O [jQuery](https://jquery.com/) é baseado nesse padrão. Exemplo de uso do Singleton:

```javascript
function Pessoa (){
   if(!Pessoa.instance){ 
       // caso Pessoa.instance não for declarada 
       Pessoa.instance = this;
   }
   return Pessoa.instance;
}
const p = Pessoa.call( name: 'alex');
const p2 = Pessoa.call(name: 'outro nome');
console.log(p) // {name:'alex'}
console.log(p2) // {name; 'alex'}
```

- ​	**Decorator**: Uma função Decorator **recebe uma função como parâmetro** e estende o seu comportamento sem modifica-la explicitamente. Exemplo de uso do Decorator:

```javascript
let hangs = false;
function callFUnction (fn){
    return hangs && fn(); // faz com que a função só seja executado quando hangs é true
}
function soma(a,b){
    return a + b;
}
console.log( callFunction(() => soma(1,2)) ) 
// false
hangs = true
console.log( callFunction(() => soma(1,2)) ) 
// 3

// "() => soma(1,3)" transforma uma função com argumentos em uma função sem argumentos com valores pre setados 
```



- ​	**Observer**:  A instância(**subcriber**) que fica escutando algo e mantém uma coleção de objetos (**observers**) e notifica-os quando ocorrem mudanças de estado. [Vue.js](https://vuejs.org/) e [Rx.js](https://rxjs-dev.firebaseapp.com/) funcionam nesse a partir desse Pattern. Exemplo de implementação de Observers: 

```` javascript
class Observable{
    constructor(){
        this.observers =[];
    }
    subcribe(fn){
        this.observers.push(fn);
    }
    notify(data){
        this.observers.forEach(observer => observer(data));
    }
}
````

- ​	**Module**: Organiza melhor o código sem a necessidade de expor varáveis globais. Exemplo:

```javascript
//declarando a classe
class Person {
    consturctor(name){
        this.name = name;
    }
}
// exporta a classe para ser usada em outro arquivo
exprt default pesrson; 

// Usando Person
import Person from './lugar/armazenado';
```



