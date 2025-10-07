# Projeto Fila de Pacientes com Monitoramento de Memória

## Descrição

Este projeto implementa uma **fila de atendimento de pacientes** em Python, considerando **prioridade** (normal ou prioritário) e **ordem de chegada**.
O sistema inclui funcionalidades de:

* Adição de pacientes;
* Remoção/atendimento de pacientes;
* Alteração de dados de pacientes;
* Exibição da fila na ordem normal e inversa;
* Monitoramento de memória a cada operação;
* Modo interativo no terminal para executar comandos de forma dinâmica.

O projeto é indicado para estudos de **estruturas de dados** (listas duplamente encadeadas) e **gerenciamento de filas com prioridades**.

---

## Estrutura do Projeto

* `Paciente`: classe que representa cada paciente com atributos:

  * `nome`
  * `idade`
  * `prioridade` (1 = normal, 2 = prioritário)
  * `proximo` e `anterior` para a lista duplamente encadeada.
* `Fila`: classe que representa a fila de atendimento, com métodos:

  * `adicionar_paciente(nome, idade, prioridade)`
  * `remover_paciente()`
  * `alterar_dados_paciente(nome, novo_nome, nova_idade, nova_prioridade)`
  * `exibir_fila()`
  * `exibir_fila_inversa()`
* Função `monitoramento_memoria(mensagem)`:

  * Usa `tracemalloc` para exibir consumo de memória antes e depois de cada operação.
* `modo_interativo(fila)`:

  * Permite interagir com a fila pelo terminal digitando comandos.

---

## Como Rodar

1. Salve o arquivo como, por exemplo, `fila_interativa.py`.
2. Abra o terminal na pasta do arquivo.
3. Execute o programa.

4. A lista inicial de pacientes será carregada automaticamente e a fila será exibida.

---

## Comandos do Modo Interativo

| Comando                                      | Descrição                           | Exemplo                      |
| -------------------------------------------- | ----------------------------------- | ---------------------------- |
| `add <nome> <idade> <P/N>`                   | Adiciona um paciente à fila         | `add João 35 P`              |
| `assist`                                     | Remove o paciente que será atendido | `assist`                     |
| `edit <nome> <novo_nome> <nova_idade> <P/N>` | Altera os dados de um paciente      | `edit Maria Mariazinha 41 N` |
| `show`                                       | Exibe a fila na ordem normal        | `show`                       |
| `showinv`                                    | Exibe a fila na ordem inversa       | `showinv`                    |
| `exit`                                       | Sai do modo interativo              | `exit`                       |

---

## Observações

* Pacientes prioritários (`P`) têm preferência de atendimento sobre pacientes normais (`N`).
* Dentro de cada prioridade, a ordem de chegada é mantida.
* O monitoramento de memória mostra:

  * Memória usada antes e depois de cada operação.
  * Diferença de memória, ajudando a analisar eficiência.

---

## Exemplo de Uso

```
Fila inicial:
[Mary (P)]-->[Aurora (P)]-->[Alice (P)]-->[Emily (P)]-->[Teste (P)]-->[James (N)]-->[Pierre (N)]-->[Mike (N)]-->[Ashley (N)]-->[David (N)]-->None

Digite um comando: add Carlos 50 N
Digite um comando: assist
Paciente Mary (P) foi atendido.
Digite um comando: show
[Carlos (N)]-->[Aurora (P)]-->...-->None
```

---

Se você quiser, posso também criar uma **versão visual do README em Markdown** já pronta para colocar no GitHub, com **exemplos de saída e cores para comandos**, que fica mais apresentável.

Quer que eu faça isso?
