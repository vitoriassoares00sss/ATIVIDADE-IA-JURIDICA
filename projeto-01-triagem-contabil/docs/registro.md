# Registro de testes – Projeto 01

Ferramenta de IA usada: Claude (chat). Todos os dados são fictícios.

| Tarefa | Instrução | Fonte | Verificação | Erro | Correção |
|---|---|---|---|---|---|
| Classificar o Cliente 02 e gerar ficha de triagem com encaminhamento | Protocolo de `docs/protocolo.md` com [NÚMERO] = 02 | `apoio/clientes_ficticios.md` (cliente 02) e `apoio/tabela_assuntos.md` | Conferi manualmente: categoria A4 consta na tabela; multa R$ 500,00 e prazo 28/10/2026 batem com o relato; regra "multa ≤ R$ 5.000 e prazo > 5 dias" aplicada corretamente; nenhuma exceção cabível | Nenhum dado inventado. Risco observado: a data sugerida (20/10) é só uma sugestão, a IA não conhece a agenda real do escritório | Ficha mantém campo de revisão do associado; agenda deve ser confirmada por humano |
| Teste de exceção: Cliente 03 (conflito entre sócios, R$ 180.000) | Mesmo protocolo com [NÚMERO] = 03 | Cliente 03 + regras de exceção da tabela | Conferi: as 3 exceções (urgência alta, conflito, valor > R$ 50.000) foram citadas e a frase "ENCAMINHAR DIRETO A UM ASSOCIADO HUMANO" apareceu | Categoria A2 foi só provisória (o caso é societário/jurídico, fora do escopo contábil) | Ficha registra enquadramento provisório e que a decisão é do associado |

## Riscos concretos identificados
1. **Dado que não poderia ser enviado (caso real):** CPF/CNPJ, valores e relato de conflito societário de cliente real não devem ir a IA pública (sigilo profissional e LGPD).
2. **Falta de revisão humana:** sem a revisão do associado, a IA poderia agendar ou orientar um caso sensível (conflito entre sócios).
3. **Excesso de confiança na classificação:** a IA tende a encaixar o caso numa categoria mesmo quando não cabe bem (ex.: Cliente 04, assunto jurídico não contábil, deve cair na exceção "fora das categorias").
