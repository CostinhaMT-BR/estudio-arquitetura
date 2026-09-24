# Passo a passo — GitHub + Vercel

Sem instalar nada no computador. Tudo pelo navegador.

## Parte 1 — Criar o repositório no GitHub

1. Entre em **github.com** e faça login (ou crie uma conta, se ainda não tiver).
2. Clique no **+** no canto superior direito → **New repository**.
3. Dê um nome, por exemplo `estudio-app`.
4. Deixe como **Private** (só você acessa) — recomendado, já que o código vai conter a URL do seu projeto Supabase e a chave pública dele.
5. **Não** marque nenhuma das caixas de "Add a README" ou similares (vamos subir os arquivos prontos).
6. Clique em **Create repository**.

## Parte 2 — Subir os arquivos

Na página do repositório recém-criado, GitHub mostra algumas opções. Procure o link **"uploading an existing file"** (costuma aparecer na tela inicial do repositório vazio).

1. Clique nele.
2. Arraste os 3 arquivos deste pacote (`index.html`, `README.md`, `DEPLOY_STEPS.md`) para a área de upload — ou clique em "choose your files" e selecione os três.
3. Role até o final da página, escreva uma mensagem curta (ex: "primeira versão") no campo de commit.
4. Clique em **Commit changes**.

Pronto — o código está no GitHub.

## Parte 3 — Conectar ao Vercel

1. Entre em **vercel.com** e faça login **usando sua conta do GitHub** (opção "Continue with GitHub") — isso já conecta as duas contas automaticamente.
2. No painel do Vercel, clique em **Add New...** → **Project**.
3. Vercel vai mostrar uma lista dos seus repositórios do GitHub — encontre `estudio-app` (ou o nome que você deu) e clique em **Import**.
4. Vercel detecta sozinho que é um site estático (não precisa mexer em nenhuma configuração de build/framework — pode deixar tudo como está).
5. Clique em **Deploy**.

Em menos de um minuto, o Vercel te dá um endereço (algo como `estudio-app.vercel.app`) — esse é o novo lugar onde o sistema vive, fora do claude.ai, sem a restrição de CSP que bloqueou o teste anterior.

## Parte 4 — Depois de publicado

Com o link do Vercel em mãos, o mesmo roteiro de teste que já fizemos (ativar `S.dataBackend='supabase'` no console, fazer login, testar CRUD) pode ser repetido — dessa vez contra o site publicado, não contra o artifact do claude.ai.

**Um ponto de atenção para checar quando chegarmos lá:** o Supabase Auth normalmente precisa saber quais domínios têm permissão para autenticar contra o projeto (**Authentication → URL Configuration**, no painel do Supabase). Pode ser necessário adicionar o endereço `.vercel.app` lá — deixamos isso registrado para verificarmos juntos no próximo teste, caso o login dê algum erro relacionado a "domínio não autorizado".

## Atualizações futuras

Sempre que o código do Estúdio mudar (novas funcionalidades, correções), o processo é: subir o `index.html` atualizado no GitHub (mesmo repositório, substituindo o arquivo) → o Vercel publica a nova versão automaticamente, sozinho, em segundos.
