# Carta Técnica de Encaminhamento e Convite à Revisão Metodológica (`L2 -> L3`)

- **Destinatário:** Grupo Fotovoltaica / UFSC — Laboratório de Energia Solar da Universidade Federal de Santa Catarina (`https://fotovoltaica.ufsc.br/`)
- **Pacote Submetido:** `PKG-B-ENERGIA-SAUDE-v1.0.0` (`2,425` cenários sintéticos únicos auditados nas 27 UFs)
- **Manifesto SHA-256:** `5dd8dba632db0220a4f89232e221bd5a0169d8d0a523c27e1569576caf9b045d` · **Licença:** `CC-BY-4.0`

## 1. Objeto da Submissão Científica Aberta

Encaminhamos ao **Grupo Fotovoltaica / UFSC** a base aberta `PKG-B-ENERGIA-SAUDE-v1.0.0`, contendo **`2,425` cenários sintéticos parametrizados** de dimensionamento solar fotovoltaico (`PR 0,75–0,82`), viabilidade sob incerteza interanual (`P10/P50/P90` de GHI **NASA POWER**), otimização horo-sazonal `A4 Verde` (**ANEEL**) e balanço horário de microgrids críticos para tipologias de unidades públicas de saúde (**CNES/DATASUS**: `UBS Porte I/II`, `UPA 24h`, `Hospital Geral SUS`) nas **27 Unidades da Federação**.

## 2. Declaração Metodológica de Cenários Sintéticos

Todos os registros desta base são **cenários sintéticos parametrizados por tipologia de porte** com verificação matemática por duplo oráculo determinístico independente (`solve_a == solve_b`), e **não representam medições físicas nem economias realizadas em hospitais específicos**.

## 3. Convite à Revisão Metodológica Independente (`Nível L3`)

Convidamos pesquisadores e discentes do **Fotovoltaica/UFSC** a auditar as hipóteses de Performance Ratio (`PR`), bandas de incerteza climática e curvas de despacho de baterias LFP, registrando críticas, correções ou extensões via `FEEDBACK_TEMPLATE.json` ou Issues no repositório `https://github.com/aristondalago-max/kpa-humanity-open-science`.
