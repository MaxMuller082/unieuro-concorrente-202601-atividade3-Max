
# Relatório da NOME DA ATIVIDADE

**Disciplina:** Programação Concorrente
**Aluno(s):** Max Muller Da Silva Rosa
**Turma:** S.I, 4 Semestre
**Professor:** Rafael Marconi
**Data:** 20/03/2026

---

# 1. Descrição do Problema

O trabalho teve como objetivo desenvolver um programa capaz de analisar grandes volumes de arquivos de log, extraindo informações como número de linhas, quantidade de palavras, caracteres e frequência de palavras-chave específicas.

A solução foi implementada em duas versões: uma sequencial (serial) e outra paralela, com o intuito de comparar o desempenho entre elas.

Na versão paralela, foi utilizada a biblioteca multiprocessing, com o uso de Pool, permitindo distribuir os arquivos entre vários processos para execução simultânea.

Os testes foram realizados com um conjunto de dados contendo aproximadamente **10 milhões de linhas**, distribuídas em diversos arquivos de texto.

A complexidade do algoritmo é linear, pois cada linha dos arquivos é percorrida apenas uma vez durante o processamento.

**Questões que devem ser respondidas:**

* Qual é o objetivo do programa?
* R= analisar arquivos de log e comparar desempenho entre execução serial e paralela

* Qual o volume de dados processado?
* R= cerca de 10 milhões de linhas
* Qual algoritmo foi utilizado?
* R= leitura e contagem de dados em arquivos
* Qual a complexidade aproximada do algoritmo?
* R= O(n)
---

# 2. Ambiente Experimental

| Item                        | Descrição             |
| --------------------------- | ---------             |
| Processador                 | i5-12500              |
| Número de núcleos           |     12                |
| Memória RAM                 |    16GB               |
| Sistema Operacional         |  Windows              |
| Linguagem utilizada         |  Python               |
| Biblioteca de paralelização | Multiprocessing (Pool)|
| Compilador / Versão         | Python 3.13           | 

---

# 3. Metodologia de Testes

Os experimentos foram realizados executando o programa em diferentes configurações de paralelismo, variando o número de processos.


## Orientações

Descrever:

* O tempo de execução foi medido utilizando a função `time.time()`, registrando o tempo no início e no final de cada execução.
* Para cada configuração, foi realizada uma execução utilizando o mesmo conjunto de dados.
* Se foi utilizada média dos tempos
* Qual tamanho da entrada foi usado

### Configurações testadas

Os experimentos devem ser realizados nas seguintes configurações:

* 1 processo (execução sequencial)
* 2 processos
* 4 processos
* 8 processos
* 12 processos

### Procedimento experimental

Descrever:

Os testes foram executados em um ambiente controlado, sem grande interferência de outros programas.
Os tempos foram coletados diretamente durante a execução do código.

---

# 4. Resultados Experimentais

Preencha a tabela com os **tempos médios de execução** obtidos.

## Orientações

* O tempo deve ser informado em **segundos**
* Utilizar a **média das execuções**

| Nº Threads/Processos | Tempo de Execução (s) |
| -------------------- | --------------------- |
| 1                    |       95.0349s        |
| 2                    |       47.7677s        |
| 4                    |       25.9577s        |
| 8                    |       17.6893s        |
| 12                   |       17.0794s        |

---

# 5. Cálculo de Speedup e Eficiência

## Fórmulas Utilizadas

### Speedup

```
Speedup(p) = T(1) / T(p)
```

Onde:

* **T(1)** = tempo da execução serial
* **T(p)** = tempo com p threads/processos

### Eficiência

```
Eficiência(p) = Speedup(p) / p
```

Onde:

* **p** = número de threads ou processos

---

# 6. Tabela de Resultados

Preencha a tabela abaixo utilizando os tempos medidos.

| Threads/Processos | Tempo (s) | Speedup | Eficiência |
| ----------------- | --------- | ------- | ---------- |
| 1                 |  95.0349s | 1.0     | 1.0        |
| 2                 |  51.3736s | 1.99    | 0.99       |
| 4                 |  25.9577s | 3.66    | 0.92       |
| 8                 |  17.6893s | 5.37    | 0.67       |
| 12                |  17.0794s | 5.56    | 0.46       |

---

# 7. Gráfico de Tempo de Execução

Construa um gráfico mostrando o **tempo de execução em função do número de threads/processos**.


![Gráfico Tempo Execução](graficos/tempo_execucao.png)

---

# 8. Gráfico de Speedup

Construa um gráfico mostrando o **speedup obtido**.



![Gráfico Speedup](graficos/speedup.png)

---

# 9. Gráfico de Eficiência

Construa um gráfico mostrando a **eficiência da paralelização**.


![Gráfico Eficiência](graficos/eficiencia.png)

---

# 10. Análise dos Resultados

Realize uma análise crítica dos resultados obtidos.

## Questões a serem respondidas

* O speedup obtido foi próximo do ideal?
* A aplicação apresentou escalabilidade?
* Em qual ponto a eficiência começou a cair?
* O número de threads ultrapassa o número de núcleos físicos da máquina?
* Houve overhead de paralelização?

Discutir possíveis causas para:

* perda de desempenho
* gargalos no algoritmo
* sincronização entre threads/processos
* comunicação entre processos
* contenção de memória ou cache

---

# 11. Conclusão

Apresente as conclusões do experimento.

## Sugestões de pontos a comentar

* O paralelismo trouxe ganho significativo de desempenho?
* Qual foi o melhor número de threads/processos?
* O programa escala bem com o aumento do paralelismo?
* Quais melhorias poderiam ser feitas na implementação?

---
