# Atualização do Quadro de Vagas SES/SP — 2026-09-22

Registro das alterações feitas no painel (`index.html`) a partir da nova versão
de `Quadro de Vagas SES_2027.xlsx`, e do que mudou em relação aos dados que
estavam publicados antes.

## 1. O que mudou nos arquivos

| Arquivo | Situação |
|---|---|
| `Quadro de Vagas SES_2027.xlsx` | Atualizado pelo usuário em 22/09/2026 — fonte de instituições, especialidades e vagas (credenciadas/ofertadas/ocupadas/projetadas). |
| `Quadro resumo total de vagas 2027.xlsx` | **Não foi alterado** (última modificação: 19/08/2026) — continua sendo a fonte dos dados financeiros (tarifa, valor pago 2026/2027). |
| `vagas-residencia-sesp/index.html` | Regenerado: bloco `DATA` (instituições/especialidades/vagas) recalculado a partir da nova planilha; bloco `FIN_DATA` (financeiro) mantido sem alteração; título (H1) alterado. |

Commit: `e863a1c` — publicado em `main` e já refletido em
https://edufabc.github.io/vagas-residencia-sesp/.

**Ajuste seguinte (mesmo dia, ainda não publicado):** remoção da PREFEITURA
MUNICIPAL DE GUARULHOS e unificação de "Faculdade de Medicina de Bauru da
Universidade de São Paulo" com "Hospital de Reabilitação de Anomalias
Craniofaciais da Universidade de São Paulo" — ver seção 3b. Isso fechou a
contagem em **68 instituições**, batendo exatamente com a planilha
financeira.

## 2. Título do painel

| Antes | Depois |
|---|---|
| Vagas de Residência Médica na Secretaria de Estado da Saúde de São Paulo | **VAGAS/BOLSAS DE RESIDÊNCIA MÉDICA/SES/SÃO PAULO** |

## 3. Instituições removidas (79 → 70)

O usuário retirou da planilha as instituições que **apenas usam o concurso de
residência (CNRM) mas não recebem financiamento/bolsa da SES/SP**. Isso foi
confirmado nos dados: todas as 9 instituições abaixo tinham vagas
**ofertadas = ocupadas = projetadas = 0** em todos os seus programas —
só apareciam com "vagas credenciadas" (autorização do CNRM), nunca com vaga
paga pelo estado.

| Instituição | Programas | Vagas credenciadas | Especialidades |
|---|---:|---:|---|
| HOSPITAL E MATERNIDADE SALVALUS | 4 | 36 | Cirurgia Geral, Ginecologia e Obstetrícia, Pediatria, Urologia |
| HOSPITAL E MATERNIDADE SÃO CRISTÓVÃO | 5 | 39 | Anestesiologia, Cirurgia Geral, Cirurgia Plástica, Ortopedia e Traumatologia, Pediatria |
| Hospital Municipal Dr. José De Carvalho Florence | 12 | 120 | Anestesiologia, Cirurgia Geral, Clínica Médica, Ginecologia e Obstetrícia, Medicina de Emergência, Medicina Intensiva, Medicina Intensiva Pediátrica, Neonatologia, Neurologia, Ortopedia e Traumatologia, Pediatria, Urologia |
| HOSPITAL SEPACO | 7 | 50 | Anestesiologia, Cirurgia Geral, Clínica Médica, Ginecologia e Obstetrícia, Medicina Intensiva, Medicina Intensiva Pediátrica, Pediatria |
| INSTITUTO DAS PEQUENAS MISSIONÁRIAS DE MARIA IMACULADA - OBRA DE AÇÃO SOCIAL PIO XII | 4 | 18 | Cardiologia Clínica, Clínica Médica, Mastologia, Oncologia Clínica |
| INSTITUTO DE PESQUISA E DESENVOLVIMENTO SOCIAL E TECNOLÓGICO - Anhembi-Morumbi/Piracicaba | 2 | 29 | Clínica Médica, Pediatria |
| OSASCO PREFEITURA MUNICIPAL | 1 | 27 | Ginecologia e Obstetrícia |
| QUARTEIRÃO DA SAÚDE DE DIADEMA | 1 | 9 | Oftalmologia |
| SANTA CASA DE MISERICÓRDIA DE BARRETOS | 15 | 139 | Cardiologia, Cirurgia Cardiovascular, Cirurgia Geral, Cirurgia Plástica, Clínica Médica, Dermatologia, Geriatria, Ginecologia e Obstetrícia, Infectologia, Nefrologia, Neurologia, Ortopedia e Traumatologia, Otorrinolaringologia, Pediatria, Psiquiatria |
| **Total removido** | **51** | **467** | — |

Nenhuma instituição nova entrou na planilha — a redução foi só por remoção.

## 3b. Ajuste fino: 70 → 68 instituições

Depois da primeira rodada, restavam 70 instituições — 2 a mais que as 68 da
planilha financeira, porque 2 delas não tinham tarifa cadastrada lá:
"FACULDADE DE MEDICINA DE BAURU DA UNIVERSIDADE DE SÃO PAULO" e
"PREFEITURA MUNICIPAL DE GUARULHOS". O usuário resolveu os dois casos:

**a) Remoção — PREFEITURA MUNICIPAL DE GUARULHOS**
Mesmo padrão das 9 instituições da seção 3: 6 programas, 59 vagas
credenciadas, **ofertadas = ocupadas = projetadas = 0** em todos — só usava
o concurso, sem financiamento SES/SP.
Especialidades: Anestesiologia, Cirurgia Geral, Ginecologia e Obstetrícia,
Medicina de Família e Comunidade, Pediatria, Psiquiatria.

**b) Unificação — Faculdade de Medicina de Bauru ↔ Hospital de Reabilitação
de Anomalias Craniofaciais (USP)**
O usuário indicou que são a mesma instituição. Os 10 programas que estavam
sob "Faculdade de Medicina de Bauru da Universidade de São Paulo" foram
reatribuídos para "Hospital de Reabilitação de Anomalias Craniofaciais da
Universidade de São Paulo" (nome que já tinha tarifa cadastrada na planilha
financeira), somando-se aos 5 programas que já existiam ali — 15 programas
no total, sem nenhuma sobreposição de especialidade+duração entre os dois
conjuntos.

Essa unificação corrigiu uma lacuna real nos valores pagos: o programa
"Cirurgia Crânio-Maxilo-Facial" (1 ano), com 1 vaga ocupada em 2026, estava
sob o nome "Faculdade de Medicina de Bauru" e por isso nunca entrava no
cálculo financeiro (sem tarifa associada). Unificado, essa vaga passou a ser
contabilizada pela tarifa da instituição (R$ 3.480,32/mês), acrescentando
cerca de **R$ 41,8 mil/ano** ao total pago que antes estava subcontado.

Resultado: **70 → 68 instituições**, e a lista de vagas passa a bater 100%
com a planilha financeira (nenhuma instituição sem tarifa).

## 4. Especialidades (139 → 143)

Nenhuma especialidade que já existia foi removida. Quatro nomes de
especialidade apareceram pela primeira vez na nova planilha:

- PATOLOGIA
- ONCOGENÉTICA - 1 ANO
- MEDICINA FÍSICA E REABILITAÇÃO 1 ANO - PROOGRAMA NOVO *(grafia mantida como está na planilha)*
- MEDICINA DE FAMÍLIA E COMUNIDADE - Saúde Mental

A grafia/caixa de todas as especialidades e instituições que já existiam foi
mantida igual à do painel anterior (normalização é só visual — nenhum valor
numérico foi alterado), para não gerar inconsistência de exibição.

## 5. Números gerais — antes x depois

| Indicador | Antes (79 inst.) | Depois (68 inst.) | Diferença |
|---|---:|---:|---:|
| Instituições | 79 | 68 | −11 |
| Especialidades | 139 | 143 | +4 |
| Programas de residência cadastrados | 1.106 | 1.056 | −50 |
| Vagas credenciadas | 14.810 | 14.341 | −469 |
| Vagas ofertadas | 6.825 | 6.849 | +24 |
| Vagas ocupadas em 2026 | 6.532 | 6.531 | −1 |
| Vagas projetadas para 2027 | 6.714 | 6.751 | +37 |

A queda em "vagas credenciadas" não é só efeito das remoções (79 − 11 = 68):
ao mesmo tempo, algumas instituições que permaneceram tiveram valores
atualizados (para cima e para baixo) nesta nova versão da planilha.

## 6. Dados financeiros (aba "Dados Financeiros")

A planilha-fonte (`Quadro resumo total de vagas 2027.xlsx`, 68 instituições
com tarifa) **não foi alterada**. Mas o valor pago é recalculado ao vivo pelo
painel (vagas ocupadas × tarifa da instituição), então a unificação
Bauru/Craniofaciais da seção 3b passou a contar 1 vaga ocupada que antes
ficava de fora por falta de tarifa associada:

| | Antes do ajuste 3b | Depois do ajuste 3b |
|---|---:|---:|
| Instituições financiadas (sem lacuna) | 66 de 68 (2 sem tarifa) | **68 de 68** |
| Total pago por ano (2026) | R$ 276.802.901,76 | R$ 276.844.665,60 |
| Projeção paga por ano (2027) | ≈ R$ 286,2 mi | R$ 286,3 mi |

Não há mais nenhuma instituição da lista de vagas sem tarifa correspondente
na planilha financeira.

## 7. Verificação

- Página renderizada localmente com Playwright em cada rodada: sem erros de
  JavaScript, KPIs, ranking e abas (Vagas / Financeiro) exibindo
  corretamente.
- `git diff` conferido linha a linha antes do commit da primeira rodada;
  bloco `FIN_DATA` confirmado byte-a-byte idêntico ao anterior.
- Primeira rodada (79→70, título): commit `e863a1c`, publicado via
  `git push origin main` e já no ar em
  https://edufabc.github.io/vagas-residencia-sesp/.
- Segunda rodada (70→68, seção 3b): aplicada localmente e verificada
  (68 instituições, 1.056 programas, 0 lacunas com a planilha financeira) —
  **ainda não commitada nem publicada**, aguardando confirmação.
