# Caderno Didático Aberto de Matemática e Combinatória Aplicada — PKG-A-CORPUS-PTBR-v1.0.0

- **Missão:** Missão A — Corpus Aberto PT-BR (`MISSION_A_CORPUS_PTBR`)
- **Versão:** `v1.0.0` · **Gerado em:** `2026-11-23T11:45:02-03:00`
- **Nível de Validação Científica:** **`L2`** (Verificação matemática por duplo oráculo determinístico independente `solve_a == solve_b` + deduplicação de cenários + sanitização de conteúdo)
- **Total de Questões Únicas Verificadas (L2):** `11092` (de `11189` acertos L1 e `13421` respostas L0)
- **Licença:** `CC-BY-4.0` (Creative Commons Atribuição 4.0 Internacional)

## 1. Resumo por Família Matemática

| Família | Questões Únicas Verificadas (L2) | Níveis Cobertos | Aplicação Didática |
| --- | ---: | --- | --- |
| `aritmetica` | 1231 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `codigos_erro` | 1187 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `combinatoria` | 1259 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `contagem` | 1276 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `logistica_humanitaria` | 1188 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `mdc_mmc` | 998 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `modular` | 858 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `primos` | 643 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `recorrencia` | 1090 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |
| `sistema_linear` | 1362 | S1, S2, S3, S4, S5 | Ensino Médio, Olímpico e Superior (STEM) |

## 2. Exemplos Didáticos Reproduzíveis com Gabarito Comentado (Amostra por Família)

### Família `aritmetica` — `g4-pilot-20261115-000000` (`S1_aquecimento`, seed `216027064946189`)
- **Enunciado:** Calcule o valor inteiro exato da expressao: ((8 + 15) - 16).
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`7`**
- **Resolução Comentada (PT-BR):**
```text
1. Some os números: 8 + 15 = 23.
2. Subtraia 16: 23 - 16 = 7.

RESPOSTA: 7
```

### Família `codigos_erro` — `g4-pilot-20261115-001238` (`S1_aquecimento`, seed `116793159711813`)
- **Enunciado:** Teoria de codigos corretores de erro (comunicacao critica): considere codigos binarios de comprimento n=11 bits capazes de corrigir ate t=1 erros. Calcule o volume da esfera de Hamming V(n,t) = soma_{k=0..t} C(n,k) e o limite superior de Hamming floor(2^n / V(n,t)). Responda 'volume_esfera,limite_hamming'.
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`12,170`**
- **Resolução Comentada (PT-BR):**
```text
RESPOSTA: 12,170
```

### Família `combinatoria` — `g4-pilot-20261115-000003` (`S1_aquecimento`, seed `85769778753907`)
- **Enunciado:** Quantas combinacoes simples C(11,3) existem?
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`165`**
- **Resolução Comentada (PT-BR):**
```text
A combinação simples é calculada por:

\[
C(11,3)=\frac{11!}{3!(11-3)!}
=\frac{11\cdot10\cdot9}{3\cdot2\cdot1}
=\frac{990}{6}
=165
\]

RESPOSTA: 165
```

### Família `contagem` — `g4-pilot-20261115-000007` (`S1_aquecimento`, seed `34942593684909`)
- **Enunciado:** Quantos inteiros k com 1<=k<=29 sao divisiveis por 6 OU por 11, mas NAO por ambos?
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`6`**
- **Resolução Comentada (PT-BR):**
```text
Múltiplos de 6 em 1..29: 6, 12, 18, 24 → 4
Múltiplos de 11 em 1..29: 11, 22 → 2
Múltiplos de ambos (lcm(6,11) = 66): nenhum em 1..29 → 0

Como não há sobreposição, "divisível por um mas não pelo outro" = (4 - 0) + (2 - 0) = 6. Lista: 6, 11, 12, 18, 22, 24.

RESPOSTA: 6
```

### Família `logistica_humanitaria` — `g4-pilot-20261115-001236` (`S1_aquecimento`, seed `173919021992411`)
- **Enunciado:** Logistica humanitaria de emergencia: um veiculo de resgate tem capacidade maxima de carga de 10 kg. Existem 4 kits medicos/alimentares indivisiveis (cada kit pode ser levado no maximo 1 vez), descritos por (peso_kg, impacto_vidas):
K1:(2 kg, 26 vidas), K2:(7 kg, 22 vidas), K3:(8 kg, 25 vidas), K4:(5 kg, 25 vidas)
Determine o valor maximo de impacto_vidas total que pode ser transportado sem exceder 10 kg.
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`51`**
- **Resolução Comentada (PT-BR):**
```text
RESPOSTA: 51
```

### Família `mdc_mmc` — `g4-pilot-20261115-000002` (`S1_aquecimento`, seed `239463460552577`)
- **Enunciado:** Determine o MDC e o MMC de 31426 e 20064. Responda 'mdc,mmc'.
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`38,16592928`**
- **Resolução Comentada (PT-BR):**
```text
 algoritmo de Euclides:

\[
\begin{aligned}
31426 &= 1\cdot20064 + 11362\\
20064 &= 1\cdot11362 + 8702\\
11362 &= 1\cdot8702 + 2660\\
8702 &= 3\cdot2660 + 722\\
2660 &= 3\cdot722 + 494\\
722 &= 1\cdot494 + 228\\
494 &= 2\cdot228 + 38\\
228 &= 6\cdot38
\end{aligned}
\]

Logo, \(\operatorname{MDC}(31426,20064)=38\).

\[
\operatorname{MMC}=\frac{31426\cdot20064}{38}=16592928
\]

RESPOSTA: 38,16592928
```

### Família `modular` — `g4-pilot-20261115-000001` (`S1_aquecimento`, seed `131943789786344`)
- **Enunciado:** Calcule 37^26 mod 679.
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`340`**
- **Resolução Comentada (PT-BR):**
```text
Por quadrados sucessivos, módulo \(679\):

\[
\begin{aligned}
37^2 &\equiv 11,\\
37^4 &\equiv 11^2=121,\\
37^8 &\equiv 121^2\equiv 382,\\
37^{16} &\equiv 382^2\equiv 618.
\end{aligned}
\]

Como \(26=16+8+2\):

\[
37^{26}\equiv 618\cdot382\cdot11\pmod{679}.
\]

\[
618\cdot382\equiv463\pmod{679},\qquad
463\cdot11=5093\equiv340\pmod{679}.
\]

RESPOSTA: 340
```

### Família `primos` — `g4-pilot-20261115-000005` (`S1_aquecimento`, seed `114607715905841`)
- **Enunciado:** Quantos numeros primos existem entre 1 e 65 (inclusive)?
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`18`**
- **Resolução Comentada (PT-BR):**
```text
Para cada número de 2 a 65, verificamos se é divisível por algum primo até sua raiz quadrada: 2, 3, 5 ou 7.

Os números primos são:
2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61.

Há 18 números primos. O número 1 não é primo.

RESPOSTA: 18
```

### Família `recorrencia` — `g4-pilot-20261115-000006` (`S1_aquecimento`, seed `198548632642424`)
- **Enunciado:** Seja a_0=2, a_1=4 e a_k = 2*a_(k-1) + (0)*a_(k-2) para k>=2. Calcule a_16.
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`131072`**
- **Resolução Comentada (PT-BR):**
```text
Para \(k\ge 2\), o termo \(0\cdot a_{k-2}\) não altera o cálculo:

\[
a_k=2a_{k-1}.
\]

Assim, a sequência tem razão \(2\), começando com \(a_1=4\):

\[
a_{16}=a_1\cdot 2^{16-1}=4\cdot 2^{15}=2^{17}=131072.
\]

RESPOSTA: 131072
```

### Família `sistema_linear` — `g4-pilot-20261115-000004` (`S1_aquecimento`, seed `129892270160408`)
- **Enunciado:** Resolva o sistema linear (variaveis x1..x2):
(-5)x1 + (2)x2 = 8
(-7)x1 + (6)x2 = 24
Responda 'x1,x2,...'.
Resolva passo a passo, de forma concisa. Termine com uma unica linha final no formato exato 'RESPOSTA: <valor>' (listas separadas por virgula, sem espacos; fracoes como a/b).
- **Gabarito Verificado por Duplo Oráculo (`solve_a == solve_b`):** **`0,4`**
- **Resolução Comentada (PT-BR):**
```text
Multiplicando a primeira equação por 3:

\[
-15x_1+6x_2=24
\]

Subtraindo a segunda equação:

\[
(-15x_1+6x_2)-(-7x_1+6x_2)=24-24
\]

\[
-8x_1=0 \Rightarrow x_1=0
\]

Substituindo na primeira equação:

\[
-5(0)+2x_2=8 \Rightarrow x_2=4
\]

RESPOSTA: 0,4
```
