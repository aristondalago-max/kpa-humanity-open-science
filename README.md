# KPA Humanity — Open Science: Educação Matemática & Energia para a Saúde Pública

- **Versão do Release:** `v1.0.0` · **Atualizado em:** `2026-11-26T08:15:04-03:00`
- **Licença:** `CC-BY-4.0` (Creative Commons Atribuição 4.0 Internacional)
- **Nível de Validação Científica Atual:** **`L2`** (Verificação matemática automatizada por duplo oráculo determinístico independente `solve_a == solve_b` + proveniência de fontes públicas auditada + deduplicação estrita de cenários)

---

## Aviso Metodológico Essencial (Transparência Científica)

> **ATENÇÃO — CENÁRIOS SINTÉTICOS PARAMETRIZADOS (NÃO SÃO ECONOMIAS REALIZADAS):**
> 1. Os estudos da **Missão B (Energia para a Saúde)** neste repositório são **cenários sintéticos parametrizados** construídos sobre dados públicos oficiais de referência por Unidade da Federação (**CNES/DATASUS** para tipologias de porte do SUS, **NASA POWER** para irradiação solar GHI estadual e **ANEEL** para tarifas de referência B3/A4 Horo-Sazonal Verde).
> 2. **Eles NÃO representam medições físicas individuais de um CNPJ/CNES específico e NÃO representam economias financeiras já realizadas em hospitais reais (Nível L5).**
> 3. Nenhum cenário simulado deve ser utilizado como projeto executivo de engenharia sem vistoria presencial de telhado/subestação, análise de faturas reais e Anotação de Responsabilidade Técnica (ART/CREA) por engenheiro eletricista habilitado.

---

## 1. Estrutura dos Pacotes Públicos (`v1.0.0`)

| Pacote | Missão | Cenários Únicos Validados (L2) | Conteúdo Principal |
| --- | --- | ---: | --- |
| [`PKG-A-CORPUS-PTBR-v1.0.0`](./PKG-A-CORPUS-PTBR-v1.0.0/) | **Missão A — Corpus Aberto PT-BR** | **22,400** (de 22,497 acertos L1) | Questões e resoluções passo a passo em português (10 famílias: aritmética, modular, MDC/MMC, combinatória, sistemas lineares, primos, recorrência, contagem, logística humanitária e códigos corretores de erro) em JSONL, CSV e Caderno Didático Markdown. |
| [`PKG-B-ENERGIA-SAUDE-v1.0.0`](./PKG-B-ENERGIA-SAUDE-v1.0.0/) | **Missão B — Energia para a Saúde** | **31,379** (de 39,241 acertos L1 · **27/27 UFs**) | Modelagem energética reproduzível para tipologias públicas do SUS (dimensionamento solar fotovoltaico, otimização tarifária ponta/fora-ponta A4, análise de incerteza climática P10/P50/P90 e autonomia de microrredes com baterias) em JSONL, CSV e Relatório Científico. |

---

## 2. Contrato de Validade Científica (`L0` a `L5`)

- **`L0` — Resultado Bruto da IA:** Resposta estruturada produzida pelo modelo avaliado.
- **`L1` — Verificação Matemática Automatizada:** Resposta validada contra **dois algoritmos determinísticos independentes (`solve_a == solve_b`)**.
- **`L2` — Proveniência, Hipóteses e Deduplicação Auditadas (Nível atual deste repositório):** Cenários deduplicados por assinatura `family:level:seed` (excluindo pares de teste de consistência para evitar dupla contagem), sanitizados e com fontes públicas documentadas.
- **`L3` — Revisão Metodológica Independente:** Revisão externa por docentes de matemática (Missão A) e engenheiros hospitalares/pesquisadores em energia solar (Missão B).
- **`L4` — Publicação Aprovada e Documentada:** Release público com manifesto SHA-256 verificado.
- **`L5` — Utilização ou Impacto Externo Confirmado:** Comprovação externa real de adoção didática ou uso em estudo de viabilidade.

---

## 3. Síntese dos Cenários Simulados na Missão B (Tipologias Parametrizadas — L2 Deduplicado)

- **Dimensionamento Solar Fotovoltaico (`cnes_solar_sus`, 7572 cenários únicos):** Potência total simulada de **2,339,239 kWp**, geração estimada de **3439815.1 MWh/ano** e potencial bruto simulado de **R$ 2,894,221,026/ano**.
- **Otimização Tarifária Ponta/Fora-Ponta A4 (`aneel_tarifa_hospital`, 8015 cenários únicos):** Redução média simulada de **R$ 70,741/mês por unidade hospitalar** via deslocamento de ponta com armazenamento LFP e retrofit de climatização.
- **Análise de Incerteza Climática NASA POWER (`vpl_incerteza_saude`, 7986 cenários únicos):** Saldo líquido médio simulado em **P10 (conservador) = R$ 616,221**, **P50 (mediano) = R$ 749,561** e **P90 (favorável) = R$ 882,901**.
- **Autonomia de Microrredes Críticas (`energia_solar`, 7806 cenários únicos):** Importação residual acumulada de **276,461 kWh** e reserva final de bateria de **306,413 kWh**.

---

## 4. Exemplos de Uso Reproduzíveis (Python)

```python
import json
import hashlib

# 1. Carregar e verificar o Corpus Aberto PT-BR (Missao A)
with open('PKG-A-CORPUS-PTBR-v1.0.0/dataset_corpus_ptbr_l2.jsonl', encoding='utf-8') as f:
    corpus = [json.loads(line) for line in f]
print(f'Total de questoes unicas L2: {len(corpus)}')
print('Exemplo:', corpus[0]['family'], '-> Gabarito Oraculo Duplo:', corpus[0]['expected_dual_oracle'])

# 2. Carregar os cenarios sinteticos de Energia para a Saude (Missao B)
with open('PKG-B-ENERGIA-SAUDE-v1.0.0/dataset_energia_saude_l2.jsonl', encoding='utf-8') as f:
    estudos = [json.loads(line) for line in f]
print(f'Total de cenarios sinteticos unicos L2: {len(estudos)}')
```

---

## 5. Como Contribuir, Reportar Erros ou Registrar Revisão Metodológica (`L3`/`L5`)

1. Consulte [`METHODOLOGY_AND_LIMITATIONS.md`](./METHODOLOGY_AND_LIMITATIONS.md) para todas as equações, fontes e hipóteses.
2. Utilize o modelo [`PKG-A-CORPUS-PTBR-v1.0.0/FEEDBACK_TEMPLATE.json`](./PKG-A-CORPUS-PTBR-v1.0.0/FEEDBACK_TEMPLATE.json) para abrir uma Issue neste repositório reportando correções pedagógicas, validação de engenharia (`L3`) ou reutilização confirmada (`L5`).
