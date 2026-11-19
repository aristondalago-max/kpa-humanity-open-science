# Metodologia, Schema, Licenciamento e Limitações — PKG-A-CORPUS-PTBR-v1.0.0

## 1. Contrato de Validade Científica (L0–L5)
- **L0 (Bruto IA):** Resposta textual estruturada retornada pelo modelo.
- **L1 (Verificação Matemática Automatizada):** Resposta final validada contra dois algoritmos determinísticos independentes (`solve_a` e `solve_b`).
- **L2 (Proveniência e Deduplicação Auditadas — Nível atual deste pacote):** Cenários deduplicados por assinatura `family:level:seed` (excluindo pares de teste de consistência) e varridos contra dados sensíveis.
- **L3 (Revisão Metodológica/Pedagógica Independente):** Revisão humana por docentes de matemática.
- **L4 (Publicação Aprovada):** Pacote homologado e publicado em repositório público.
- **L5 (Impacto Externo Confirmado):** Reutilização didática documentada em escolas, universidades ou projetos abertos.

## 2. Limitações e Uso Responsável
- O gabarito numérico (`expected_dual_oracle`) tem garantia matemática determinística de 100% (oráculo duplo em Python).
- O texto explicativo intermediário (`solution_ptbr`) foi redigido por modelo de linguagem (`claude-fable-5-1`) sem expor cadeias privadas de pensamento; recomenda-se supervisão docente ao utilizar os passos intermediários em sala de aula.

## 3. Canal de Feedback e Correções
- Para reportar correções pedagógicas, registrar reutilização didática (L5) ou solicitar novas listas de exercícios, utilize o formulário estruturado em `FEEDBACK_TEMPLATE.json` ou o endpoint de feedback do KPA Humanity Delivery.
