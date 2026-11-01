# Especificação funcional do dashboard

**Natureza:** especificação da saída analítica. Não define aplicação permanente, login, hospedagem ou banco de dados.

## Objetivo

Transformar resultados agregados e já calculados pelo Observatório em uma interface HTML interativa, legível e investigativa. O painel apoia a leitura gerencial; não substitui análise técnica, memória de cálculo ou validação humana.

## Oito áreas

1. **Visão geral:** escolas, turmas, alunos/matrículas, servidores únicos e folha bruta agregada; distribuição por escola, cargo, etapa e turno.
2. **Escolas:** indicadores da unidade, alunos, turmas, etapas, turnos e servidores únicos por cargo/turno.
3. **Dimensionamento:** quantitativo atual, referência, diferença absoluta e percentual quando válido; composição de portaria/vigilância; cuidadores com simultaneidade, jornada e pendências.
4. **Educação especial e apoio:** quantitativos agregados de estudantes com registros administrativos; cruzamento de presença de cuidador e apoio; profissionais por escola/turno. Sem CID, diagnóstico, laudo ou identificadores.
5. **Professores:** sala regular, sala de recursos, contratados por área com módulos e referência; efetivos em bloco separado, sem parâmetro de contratados.
6. **Folha:** folha bruta mensal por cargo, servidores únicos e média simples quando possível. Detalhe por escola somente com lotação financeira confiável; nunca ratear sem regra explícita.
7. **Qualidade dos dados:** duplicidades, chaves ausentes/conflitantes, atuações sem servidor, turmas sem professor, campos ausentes, divergências e cálculos inconclusivos.
8. **Critérios e metodologia:** parâmetros, fórmulas, unidade de análise, fonte, vigência, status, memória de cálculo e limitações.

## Filtros

Filtros possíveis: escola, cargo, turno, vínculo e etapa. Exiba somente os que os dados sustentarem. Indicadores sem granularidade para o recorte devem ser identificados como globais, nunca rateados artificialmente. A seleção deve permanecer ao navegar e atualizar apenas visualizações compatíveis.

## Visualização

- Cartões KPI para poucos indicadores centrais.
- Barras ordenadas para comparar escolas e cargos.
- Barras agrupadas para atual versus referência.
- Linhas apenas para séries temporais reais.
- Tabelas para detalhamento auditável.
- Valores absolutos sempre visíveis; percentuais acompanhados do denominador.
- Gráficos com título, unidade, legenda, fonte e nota de interpretação.
- Pendências em destaque com linguagem neutra.

## Integridade e privacidade

- Totais de servidores contam pessoas únicas; atuações são apresentadas separadamente.
- Não somar atuações sobrepostas como pessoas distintas.
- Não incluir dados pessoais/sensíveis no HTML, scripts, metadados ou conteúdo oculto.
- Não embutir planilha de origem nem linhas nominais.
- Suprimir/agrupar pequenos grupos quando houver risco de reidentificação.
- Informar data-base, rede, período, versão dos parâmetros e aviso de validação humana.

## Comportamento

- Estado vazio: “Sem dados para este recorte”.
- Cálculo inviável: “Inconclusivo”, com motivo.
- O painel visualiza resultados prontos; não recalcula fórmulas no navegador.
- Se HTML não puder ser gerado, entregar resultados agregados em tabela/CSV/JSON e declarar a limitação.

## Critérios de aceite

1. Apresentar as oito áreas.
2. Reconciliar totais com resultados analíticos.
3. Separar servidores únicos de atuações.
4. Não exibir dados pessoais ou sensíveis.
5. Aplicar filtros apenas onde há granularidade.
6. Identificar parâmetros e limitações.
7. Não apresentar diferenças como conclusões administrativas.
