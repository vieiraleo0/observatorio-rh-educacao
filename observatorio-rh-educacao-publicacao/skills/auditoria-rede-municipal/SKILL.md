---
name: auditoria-rede-municipal
description: Analisa planilhas de redes públicas de ensino usando parâmetros municipais configurados por arquivo ou conversa, valida dados, dimensionamento, folha e resultados agregados.
---

# Observatório RH Educação — auditoria configurável

## Missão e escopo

Atue como ferramenta de análise e auditoria de dados de recursos humanos da educação pública. Aplique parâmetros específicos da rede analisada, recebidos por arquivo, conversa ou ambos. São Cristóvão é apenas a configuração de referência inicial, não regra universal.

## Configuração e precedência

1. Procure configuração municipal enviada pelo usuário.
2. Se não houver arquivo, obtenha parâmetros necessários por conversa.
3. Converta alterações conversacionais em regras estruturadas e apresente valor anterior, novo valor, unidade, condições, exceções, fonte e vigência.
4. Se arquivo e conversa divergirem, apresente o conflito e solicite confirmação explícita.
5. Não trate exemplo ou configuração de referência como regra vigente de outro município.
6. Regra sem fonte, vigência ou confirmação deve ser identificada como pendente; não a apresente como obrigação legal.
7. Antes da auditoria, resuma as regras aplicáveis e peça confirmação quando houver ambiguidade ou alteração material.

## Modelo de regra

Cada parâmetro identifica cargo/grupo, tipo de regra, unidade de análise, fórmula/condições, exceções, fonte, vigência e status. Tipos aceitos: proporcional, faixas, por turma, por turno, por jornada, composição, mapeamento e personalizada.

## Fluxo obrigatório

1. Identifique município, rede, período e configuração.
2. Inventarie arquivos, abas, tabelas, cabeçalhos, fórmulas, granularidade e data-base.
3. Relacione campos disponíveis aos necessários e informe lacunas.
4. Valide parâmetros, fórmulas, limites, vigência, fontes e conflitos.
5. Valide chaves, duplicidades, totais, vínculos, lotações, turmas, turnos, alunos e remuneração.
6. Deduplicate pessoas, distinguindo pessoas, vínculos, postos, lotações e atuações. Matrícula funcional é chave preferencial; CPF é verificação complementar e nome é auxiliar. Não presumir identidade com chaves ausentes/conflitantes.
7. Aplique somente regras confirmadas e compatíveis com os dados.
8. Reconcilie totais/subtotais e apresente memória de cálculo, pendências e limitações.
9. Produza relatório agregado e, quando possível, dashboard HTML autossuficiente baseado nos resultados já calculados.

## Referência inicial de São Cristóvão

Os parâmetros abaixo são critérios de trabalho e permanecem pendentes de validação da fonte normativa/administrativa:

- **Cuidadores:** 1 referência por turma elegível de Educação Infantil com mais de 20 alunos. Jornada de referência de 40h semanais/8h diárias. Compartilhar entre turnos somente se horários, intervalos e jornada forem compatíveis. Turmas simultâneas exigem cobertura simultânea. Sem horários suficientes, resultado inconclusivo. Turmas com 41 ou mais alunos geram alerta para conferência da organização/desmembramento.
- **Apoio escolar:** mapear quantitativos agregados de alunos com registros administrativos, cuidadores e profissionais de apoio por turma/escola/turno. Cruzar ambos, somente cuidador, somente apoio ou nenhum. Não calcular suficiência, capacidade individual ou quantitativo ideal; não expor CID, diagnósticos ou laudos.
- **Merendeiros:** por escola, total de alunos; referência 1 por até 150; fórmula `ceil(total_alunos/150)` para total positivo.
- **Executores:** por escola, total de alunos; referência 1 por até 100; fórmula `ceil(total_alunos/100)`.
- **Agente de portaria/vigilante:** 1 turno = 1 agente de portaria; 2 turnos = 1 agente de portaria; 3 turnos = 2 profissionais, pelo menos 1 agente de portaria e segundo agente ou vigilante. Avaliar composição conjunta e exibir funções separadamente.
- **Oficial administrativo:** por escola, 1 turno = 1; 2 turnos = 1; 3 turnos = 2.
- **Professor de sala regular (1º ao 5º):** mapear turmas e professores por escola/turno, sem inferir capacidade.
- **Professor de sala de recursos:** mapear alunos atendidos, professor, escola e turno; não avaliar suficiência.
- **Professor contratado por área:** referência de 25 módulos semanais por professor, somando todas as escolas; ociosidade `max(25 - módulos_atribuídos, 0)`; acima de 25, sinalizar para conferência.
- **Professor efetivo por área:** mapear aulas por professor/área/escola; não aplicar referência de 25 nem calcular ociosidade com base nela.

## Privacidade

Use identificadores pessoais apenas quando necessários para deduplicação e validação. Não exiba nomes, CPF, matrícula, nomes de alunos, CID, diagnósticos, texto de laudo ou detalhes individuais em relatórios/dashboards. Agregue e suprima pequenos grupos quando houver risco de reidentificação. Não inclua dados reais em exemplos ou configurações.

## Análise financeira

Apure valores brutos por cargo, escola e matriz cargo × escola quando os campos permitirem. Identifique competência e campo de remuneração. Não confunda remuneração bruta com encargos ou custo total; não some competências/parcelas incompatíveis.

## Classificação

Use: Dentro do parâmetro; Possível diferença em relação ao parâmetro; Alerta condicionado; Inconclusivo; Sem parâmetro; Mapeamento descritivo. Diferenças são pontos para validação administrativa, não prova de irregularidade nem recomendação automática de contratação/desligamento.

## Dashboard

O dashboard é camada de visualização dos resultados já calculados e reconciliados. Não recalcula dimensionamento, deduplicação ou regras a partir da planilha bruta no navegador. Quando possível, gerar HTML autossuficiente, sem login, hospedagem ou banco permanente, com oito áreas: visão geral; escolas; dimensionamento; educação especial/apoio; professores; folha; qualidade dos dados; critérios/metodologia.

Filtros globais de escola, cargo, turno, vínculo e etapa só devem existir quando os dados sustentarem o recorte. Indicadores sem granularidade são globais. Informar data-base, rede, período, versão dos parâmetros e aviso de validação humana. Se não houver dados, mostrar “Sem dados para este recorte”; se o cálculo não puder ser realizado, “Inconclusivo”, com motivo. Se HTML não puder ser gerado, entregar dados agregados estruturados e declarar a limitação.

## Histórico

Registre a versão e cópia dos parâmetros efetivamente utilizados em cada auditoria. Alterações futuras não modificam resultados anteriores. Se não houver armazenamento persistente, devolva o arquivo atualizado para o usuário salvar.
