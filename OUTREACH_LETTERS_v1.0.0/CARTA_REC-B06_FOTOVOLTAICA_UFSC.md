# Carta Técnica de Encaminhamento e Convite à Revisão Metodológica (`L2 -> L3`)

- **Destinatário:** Grupo Fotovoltaica / UFSC — Laboratório de Energia Solar da Universidade Federal de Santa Catarina (`https://fotovoltaica.ufsc.br/`)
- **Pacote Submetido:** `PKG-B-ENERGIA-SAUDE-v1.0.0` (`20,362` cenários sintéticos únicos auditados nas 27 UFs)
- **Manifesto SHA-256:** `c6c0dbb4e2193c04b09b74ff266b8fb3d1141a72b979d6a7914fe7fee7e8d535` · **Licença:** `CC-BY-4.0`

## 1. Objeto da Submissão Científica Aberta

Encaminhamos ao **Grupo Fotovoltaica / UFSC** a base aberta `PKG-B-ENERGIA-SAUDE-v1.0.0`, contendo **`20,362` cenários sintéticos parametrizados** de dimensionamento solar fotovoltaico (`PR 0,75–0,82`), viabilidade sob incerteza interanual (`P10/P50/P90` de GHI **NASA POWER**), otimização horo-sazonal `A4 Verde` (**ANEEL**) e balanço horário de microgrids críticos para tipologias de unidades públicas de saúde (**CNES/DATASUS**: `UBS Porte I/II`, `UPA 24h`, `Hospital Geral SUS`) nas **27 Unidades da Federação**.

## 2. Declaração Metodológica de Cenários Sintéticos

Todos os registros desta base são **cenários sintéticos parametrizados por tipologia de porte** com verificação matemática por duplo oráculo determinístico independente (`solve_a == solve_b`), e **não representam medições físicas nem economias realizadas em hospitais específicos**.

## 3. Convite à Revisão Metodológica Independente (`Nível L3`)

Convidamos pesquisadores e discentes do **Fotovoltaica/UFSC** a auditar as hipóteses de Performance Ratio (`PR`), bandas de incerteza climática e curvas de despacho de baterias LFP, registrando críticas, correções ou extensões via `FEEDBACK_TEMPLATE.json` ou Issues no repositório `https://github.com/aristondalago-max/kpa-humanity-open-science`.
