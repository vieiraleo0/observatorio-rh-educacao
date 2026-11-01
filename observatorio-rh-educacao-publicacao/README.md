# Observatório RH Educação

Documentação e configurações de referência para auditoria de dados de recursos humanos da educação pública municipal.

> **Escopo deste repositório:** documentação, metodologia e modelos de configuração. O plugin do ChatGPT permanece privado e este repositório, nesta versão, **não contém um motor autônomo** para processar planilhas nem um serviço web hospedado.

## Objetivos

- Apoiar a análise de quadro de pessoal, matrículas, turmas, turnos e folha.
- Aplicar parâmetros específicos de cada rede municipal.
- Identificar inconsistências e oportunidades de revisão administrativa.
- Separar pessoas únicas de vínculos, lotações e atuações.
- Produzir resultados agregados, rastreáveis e sujeitos à validação humana.

## Estrutura

```text
.
├── configuracao/
│   ├── especificacao-dashboard.md
│   ├── manual-configuracao.md
│   ├── modelo-configuracao-municipal.json
│   └── sao-cristovao.json
├── skills/
│   └── auditoria-rede-municipal/
│       └── SKILL.md
├── .gitignore
├── README.md
└── SECURITY.md
```

## Comece por aqui

1. Leia o [manual de configuração municipal](configuracao/manual-configuracao.md).
2. Copie `configuracao/modelo-configuracao-municipal.json` para criar uma configuração.
3. Preencha as regras, fontes, vigência e status de validação.
4. Não aplique regras ambíguas ou pendentes sem confirmação explícita da autoridade responsável.
5. Consulte a [especificação do dashboard](configuracao/especificacao-dashboard.md) para os requisitos dos relatórios gerenciais.

## Configuração de São Cristóvão

O arquivo `configuracao/sao-cristovao.json` registra parâmetros de trabalho definidos durante a construção do Observatório. É um **rascunho de referência**, não uma consolidação normativa. As regras estão marcadas como pendentes de validação e devem ser conferidas com as fontes legais e administrativas municipais antes de qualquer uso oficial.

## Princípios metodológicos

- Matrícula funcional é a chave preferencial para deduplicar servidores; CPF pode ser usado apenas como verificação complementar e nome como campo auxiliar.
- Não presumir identidade quando as chaves estiverem ausentes ou conflitantes.
- Diferenciar pessoas, vínculos, lotações e atuações.
- Uma pessoa que atua em várias escolas ou turmas continua sendo uma pessoa nos totais de servidores.
- Diferenças em relação aos parâmetros são alertas para conferência, não prova de irregularidade nem recomendação automática de contratação ou desligamento.
- Dados de saúde de estudantes e outros dados sensíveis devem permanecer fora dos relatórios individualizados e dos dashboards.

## Limites

O dashboard descrito aqui é uma saída HTML gerada após a análise, quando o ambiente permitir. Ele apenas apresenta resultados já calculados e reconciliados; não é uma aplicação web permanente, não oferece login, hospedagem ou banco de dados e não deve recalcular as regras no navegador.

## Privacidade e contribuição

Antes de enviar qualquer arquivo ao GitHub, revise seu conteúdo e o histórico Git. Não publique planilhas de origem, dados nominais, relatórios individualizados, tokens, credenciais ou arquivos de auditorias reais. Consulte [SECURITY.md](SECURITY.md).

## Licença

Nenhuma licença aberta foi atribuída neste repositório. Na ausência de uma licença explícita, aplicam-se os direitos autorais padrão; a publicação do código/documentação não concede automaticamente autorização para reutilização, modificação ou redistribuição.
