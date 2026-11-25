# Relatório Científico Demonstrativo — KPA Humanity: Energia para a Saúde (PKG-B-ENERGIA-SAUDE-v1.0.0)

- **Missão:** Missão B — KPA Humanity: Energia para a Saúde (`MISSION_B_ENERGIA_SAUDE`)
- **Versão:** `v1.0.0` · **Gerado em:** `2026-11-25T06:00:03-03:00`
- **Nível de Validação Científica:** **`L2`** (Cálculos verificados por duplo oráculo determinístico `solve_a == solve_b`, cenários únicos deduplicados por `family:level:seed` e proveniência explícita das fontes públicas)
- **Cenários Únicos Auditados (L2):** `24276` (de `30368` acertos L1 e `31129` execuções L0 — **`27 / 27 UFs`** cobertas)
- **Licença:** `CC-BY-4.0`

## 1. Aviso Metodológico Obrigatório (Distinção entre Tipologia Parametrizada e Unidade Individual)

> **IMPORTANTE (G1 / G8):** Os cenários deste relatório combinam **parâmetros públicos reais de referência por UF** (irradiação solar média diária GHI do **NASA POWER**, tarifas homologadas B3/A4 da **ANEEL** e faixas de consumo por porte de estabelecimento do **CNES/DATASUS**) com **sorteios paramétricos determinísticos reprodutíveis** dentro de cada faixa tipológica (`UBS Porte I/II`, `UPA 24h Porte I/II`, `Hospital Geral Público SUS`).
> - **Não representam medição física de um CNPJ/CNES individual específico.**
> - **Economias e gerações simuladas (L2) não são economias realizadas (L5).**
> - **Nenhum cenário simulado deve ser executado como obra sem vistoria local de telhado/subestação, estudo de seletividade e Anotação de Responsabilidade Técnica (ART/CREA) por engenheiro eletricista habilitado.**

## 2. Resultados Consolidados (Cenários Únicos Deduplicados — Sem Dupla Contagem)

| Eixo de Modelagem | Cenários Únicos (L2) | Indicador Principal Simulado (Tipologias) | Incerteza / Observação Técnica |
| --- | ---: | --- | --- |
| **1. Dimensionamento Solar SUS (`cnes_solar_sus`)** | 5868 | Potência: **1,811,868 kWp** · Geração: **2664143.7 MWh/ano** · Potencial bruto: **R$ 2,242,027,652/ano** | PR entre 75% e 82%; ano de 365 dias |
| **2. Otimização Ponta A4 Hospitalar (`aneel_tarifa_hospital`)** | 6205 | Custo atual: **R$ 1,454,596,990/mês** -> Otimizado: **R$ 1,016,337,460/mês** (Média: **R$ 70,630/mês** por hospital) | Deslocamento de ponta via bateria LFP + retrofit HVAC |
| **3. Viabilidade sob Incerteza Climática (`vpl_incerteza_saude`)** | 6173 | Saldo líquido médio acumulado: **P10 = R$ 615,843** · **P50 = R$ 749,183** · **P90 = R$ 882,522** | Variação interanual GHI NASA POWER (-10% / 0% / +10%) |
| **4. Autonomia de Microgrids Críticos (`energia_solar`)** | 6030 | Importação residual total: **211,912 kWh** · Reserva final em bateria: **239,665 kWh** | Balanço causal horário sem exportação líquida |

## 3. Proveniência Auditada das Fontes Públicas (G1)

| Fonte | URL Oficial | Grandezas e Unidades | Data de Referência / Validade | Natureza no Modelo |
| --- | --- | --- | --- | --- |
| **CNES / DATASUS** | `https://cnes.datasus.gov.br/` | Faixas de consumo mensal por tipologia SUS (`1.800` a `180.000 kWh/mês`) | Referência estrutural 2025/2026 | Parametrização por tipologia de porte |
| **NASA POWER (SSE)** | `https://power.larc.nasa.gov/` | Irradiação Solar Global Horizontal (`GHI` em `Wh/m²/dia`: `4.350` em SC a `5.820` no PI) | Climatologia multianual NASA SSE | Valor médio estadual real + banda P10/P50/P90 |
| **ANEEL Tarifas** | `https://www.gov.br/aneel/pt-br/assuntos/tarifas` | Tarifas de referência B3/A4 Horo-Sazonal Verde (`720` a `940 R$/MWh` fora de ponta; `3x–4x` na ponta) | Ciclo tarifário 2025/2026 | Parâmetro regulatório estadual de referência |
