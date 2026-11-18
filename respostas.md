# Checkpoints de JavaScript

---

## Checkpoint 1 — Arrays e Laços (`for`)

### 1. Qual valor o segundo bloco imprime (a média das quatro notas)? Faça a conta antes.
**R:** `6.875`

### 2. Em `notas`, qual é o índice do primeiro elemento? E do último, em função de `length`?
**R:** O índice do primeiro elemento é `0`. Já o `length` determina a quantidade de elementos na lista, então o índice do último elemento é `notas.length - 1`.

### 3. Escreva um laço `for` que imprima os números pares de 2 a 10:
**R:**
```javascript
for (let num = 2; num <= 10; num += 2) {
    console.log(num);
}
```
*(Nota: no seu rascunho estava começando em `0` e usando apenas um `&`; o ideal é iniciar em `2` e usar `&&` caso adicione outra condição).*

### 4. Faça um teste de mesa e diga o que será impresso:
```javascript
let total = 0;
for (let i = 1; i <= 4; i++) {
    total += i;
}
console.log(total);
```
**R:** `10`

---

## Checkpoint 2 — Funções

### 1. O que a função abaixo imprime? Qual é o erro e como corrigi-lo?
```javascript
function soma(a, b) {
    a + b;
}
console.log(soma(2, 3));
```
**R:** O código atual imprime `undefined` porque falta a palavra-chave `return`. Para corrigir e imprimir `5`, basta colocar `return a + b;` dentro da função.

### 2. Escreva uma função `ehPar(n)` que retorne `true` se `n` for par e `false` caso contrário.
**R:**
```javascript
function ehPar(n) {
    if (n % 2 === 0) {
        return true;
    } else {
        return false;
    }
}
console.log(ehPar(5)); // false
```

### 3. Qual a diferença entre `console.log(x)` e `return x` dentro de uma função?
**R:** O `console.log(x)` apenas exibe o valor no console do navegador para visualização, sem devolvê-lo ao programa. Já o `return x` encerra a função e devolve o valor como resultado, permitindo guardá-lo em uma variável ou exibi-lo depois com `console.log(nomeDaFuncao())`.

---

## Checkpoint 3 — DOM e Eventos

### 1. Remova o `defer` do `<script>` e atualize a página. Qual erro aparece no console? Explique por que ele acontece.
**R:** Aparece o erro: `Uncaught TypeError: Cannot set properties of null (setting 'textContent')`. Sem o `defer`, o navegador executa o JavaScript antes de terminar de ler o HTML. Como o elemento da página ainda não foi criado na tela, a busca retorna `null` ("nada encontrado"), e o código falha ao tentar alterar o `textContent` de algo que ainda não existe.

### 2. Descreva com suas palavras o que acontece, passo a passo, a cada clique no botão:
**R:** A cada clique no botão, o programa soma 1 à variável de contagem, atualiza o número de cliques exibido na tela e altera o texto do próprio botão.

### 3. Por que a variável `cliques` foi declarada com `let` e não com `const`?
**R:** Porque o `let` permite reatribuir e mudar o valor da variável ao decorrer do código, enquanto `const` cria um valor fixo que não pode ser alterado.

---

## Checkpoint 4 — Precedência e Boas Práticas (Etapa 8.1)

### 1. Por que não se pode escrever `n1 + n2 / 2`? Calcule o resultado dessa expressão para `8` e `6` e compare com a média correta.
**R:** Porque na ordem das operações matemáticas, a divisão acontece antes da soma (`8 + 6 / 2` resulta em `8 + 3 = 11`). O certo é usar parênteses em `(n1 + n2) / 2` para somar antes de dividir, chegando à média correta de `7`.

### 2. Por que a média foi calculada em uma função separada (`calcularMedia`), e não escrita direto dentro do `addEventListener`?
**R:** Para organizar e reutilizar o código. O `addEventListener` cuida apenas da interação com a tela, enquanto a função isola a regra matemática, facilitando testes e manutenção.

### 3. Se o professor mudasse a média mínima de 6 para 7, quantas linhas do seu código você precisaria alterar? Por quê?
**R:** Apenas 1 linha (`const NOTA_MINIMA = 7;`). Porque o valor está centralizado em uma constante no topo do código, evitando que você tenha que procurar e alterar o número `6` manualmente em vários lugares.
