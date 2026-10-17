# Protocolo – Projeto 01: Triagem administrativa

## Elementos do fluxo
| Elemento | Definição neste projeto |
|---|---|
| Entrada | Nome, CPF/CNPJ fictício, assunto resumido e urgência percebida (apoio/clientes_ficticios.md) |
| Processamento | Classificar numa lista fechada (apoio/tabela_assuntos.md), aplicar perguntas de apoio, decidir entre agendamento direto ou associado |
| Saída | Ficha de triagem preenchida no modelo da tabela, com recomendação de encaminhamento |
| Exceções | Assunto fora das categorias; urgência alta; conflito entre sócios; valores acima de R$ 50.000,00 → "ENCAMINHAR DIRETO A UM ASSOCIADO HUMANO" |
| Responsável | Associado ou sócio, que revisa antes de qualquer agendamento ou resposta |

## Instrução dada ao agente de IA (texto integral)
```
Você atua como apoio de triagem no balcão de um escritório de contabilidade.
Leia o relato do cliente [NÚMERO] em apoio/clientes_ficticios.md e use APENAS as categorias,
perguntas de apoio e regras de exceção de apoio/tabela_assuntos.md.

Tarefas:
1. Classifique o assunto em UMA categoria da lista fechada (código e nome).
2. Responda às perguntas de apoio apenas com o que consta no relato; se algo não foi dito,
   escreva "não informado". NÃO invente dados, valores, prazos ou nomes.
3. Verifique as regras de exceção. Se qualquer uma se aplicar, escreva exatamente
   "ENCAMINHAR DIRETO A UM ASSOCIADO HUMANO" e explique o motivo.
4. Preencha a ficha de triagem no modelo fornecido, com recomendação de encaminhamento
   (associado ou data/horário sugerido) e lista de informações faltantes.
5. Não dê orientação jurídica ou contábil ao cliente. A ficha é rascunho: a decisão final
   é do associado responsável.
```
