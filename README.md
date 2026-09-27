# ClearBank - Análise Financeira

Desafio final do módulo de Python. O notebook lê o `transacoes.csv`, valida os dados, calcula métricas por mês, aponta transações acima de R$ 10.000 e gera o `relatorio.json`.

## Como rodar

Precisa de Python 3.10+ e Jupyter (ou Colab).

1. Coloque o `transacoes.csv` na mesma pasta do notebook.
2. Abra o `desafio-final.ipynb`.
3. Execute todas as células.

No terminal:

```bash
jupyter notebook desafio-final.ipynb
```

No Colab, faça upload do notebook e do CSV e rode tudo.

## Saída

Ao executar todas as células, o notebook gera duas saídas:

### Terminal

1. **Resumo da limpeza** — total de linhas lidas, válidas e inválidas.
2. **Relatório mensal** — data de geração, período analisado, contagem de transações e, para cada mês:
   - quantidade de transações;
   - total de crédito e débito;
   - saldo, média, maior e menor valor.
3. **Transações suspeitas** — registros com valor acima de R$ 10.000,00 (id, cliente, data e valor).

### Arquivo `relatorio.json`

Exporta o mesmo conteúdo do relatório em JSON, com a estrutura:

| Campo | Descrição |
|-------|-----------|
| `gerado_em` | Data de geração (`AAAA-MM-DD`) |
| `total_transacoes_validas` | Quantidade de linhas válidas |
| `total_transacoes_invalidas` | Quantidade de linhas descartadas |
| `periodo` | `inicio`, `fim` e `dias` do intervalo analisado |
| `resumo_mensal` | Métricas por mês (`quantidade`, `total_credito`, `total_debito`, `saldo`, `media`, `maior_valor`, `menor_valor`) |
| `transacoes_suspeitas` | Lista de transações acima do limite (`id`, `cliente_id`, `data`, `valor`) |

## Arquivos

- `desafio-final.ipynb` — notebook com a solução
- `transacoes.csv` — dados de entrada
- `relatorio.json` — saída gerada pelo notebook
