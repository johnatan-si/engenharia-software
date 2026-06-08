
# Atividade: Grafo de Fluxo de Controle e Complexidade Ciclomática

 
  

## Fórmulas importantes

  

A complexidade ciclomática pode ser calculada por:

  

```text

V(G) = E - N + 2

```

  

Onde:

  

- `E` = número de arestas do grafo;

- `N` = número de nós do grafo.

  

Também pode ser calculada por:

  

```text

V(G) = P + 1

```

  

Onde:

  

- `P` = número de nós predicados;

- nó predicado é um nó com duas ou mais saídas.

  

---

  

## Instruções gerais para os alunos

  

Para cada questão:

  

1. Identifique os **blocos básicos**.

2. Desenhe o **Grafo de Fluxo de Controle (GFC)**.

3. Conte:

- número de nós `N`;

- número de arestas `E`;

- número de nós predicados `P`.

4. Calcule a complexidade ciclomática usando:

  

```text

V(G) = E - N + 2

```

  

e

  

```text

V(G) = P + 1

```

  

5. Liste os caminhos linearmente independentes.

6. Proponha casos de teste para exercitar os caminhos principais.

  

---

  

# Questão 1 — Validação simples com `if` e `while`

  

```java

public static int contarParesPositivos(int[] valores) {

int i = 0;

int pares = 0;

  

while (i < valores.length) {

if (valores[i] > 0 && valores[i] % 2 == 0) {

pares++;

}

i++;

}

  

return pares;

}

```

  

## Tarefas

  

a) Desenhe o GFC do método.

  

b) Calcule a complexidade ciclomática.

  

c) Liste os caminhos linearmente independentes.

  

d) Proponha casos de teste para cobrir:

  

- vetor vazio;

- vetor com número positivo par;

- vetor com número positivo ímpar;

- vetor com número negativo par;

- vetor com vários elementos.

  

---

  

# Questão 2 — Cálculo de multa com `if`, `else` e `for`

  

```java

public static double calcularMulta(int diasAtraso, boolean aluno, int quantidadeLivros) {

double multa = 0.0;

  

for (int i = 0; i < quantidadeLivros; i++) {

if (diasAtraso > 0) {

multa = multa + diasAtraso * 1.50;

}

}

  

if (aluno) {

multa = multa * 0.5;

} else {

multa = multa + 5.0;

}

  

return multa;

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule `V(G)`.

  

c) Explique o impacto do `for` no grafo.

  

d) Crie casos de teste para:

  

- nenhum livro;

- livro sem atraso;

- livro com atraso;

- aluno;

- não aluno.

  

---

  

# Questão 3 — Classificação de senha

  

```java

public static String avaliarSenha(String senha) {

int pontos = 0;

int i = 0;

  

while (i < senha.length()) {

char c = senha.charAt(i);

  

if (Character.isDigit(c)) {

pontos++;

}

  

if (Character.isUpperCase(c)) {

pontos++;

}

  

i++;

}

  

if (senha.length() >= 8 && pontos >= 2) {

return "Forte";

} else {

return "Fraca";

}

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule a complexidade ciclomática.

  

c) Liste caminhos independentes.

  

d) Proponha senhas de teste.

  

---

  

# Questão 4 — Cálculo de bônus com `while`, `if` e `break`

  

```java

public static double calcularBonus(double[] vendas) {

int i = 0;

double total = 0.0;

  

while (i < vendas.length) {

if (vendas[i] < 0) {

break;

}

  

total = total + vendas[i];

i++;

}

  

if (total >= 10000) {

return total * 0.10;

}

  

return total * 0.05;

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Mostre como o `break` altera o fluxo normal do laço.

  

c) Calcule a complexidade ciclomática.

  

d) Proponha casos de teste.

  

---

  

# Questão 5 — Aprovação de aluno com laço e decisão composta

  

```java

public static String avaliarAluno(double[] notas, int faltas) {

double soma = 0.0;

int i = 0;

  

while (i < notas.length) {

soma = soma + notas[i];

i++;

}

  

double media = soma / notas.length;

  

if (media >= 60 && faltas <= 10) {

return "Aprovado";

} else if (media >= 40) {

return "Recuperacao";

} else {

return "Reprovado";

}

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule a complexidade ciclomática.

  

c) Discuta o risco de erro se `notas.length == 0`.

  

d) Proponha casos de teste.

  

---

  

# Questão 6 — Sistema de saque bancário

  

```java

public static String sacar(double saldo, double valor, int tentativasSenha, boolean contaBloqueada) {

if (contaBloqueada) {

return "Conta bloqueada";

}

  

if (tentativasSenha >= 3) {

return "Senha bloqueada";

}

  

if (valor <= 0) {

return "Valor invalido";

}

  

if (saldo >= valor) {

saldo = saldo - valor;

return "Saque realizado";

} else {

return "Saldo insuficiente";

}

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule `V(G)`.

  

c) Liste os caminhos independentes.

  

d) Proponha casos de teste.

  

---

  

# Questão 7 — Busca em vetor com `while` e `if`

  

```java

public static boolean contemNumero(int[] numeros, int procurado) {

int i = 0;

boolean encontrado = false;

  

while (i < numeros.length && !encontrado) {

if (numeros[i] == procurado) {

encontrado = true;

}

i++;

}

  

return encontrado;

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule a complexidade ciclomática.

  

c) Discuta o efeito da condição composta no `while`.

  

d) Crie casos de teste.

  

---

  

# Questão 8 — Validação de formulário com `for`, `continue` e `if`

  

```java

public static int contarCamposValidos(String[] campos) {

int validos = 0;

  

for (int i = 0; i < campos.length; i++) {

if (campos[i] == null) {

continue;

}

  

if (campos[i].trim().isEmpty()) {

continue;

}

  

validos++;

}

  

return validos;

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Mostre como o `continue` altera o fluxo.

  

c) Calcule a complexidade ciclomática.

  

d) Proponha casos de teste.

  

---

  

# Questão 9 — Simulação de jogo simples

  

```java

public static String avaliarJogada(int energia, int inimigos, boolean itemEspecial) {

while (inimigos > 0 && energia > 0) {

if (itemEspecial) {

energia = energia - 1;

} else {

energia = energia - 3;

}

  

inimigos--;

}

  

if (energia > 0) {

return "Venceu";

} else {

return "Perdeu";

}

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule a complexidade ciclomática.

  

c) Proponha casos de teste para vitória e derrota.

  

d) Explique o papel da condição composta no `while`.

  

---

  

# Questão 10 — Questão-desafio: caixa eletrônico com repetição de tentativas

  

```java

public static String autenticar(String senhaCorreta, String[] tentativas) {

int i = 0;

  

while (i < tentativas.length && i < 3) {

if (tentativas[i].equals(senhaCorreta)) {

return "Acesso permitido";

}

i++;

}

  

return "Acesso bloqueado";

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule a complexidade ciclomática.

  

c) Explique a diferença entre sair do método por `return` dentro do laço e sair pelo fim do `while`.

  

d) Proponha casos de teste.

  

---

  

# Questão 11 - Carrinho de compras

  

```java

public static double calcularFrete(double peso, double valorCompra, boolean entregaExpressa) {

double frete = 0.0;

  

if (peso <= 0) {

return -1.0;

}

  

if (peso <= 5) {

frete = 10.0;

} else {

frete = 20.0;

}

  

if (valorCompra >= 300.0) {

frete = frete * 0.5;

}

  

if (entregaExpressa) {

frete = frete + 15.0;

}

  

return frete;

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule `V(G)`.

  

c) Liste os caminhos independentes.

  

d) Crie casos de teste.

  

---

  

# Questão 12 — Controle de temperatura

  

```java

public static String avaliarTemperatura(int[] leituras) {

int i = 0;

int alertas = 0;

  

while (i < leituras.length) {

if (leituras[i] > 80) {

alertas++;

}

  

if (leituras[i] < 0) {

return "Sensor com defeito";

}

  

i++;

}

  

if (alertas >= 3) {

return "Risco alto";

}

  

return "Normal";

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule a complexidade ciclomática.

  

c) Mostre caminhos com retorno antecipado.

  

d) Crie casos de teste.

  

---

  

# Questão 13 — Pagamento de funcionário

  

```java

public static double calcularPagamento(int horas, double valorHora, boolean feriado) {

double total = 0.0;

  

if (horas <= 0 || valorHora <= 0) {

return 0.0;

}

  

for (int i = 0; i < horas; i++) {

if (i < 8) {

total = total + valorHora;

} else {

total = total + valorHora * 1.5;

}

}

  

if (feriado) {

total = total * 2;

}

  

return total;

}

```

  

## Tarefas

  

a) Desenhe o GFC.

  

b) Calcule `V(G)`.

  

c) Discuta a diferença entre cobertura de decisões e cobertura de caminhos.

  

d) Proponha casos de teste.

  

---

  
