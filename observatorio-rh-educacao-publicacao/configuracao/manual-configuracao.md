# Manual de configuração municipal

## Objetivo

Orientar a criação e manutenção de parâmetros para auditorias no Observatório RH Educação. O arquivo de configuração contém regras, não dados de servidores ou alunos.

## Formas de configuração

### Por arquivo

1. Faça uma cópia de `modelo-configuracao-municipal.json`.
2. Preencha município, rede, identificação, versão e vigência.
3. Cadastre uma entrada em `parametros` para cada cargo ou grupo.
4. Escolha `tipo_regra` e `unidade_analise` compatíveis.
5. Descreva fórmula, limites, condições e exceções.
6. Informe a fonte normativa ou administrativa, com identificação e artigo/item quando houver.
7. Enquanto não houver validação, mantenha `status` como `pendente_validacao`.

### Por conversa

Informe cargo, unidade de aplicação, parâmetro, condições, exceções, fonte e vigência. A regra estruturada deve ser apresentada em resumo e confirmada antes de ser aplicada.

### Combinação

O arquivo pode ser complementado por conversa. Se houver divergência, apresente o valor do arquivo e a alteração solicitada; não escolha silenciosamente. A regra só deve ser aplicada após confirmação explícita.

## Tipos de regra

- `proporcional`: razão entre quantidade observada e parâmetro.
- `faixas`: intervalos e referências.
- `por_turma`: regra aplicada à turma, podendo depender de etapa, alunos, horários e simultaneidade.
- `por_turno`: regra dependente dos turnos de funcionamento.
- `por_jornada`: regra dependente de carga horária, módulos ou escala.
- `composicao`: combinação de funções ou requisitos mínimos.
- `mapeamento`: identificação e distribuição sem cálculo de quantitativo ideal.
- `personalizada`: regra excepcional com fórmula e condições documentadas.

## Campos essenciais

`id`, `cargo_grupo`, `tipo_regra`, `unidade_analise`, `status`, `regra`, `condicoes`, `excecoes`, `fonte`, `vigencia` e `notas`.

## Validação antes da auditoria

Verifique campos obrigatórios, tipos, unidades, fórmulas, limites sem lacunas ou sobreposições, compatibilidade com os dados, vigência, fonte, conflitos e campos que não podem ser calculados. Regras ambíguas, incompletas ou não confirmadas devem ser classificadas como pendentes ou inconclusivas.

## Reprodutibilidade

Cada mudança deve gerar nova versão. Preserve uma cópia dos parâmetros, versão, vigência, data da validação e resumo das alterações usadas em cada auditoria. Mudanças futuras não devem modificar retroativamente auditorias anteriores.

## Limites e proteção de dados

A configuração não substitui análise jurídica nem validação da autoridade competente. Diferenças em relação a parâmetros não provam irregularidade nem determinam contratação ou desligamento. Relatórios devem ser agregados e anonimizados. Não inclua dados de saúde, nomes, CPF ou matrículas neste arquivo.
