# MCR Serralheria — ativar /admin com segurança

O GitHub Pages é estático. Por isso, **não coloque usuário e senha dentro de HTML ou JavaScript**. Nesta versão, o painel usa Supabase Auth + banco PostgreSQL + RLS. O site continua hospedado no GitHub Pages; apenas login, clientes e pedidos ficam no Supabase.

## 1. Criar o projeto Supabase

1. Crie um projeto novo no Supabase.
2. Abra **SQL Editor**.
3. Cole todo o conteúdo de `supabase-schema.sql` e execute.

## 2. Criar o administrador

Depois do SQL, abra **Authentication > Users > Add user**.

- E-mail: `mcrserralheriabr@gmail.com`
- Senha: use a senha inicial que você definiu para o painel.
- Marque/garanta que o usuário esteja confirmado.

O gatilho do banco criará automaticamente o nome de usuário `admin`.

> Troque a senha depois do primeiro acesso pelo próprio menu Configurações do painel.

## 3. Conectar o site

No Supabase, copie a **Project URL** e a **anon/publishable key**. Abra `js/supabase-config.js` e substitua os dois campos `COLE_AQUI...`.

A chave anon/publishable pode estar no navegador. A segurança está nas regras RLS do banco. **Nunca** use a `service_role` no site.

## 4. Ajustar a URL do site no Supabase

Em Authentication/URL Configuration, use como Site URL:

`https://mcrserralheria.site`

## 5. Publicar

Envie os arquivos atualizados ao mesmo repositório GitHub Pages. A pasta `admin` deve ficar na raiz do projeto.

Acesso:

`https://mcrserralheria.site/admin/`

O endereço sem a barra final normalmente redireciona para o mesmo painel.

## Segurança implementada

- Senha nunca fica no GitHub.
- Sessão autenticada pelo Supabase.
- RLS impede visitantes de listar clientes e pedidos.
- A página pública consulta somente um pedido quando recebe o código correto.
- Telefone do cliente não é retornado para a página pública.
- `/admin` contém `noindex,nofollow` para não aparecer em buscadores.
- A chave `service_role` nunca é usada no navegador.
