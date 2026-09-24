# Estúdio — Sistema de Gestão para Escritórios de Arquitetura

Este repositório contém o Estúdio pronto para ser publicado fora do claude.ai — o que é necessário para que a conexão real com o Supabase (login, banco de dados) funcione, já que o artifact publicado dentro do claude.ai bloqueia esse tipo de conexão por segurança (política de CSP).

## O que tem aqui

Um único arquivo: `index.html`. Todo o sistema — HTML, CSS e JavaScript — está nele, autocontido. Não precisa de build, não precisa instalar nada, não precisa de servidor próprio.

## Estado atual

- `S.dataBackend` está em `'claude'` por padrão — o sistema continua funcionando com o banco de desenvolvimento do Claude até que essa configuração seja trocada deliberadamente.
- A conexão real com o Supabase (URL + chave pública) já está configurada no código, pronta para ser testada assim que este site estiver publicado num domínio próprio.
- Login (Supabase Auth), leitura/escrita reais (Etapa 2A) e o restante da arquitetura já estão implementados — faltando apenas Realtime, Storage, e a troca definitiva do backend padrão.

## Publicação

Ver `DEPLOY_STEPS.md` neste mesmo repositório para o passo a passo de publicar no Vercel.
