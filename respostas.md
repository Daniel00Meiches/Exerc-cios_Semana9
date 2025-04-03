Um zoológico está desenvolvendo um sistema básico para registrar animais. Todos os  animais têm um nome, uma espécie e uma idade. Além disso, há animais classificados  como animais selvagens, que possuem um habitat natural como característica adicional. 
Para tornar o sistema mais organizado e reutilizável, a equipe utilizou conceitos de  Programação Orientada a Objetos (POO), como herança e reutilização de métodos. 
Veja a implementação inicial abaixo: 

```javascript
// Classe base 
class Animal { 
 constructor(nome, especie, idade) { 
 this.nome = nome; 
 this.especie = especie; 
 this.idade = idade; 
 } 
 exibirInformacoes() { 
 return `Nome: ${this.nome}, Espécie: ${this.especie}, Idade: ${this.idade}`;  } 
} 
// Classe derivada 
class AnimalSelvagem extends Animal { 
 constructor(nome, especie, idade, habitat) { 
 super(nome, especie, idade); 
 this.habitat = habitat; 
 } 
 exibirHabitat() { 
 return `Habitat natural: ${this.habitat}`; 
 } 
} 
// Instâncias e retornos 
const animal1 = new Animal("Tico", "Macaco", 4); 
const animal2 = new AnimalSelvagem("Nala", "Leoa", 5, "Savana Africana"); 
console.log(animal1.exibirInformacoes()); 
console.log(animal2.exibirInformacoes()); 
console.log(animal2.exibirHabitat());
```

Perguntas Dissertativas: <br>

### 1. Estrutura de Classes e Objetos <br>

**a) Quais atributos são definidos na classe Animal?** <br>

R) Os atributos definidos são o nome do animal, sua espécie e sua idade.

**b) Como a classe AnimalSelvagem amplia a estrutura de Animal?** <br>

R) A classe AnimalSelvagem amplia a estrutura da classe Animal adicionando um novo atributo que é o habitat natural do animal e um método que exibe o habitat.

### 2. Herança <br>

**c) O que significa a linha class AnimalSelvagem extends Animal?** <br>

R) Essa linha quer dizer que a classe AnimalSelvagem vai herdar os atributos e métodos da classe mãe, Animal. No javascript, o termo "extends" faz a herança.

**d) O que acontece internamente quando usamos o comando super(...) dentro do  construtor da subclasse?** <br>

R) Quando o comando super é usado, os atributos da classe Animal (nome, espécie e idade) serão herdados para a classe AnimalSelvagem. Isso evita repetir a definição dos mesmos atributos no código da subclasse AnimalSelvagem.

### 3. Instanciação <br>

**e) O que ocorre passo a passo quando o comando new AnimalSelvagem("Nala",  "Leoa", 5, "Savana Africana") é executado?**

R) O programa vai atribuir os parâmetros "Nala", "Leoa", 5 e "Savana Africana" aos seus respectivos atributos: Nome, Espécie, Idade e Habitat. Essencialmente:

```
this.nome = "Nala";
this.especie = "Leoa";
this.idade = 5;
this.habitat = "Savana Africana";
```

**f) Qual a diferença entre a criação dos objetos animal1 e animal2?** <br>

R) A diferença da criação dos objetos animal1 e animal2 é que animal1 terá apenas os atributos da classe Animal: nome, espécie e idade. Agora, o animal2 terá esses três atributos e também terá o atributo do habitat que é exclusivo da classe AnimalSelvagem.

### 4. Acesso a Métodos <br>

**g) Por que o método exibirInformacoes() pode ser utilizado tanto em animal1 quanto em animal2?** <br>

R) O método exibirInformacoes() pode ser usado nos dois objetos pois ambos os objetos têm os atributos necessários, que são nome, espécie e idade, para que o método funcione corretamente.

**h) O método exibirHabitat() está disponível em animal1? Justifique sua resposta.** <br>

R) O método exibirHabitat() não está disponível em animal1, porque esse método é definido apenas na subclasse AnimalSelvagem e a classe mãe Animal não tem como herdar ou utilizar os métodos e atributos da subclasse AnimalSelvagem.

### 5. Reutilização de Código <br>

**i) Como a herança contribui para evitar duplicação de código nesse exemplo?** <br>

R) A herança da classe Animal permite que a subclasse AnimalSelvagem pode herdar os atributos da classe mãe sem ter que repetir código para a definição dos mesmos atributos na função constructor. A herança também permite que a subclasse Animal Selvagem pode chamar o método exibirInformacoes() sem ter que definir o mesmo método na subclasse.

**j) Se fosse necessário adicionar um novo comportamento a todos os animais, como  "dormir()", em qual classe ele deveria ser implementado? Por quê?**

R) Se o comportamento dormir() fosse um comportamento para todos os animais, deveria ser implementado na classe mãe Animal, já que esse comportamento poderia então ser herdado para outras subclasses de animais.

### 6. Retorno e Impressão <br>

**k) Qual é a saída exata exibida no console ao executar o código apresentado?** <br>

R)

```
Nome: Tico, Espécie: Macaco, Idade: 4
Nome: Nala, Espécie: Leoa, Idade: 5
Habitat natural: Savana Africana
```

**l) O que aconteceria se fosse removida a linha super(nome, especie, idade) do  construtor da classe AnimalSelvagem?** <br>

R) 

### 7. Prática de Extensão <br>
m) Crie uma nova subclasse chamada AnimalDomestico, que herda de Animal e inclui  um novo atributo chamado nomeDono. 
n) Implemente um método chamado exibirDono() que retorne: "Dono de [nome do  animal]: [nome do dono]".

### 8. Organização e Clareza de Código <br>
o) Explique por que utilizar classes em vez de apenas funções soltas pode tornar o código  mais organizado e fácil de manter. 

### 9. Criação de Métodos <br>
p) Se fosse necessário criar um método chamado aniversario() para aumentar a idade de  qualquer animal em um ano, em qual classe ele deveria ser inserido? Justifique  tecnicamente sua escolha.

### 10. Especialização com Herança <br>
q) Qual é a principal motivação para se utilizar herança na criação de AnimalSelvagem em  vez de repetir os atributos e métodos da classe Animal? Quais seriam as consequências  caso não fosse utilizada herança nesse cenário?
