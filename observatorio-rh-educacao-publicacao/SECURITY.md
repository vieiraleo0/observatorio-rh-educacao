# Segurança e divulgação responsável

## Não publique

Este repositório é público. Não envie:

- planilhas nominais de servidores, estudantes ou responsáveis;
- CPF, matrícula funcional, nomes, contatos ou identificadores individuais;
- CID, diagnósticos, laudos, informações clínicas ou outros dados pessoais sensíveis;
- relatórios de auditoria que permitam identificar pessoas;
- dashboards com linhas individuais, mesmo que estejam ocultas na interface;
- credenciais, senhas, tokens, chaves privadas, arquivos `.env` ou URLs assinadas;
- dados reais em exemplos, capturas de tela ou histórico de commits.

O `.gitignore` reduz o risco de inclusão acidental, mas **não substitui a revisão manual** antes de cada commit.

## Princípios para relatórios

- Preferir resultados agregados e anonimizados.
- Suprimir ou agrupar células pequenas quando houver risco de reidentificação.
- Não incluir dados pessoais em HTML, JavaScript, metadados ou nomes de arquivos.
- Não embutir a planilha de origem em dashboards.
- Usar dados sintéticos em testes e exemplos.

## Se um segredo ou dado pessoal for publicado

1. Remova o arquivo do repositório e interrompa a divulgação.
2. Considere que o dado pode permanecer no histórico Git, forks, caches e clones.
3. Revogue e substitua imediatamente qualquer credencial exposta.
4. Avalie a necessidade de medidas adicionais com a equipe responsável por privacidade e segurança. Apenas apagar o arquivo no último commit não elimina a exposição anterior.

## Relato de vulnerabilidades

Não publique detalhes exploráveis de vulnerabilidades em uma issue pública. Entre em contato privadamente com o mantenedor pelo canal privado disponível no perfil do GitHub e forneça passos mínimos para reprodução, impacto e evidências sem dados pessoais.
