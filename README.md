# MCR Serralheria

Site estático pronto para GitHub Pages.

## Páginas principais
- `index.html` — início
- `servicos.html` — catálogo de serviços
- `servico.html` — detalhe de cada serviço
- `categoria.html` — serviços filtrados por categoria
- `clientes.html` — acompanhamento do serviço por código
- `contato.html` — canais de contato e formulário para WhatsApp

## Contato configurado
- Instagram: @mcr.serralharia
- E-mail: mcrserralheriabr@gmail.com
- WhatsApp: (67) 99840-1792
- Região: Brasil • Mato Grosso do Sul • Três Lagoas

As imagens dos serviços ficam em `img/servicos/`.

## Painel administrativo seguro

A versão atual possui painel em `/admin/` e acompanhamento de pedidos na página `clientes.html`.
Como o site está hospedado no GitHub Pages, autenticação e banco de dados usam Supabase.
Leia `GUIA-ADMIN-SEGURO.md`, execute `supabase-schema.sql` e preencha `js/supabase-config.js` antes de publicar.

Nunca coloque senha, `service_role` ou outros segredos no repositório GitHub.
