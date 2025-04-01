# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ``` 
let a = "olá" 
let b = 10 
print(a)
Resolva as questões com uso do Visual Studio Code ou ambiente similar.

Teste seus códigos antes de trazer a resposta para cá.

Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)

ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove.

Questões objetivas
1) Considere o seguinte código JavaScript:

javascript
Copiar
Editar
//EX01
let p = 10;
let q = 3;
let r = 6;

let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

const valores = [3, 6, 9, 12, 15];
let produto = 1;

for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
}

console.log("O produto dos valores é:", produto);
Qual das seguintes alternativas melhor descreve o que o código faz?

Resposta:
A) O código avalia a expressão booleana, imprime true, calcula o produto dos números na lista e imprime o resultado no console.

2) O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

javascript
Copiar
Editar
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    } while (limite >= totalCompras && i < compras.length);

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
javascript
Copiar
Editar
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    var totalCompras = compras[0];
    var limite = 5000;
    var status = 'aprovado';
    var saldoDisponivel = 0;
    var i = 1;

    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    saldoDisponivel = limite - totalCompras;

    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

Resposta:
B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

3) Considere o seguinte trecho de código em JavaScript:

javascript
Copiar
Editar
//EX03
const idade = 21;

if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  console.log("Você está na melhor idade!");
}
Qual das seguintes alternativas melhor descreve o comportamento do código?

Resposta:
B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".

4) Qual será o resultado impresso no console após a execução do seguinte código?

javascript
Copiar
Editar
//EX04
var energiaDisponivel = 1200;
var bateriaExtra = 400;
var consumoDispositivos = [300, 600, 500, 200, 400];

for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];

    if (consumo <= energiaDisponivel) {
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        energiaDisponivel -= consumo;
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
Qual será o resultado impresso no console?

Resposta:
B)
Dispositivo 1 ligado. Energia restante: 900
Dispositivo 2 ligado com bateria extra. Energia restante: 700
Dispositivo 3 ligado. Energia restante: 200
Dispositivo 4 não pode ser ligado. Energia insuficiente.
Dispositivo 5 não pode ser ligado. Energia insuficiente.

5) Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Resposta:
B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.

6) Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Resposta:
A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças.

Questões dissertativas
7) Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

plaintext
Copiar
Editar
Pedidos abaixo de R$50,00 → "Frete não disponível!"
Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"
Pedidos de R$200,00 ou mais → "Frete grátis!"
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

Resposta:

plaintext
Copiar
Editar
Início
    Leia valorTotalCompra
    Se valorTotalCompra < 50 então
        Escreva "Frete não disponível!"
    Senão se valorTotalCompra <= 199.99 então
        Escreva "Frete com custo adicional!"
    Senão
        Escreva "Frete grátis!"
Fim
8) Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

Resposta:

plaintext
Copiar
Editar
Classe Veiculo:
    Atributos:
        modelo
        ano
    
    Método Construtor(modelo, ano):
        Definir modelo = modelo
        Definir ano = ano
    
    Método CalcularConsumo():
        Retornar "Método genérico de consumo"

Classe Carro herda Veiculo:
    Atributos:
        quilometragem
        eficiencia

    Método Construtor(modelo, ano, quilometragem, eficiencia):
        Chamar Construtor de Veiculo
        Definir quilometragem = quilometragem
        Definir eficiencia = eficiencia

    Método CalcularConsumo():
        Retornar quilometragem / eficiencia

Classe Moto herda Veiculo:
    Atributos:
        quilometragem
        eficiencia

    Método Construtor(modelo, ano, quilometragem, eficiencia):
        Chamar Construtor de Veiculo
        Definir quilometragem = quilometragem
        Definir eficiencia = eficiencia

    Método CalcularConsumo():
        Retornar quilometragem / eficiencia
9) Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Resposta:

plaintext
Copiar
Editar
Início
    Leia velocidadeInicial
    Leia desaceleracao
    velocidade = velocidadeInicial
    tempo = 0
    Enquanto velocidade > velocidadeSegura e tempo < tempoMaximo:
        velocidade = velocidade - desaceleracao
        tempo = tempo + 1
    Se velocidade <= velocidadeSegura então
        Escreva "A sonda pousou com sucesso após " + tempo + " segundos."
    Senão
        Escreva "A sonda não conseguiu pousar dentro do tempo máximo."
Fim
10) Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

Resposta:

plaintext
Copiar
Editar
Função MultiplicarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes podem ser multiplicadas (número de colunas de A == número de linhas de B)  
    Se tamanho(matrizA[0]) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser multiplicadas. Elas têm dimensões incompatíveis."  
    Senão:  
        linhasA <- tamanho(matrizA)  
        colunasA <- tamanho(matrizA[0])  
        colunasB <- tamanho(matrizB[0])  
        matrizResultado <- novaMatriz(linhasA, colunasB)  

        # Loop para percorrer e multiplicar as matrizes  
        Para i de 0 até linhasA-1 faça:  
            Para j de 0 até colunasB-1 faça:  
                soma <- 0  
                Para k de 0 até colunasA-1 faça:  
                    soma <- soma + (matrizA[i][k] * matrizB[k][j])  
                matrizResultado[i][j] <- soma  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1.1, 1.2], [1.3, 1.4]]  

totalInvestimentos <- MultiplicarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Investimentos multiplicados:")  
ImprimirMatriz(totalInvestimentos)  
