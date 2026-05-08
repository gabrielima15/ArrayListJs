# :rocket: ARRAYLIST EM JAVASCRIPT: <br>

## O que é?<br>

### No javaScript listas são um conjuntos de elementos onde podemos guardar valores nele para uso empresariáis, uma delas é manipular valores dentro dele para criar uma nova lista com os dados modificados, os métodos abaixo não modificam o Array original apenas criam uma nova Array com o valores alterados.
<br>

## :arrows_counterclockwise: map() <br>

### Cria um novo array com valores modificados com mesma quantidade de valores do array anterior.<br>

### dos exemplos abaixo vão ser usado a lista valores e funcionarios.<br>

```

const valores = [2,5,1,8,7,9,11,22];

const funcionarios = [
  { id: 1, nome: "Ana Silva", departamento: "TI", salario: 7500, ativo: true },
  { id: 2, nome: "Bruno Costa", departamento: "RH", salario: 4200, ativo: true },
  { id: 3, nome: "Carla Souza", departamento: "TI", salario: 8100, ativo: false },
  { id: 4, nome: "Diego Lima", departamento: "Financeiro", salario: 5500, ativo: true },
  { id: 5, nome: "Elena Martins", departamento: "TI", salario: 6000, ativo: false }
];

```
<br>

```
// pega os valores do array e cria uma nova com os valores multiplicados.

let novoValor = valores.map(x=> x * 2);

```
<br>

```

// nesse código todos os funcionarios recebem uma bonificação de 5%.

let bonificacao = funcionarios.map(x =>{
    return (x.salario * 0.05) + x.salario;
});

```
<br>

## :mag: filter()<br>

### método que busca filtrar valores específicos e cria um novo com aqueles dados.<br>

```
// filtrar apenas valores que são pares.

let numerosPares = valores.filter(x =>{
    return x % 2 == 0;
});

```
<br>

```
// filtrar funcionarios que são da área de TI e que estão ativos.

let funcionarioAtivo = funcionarios.filter(f =>{
        return f.departamento === 'TI' && f.ativo == true;
});

```
<br>

## :abacus: reduce()<br>

### método que funciona como um contador responsável por reduzir todo o valor da lista em um valor único.<br>

### :warnin: estrutura do reduce: array.reduce(callback => (contador, incrementador),inicializador) nele você pode definir em como iniciar o valor inicial depois de definir a saida do método.<br>

```
// somando todos os numeros dentro da lista.
let acumulador = valores.reduce((valor,acumular) => {
    return valor + acumular;
},0);

```
<br>

```
// podemos pegar o valor dos funcionários e fazer a soma dele para ver o valor total bruto.

let valorSomado = funcionarios.reduce((inicial,final) => inicial + final.salario,0);

```
<br>

## :bowl_with_spoon: podemos utilizar também todos os métodos map,filter e reduce numa única variavel, também filtrar mais ainda em qual dado querendo obter tornando mais preciso o valor que estamos procurando!<br>

```
/*Calcular o custo total da folha de pagamento apenas os
 funcionários ativos do departamento de TI que ganham mais de 6000."
*/

const custoTotalTI = funcionarios
  .filter(f => f.ativo && f.departamento === "TI" && f.salario > 6000)
  .map(f => f.salario)
  .reduce((acumulador, salario) => acumulador + salario, 0);

```


