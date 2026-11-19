# Documentação Metodológica, Fontes Públicas, Equações e Limitações

## 1. Arquitetura de Verificação por Duplo Oráculo Independente (`solve_a == solve_b`)

Nenhum problema deste repositório depende da resposta do modelo de linguagem para definir o gabarito. Para cada uma das **14 famílias** (nos níveis de dificuldade `S1_aquecimento` a `S5_extremo`), o gerador constrói uma instância determinística a partir de uma `seed` auditável e executa **dois algoritmos matematicamente independentes (`solve_a` e `solve_b`)**:

| Família | Missão | Algoritmo Oráculo A (`solve_a`) | Algoritmo Oráculo B (`solve_b`) | Formato do Gabarito |
| --- | --- | --- | --- | --- |
| `aritmetica` | A | Avaliação recursiva direta da árvore sintática | Conversão pós-fixa (RPN) avaliada em pilha com `fractions.Fraction` | `int` |
| `modular` | A | Exponenciação modular nativa `pow(a, b, m)` | Exponenciação binária iterativa bit a bit (*square-and-multiply*) | `int` |
| `mdc_mmc` | A | Algoritmo de Euclides (`math.gcd` / `math.lcm`) | Fatoração explícita em números primos e produto de potências mínimas/máximas | `mdc,mmc` |
| `combinatoria` | A | Coeficiente binomial via `math.comb(n, k)` | Produto multiplicativo exato em aritmética racional `Fraction` | `int` |
| `sistema_linear` | A | Eliminação de Gauss-Jordan com pivoteamento em `Fraction` | Regra de Cramer / substituição algébrica exata | `x1,x2,...` |
| `primos` | A | Crivo de Eratóstenes em `bytearray` | Teste de primalidade por divisão até $\lfloor\sqrt{n}\rfloor$ para cada inteiro | `int` |
| `recorrencia` | A | Iteração linear sequencial de 2ª ordem | Exponenciação rápida da matriz de transição $2\times 2$ | `int` |
| `contagem` | A | Princípio da Inclusão-Exclusão ($\lfloor n/a\rfloor + \lfloor n/b\rfloor - 2\lfloor n/\text{mmc}(a,b)\rfloor$) | Varredura explícita com operador XOR de divisibilidade | `int` |
| `logistica_humanitaria` | A | Programação Dinâmica 1D ($DP[w]$) para Mochila 0/1 | Busca recursiva exata (*Branch-and-Bound*) por subconjuntos | `int` |
| `codigos_erro` | A | Somatório da esfera de Hamming via `math.comb` e divisão inteira $2^n // V(n,t)$ | Construção iterativa do Triângulo de Pascal e deslocamento binário $(1\ll n) // V(n,t)$ | `volume,limite` |
| `energia_solar` | B | Simulação passo a passo do estado de carga (SoC) da bateria | Recorrência algébrica de Lindley truncada em `[0, C]` com `Fraction` | `importacao,carga_final` |
| `cnes_solar_sus` | B | Aritmética inteira escalada para potência de pico ($\text{kWp}$), geração anual ($\text{kWh}$) e economia bruta ($\text{R\$}$) | Aritmética racional exata (`Fraction`) com arredondamento de teto/piso | `KWp_min,G_ano,Econ_ano` |
| `aneel_tarifa_hospital` | B | Comparação direta de fatura mensal A4 Verde antes e após deslocamento de ponta | Decomposição marginal da economia ($S_p T_p + S_{fp} T_{fp}$) | `Custo_atual,Custo_otim,Econ_mes` |
| `vpl_incerteza_saude` | B | Fluxo de caixa líquido acumulado em inteiros para $P_{10}$ ($-10\%$), $P_{50}$ e $P_{90}$ ($+10\%$) | Soma explícita período a período em aritmética racional `Fraction` | `V_10,V_50,V_90` |

## 2. Proveniência e Parametrização das Fontes Públicas na Missão B

1. **CNES / DATASUS (`https://cnes.datasus.gov.br/`):** Define as 5 classes tipológicas (`UBS Porte I`: `1.800–4.500 kWh/mês`; `UBS Porte II com Rede de Frio`: `4.500–9.500 kWh/mês`; `UPA 24h Porte I`: `14.000–28.000 kWh/mês`; `UPA 24h Porte II`: `28.000–52.000 kWh/mês`; `Hospital Geral Público SUS`: `65.000–180.000 kWh/mês`).
2. **NASA POWER (`https://power.larc.nasa.gov/`):** Fornece a irradiação solar global horizontal média diária (`GHI` em $\text{Wh/m}^2/\text{dia}$) para as 27 capitais estaduais brasileiras (de `4.350 Wh/m²/dia` em Florianópolis-SC a `5.820 Wh/m²/dia` em Teresina-PI).
3. **ANEEL (`https://www.gov.br/aneel/pt-br/assuntos/tarifas`):** Fornece as tarifas estaduais de referência (`720` a `940 R$/MWh` fora de ponta e multiplicador de ponta A4 Horo-Sazonal Verde de $3\times$ a $4\times$).

## 3. Limitações de Aplicação

- **Cenários Sintéticos vs. Medições Reais:** Os valores de consumo mensal, capacidade de bateria e CAPEX dentro de cada tipologia são gerados por sorteio pseudoaleatório determinístico (`seed`) dentro das faixas reais de porte. Portanto, **são cenários sintéticos de referência metodológica e não representam economias realizadas em hospitais específicos**.
- **Requisitos para Projeto Executivo:** A aplicação em qualquer estabelecimento real do SUS exige medição física de curva de carga de 15 minutos, avaliação estrutural de coberturas, parecer de acesso junto à distribuidora local (PRODIST/ANEEL) e ART registrada no CREA.
