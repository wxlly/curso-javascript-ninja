# Desafio da semana #4

```js
/*
Declare uma variável chamada `isTruthy`, e atribua a ela uma função que recebe
um único parâmetro como argumento. Essa função deve retornar `true` se o
equivalente booleano para o valor passado no argumento for `true`, ou `false`
para o contrário.
*/
var isTruthy = function(x) {
  return x ? true : false;
}

// Invoque a função criada acima, passando todos os tipos de valores `falsy`.
isTruthy('');
isTruthy(undefined);
isTruthy(null);
isTruthy(NaN);
isTruthy(-0);
isTruthy(0);
isTruthy(false);

/*
Invoque a função criada acima passando como parâmetro 10 valores `truthy`.
*/
isTruthy('wollace');
isTruthy('1');
isTruthy({});
isTruthy([]);
isTruthy(true);
isTruthy(1);
isTruthy(2);
isTruthy(3);
isTruthy(4);
isTruthy(1000);

/*
Declare uma variável chamada `carro`, atribuindo à ela um objeto com as
seguintes propriedades (os valores devem ser do tipo mostrado abaixo):
- `marca` - String
- `modelo` - String
- `placa` - String
- `ano` - Number
- `cor` - String
- `quantasPortas` - Number
- `assentos` - Number - cinco por padrão
- `quantidadePessoas` - Number - zero por padrão
*/
var carro = {
  marca: 'ford',
  modelo: 'Fusion',
  placa: 'AAA-1234',
  ano: 2019,
  cor: 'Preto',
  quantasPortas: 4,
  assentos: 5,
  quantidadadePessoas: 0
}

/*
Crie um método chamado `mudarCor` que mude a cor do carro conforme a cor
passado por parâmetro.
*/
carro.mudarCor = function(x) {
  return carro.cor = x;
}

/*
Crie um método chamado `obterCor`, que retorne a cor do carro.
*/
carro.obterCor = function() {
  return carro.cor;
}

/*
Crie um método chamado `obterModelo` que retorne o modelo do carro.
*/
carro.obterModelo = function() {
   return carro.modelo;
}

/*
Crie um método chamado `obterMarca` que retorne a marca do carro.
*/
carro.obterMarca = function() {
  return carro.marca;
}

/*
Crie um método chamado `obterMarcaModelo`, que retorne:
"Esse carro é um [MARCA] [MODELO]"
Para retornar os valores de marca e modelo, utilize os métodos criados.
*/
carro.obterMarcaModelo = function() {
	return 'Esse carro é um ' + carro.obterModelo() + ' ' + carro.obterMarca();
}

/*
Crie um método que irá adicionar pessoas no carro. Esse método terá as
seguintes características:

- Ele deverá receber por parâmetro o número de pessoas entrarão no carro. Esse
número não precisa encher o carro, você poderá acrescentar as pessoas aos
poucos.

- O método deve retornar a frase: "Já temos [X] pessoas no carro!"

- Se o carro já estiver cheio, com todos os assentos já preenchidos, o método
deve retornar a frase: "O carro já está lotado!"

- Se ainda houverem lugares no carro, mas a quantidade de pessoas passadas por
parâmetro for ultrapassar o limite de assentos do carro, então você deve
mostrar quantos assentos ainda podem ser ocupados, com a frase:
"Só cabem mais [QUANTIDADE_DE_PESSOAS_QUE_CABEM] pessoas!"

- Se couber somente mais uma pessoa, mostrar a palavra "pessoa" no retorno
citado acima, no lugar de "pessoas".

*/
carro.adicionaPessoas = function(x) {
  carro.quantidadadePessoas += x;
  var assentosLivres = 5 - carro.quantidadadePessoas;
  var naoPlural1 = carro.quantidadadePessoas == 4 ? 'pessoa' : 'pessoas';
  var naoPlural2 = assentosLivres == 4 ? 'pessoa' : 'pessoas';
  var txt = carro.quantidadadePessoas >= 5 ? 'O carro já está lotado!' : 'Só cabe mais ' + assentosLivres + ' ' + naoPlural1 + '!';

  return 'Já temos ' + carro.quantidadadePessoas + ' ' + naoPlural2 + ' ' + 'no carro! ' + txt;
}

/*
Agora vamos verificar algumas informações do carro. Para as respostas abaixo,
utilize sempre o formato de invocação do método (ou chamada da propriedade),
adicionando comentários _inline_ ao lado com o valor retornado, se o método
retornar algum valor.

Qual a cor atual do carro?
*/
carro.obterCor(); //Preto

// Mude a cor do carro para vermelho.
carro.mudarCor('Vermelho');

// E agora, qual a cor do carro?
carro.obterCor(); //Vermelho

// Mude a cor do carro para verde musgo.
carro.mudarCor('Verde Musgo');

// E agora, qual a cor do carro?
carro.obterCor(); //Verde Musgo

// Qual a marca e modelo do carro?
carro.obterMarcaModelo(); //Esse carro é um Fusion Ford

// Adicione 2 pessoas no carro.
carro.adicionaPessoas(2); //Já temos 2 pessoas no carro! Só cabe mais 3 pessoas!

// Adicione mais 4 pessoas no carro.
carro.adicionaPessoas(4); //Já temos 6 pessoas no carro! O carro já está lotado!

// Faça o carro encher.
carro.adicionaPessoas(5); //Já temos 5 pessoas no carro! O carro já está lotado!

// Tire 4 pessoas do carro.
carro.adicionaPessoas(5); //Já temos 1 pessoa no carro! Só cabe mais 4 pessoas!

// Adicione 10 pessoas no carro.
carro.adicionaPessoas(10); //Já temos 11 pessoas no carro! O carro já está lotado!

// Quantas pessoas temos no carro?
//11
``
