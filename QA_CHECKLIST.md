QA Checklist — Paraíso Pet Store (sadads.html)

Funcionalidade
- [ ] Abrir `sadads.html` em um navegador (Chrome/Firefox/Edge) e verificar carregamento.
- [ ] Configurar token administrativo via console e criar o admin.
- [ ] Fazer login com o admin criado e acessar o painel.
- [ ] Criar/editar/excluir produtos no painel admin e verificar persistência no `localStorage`.
- [ ] Adicionar itens ao carrinho, alterar quantidades e remover itens.
- [ ] Aplicar cupom válido e verificar desconto no total.
- [ ] Finalizar pedido: botão WhatsApp gera mensagem correta no formato e abre o link.

Acessibilidade e UX
- [ ] Inputs importantes têm `aria-label` ou labels visíveis.
- [ ] Imagens relevantes têm `alt` (verificar imagens dinâmicas no catálogo).
- [ ] Botões usam `type="button"` para evitar submits indesejados.
- [ ] Verificar contraste de cores e foco visível (tab navigation).

Internacionalização / Texto
- [ ] Revisar todos os textos em Português (padronização, acentuação, termos comerciais).
- [ ] Formato de moeda consistente: `R$ 0,00`.

Segurança mínima
- [ ] Credenciais hardcoded removidas; admin criado localmente com hash SHA-256.
- [ ] Validar que senha salva é hash (ver em `localStorage` -> `petstore_admin`).
- [ ] Usar token administrativo por URL/console para criar o admin sem expor criação pública.
- [ ] Não expor dados sensíveis em `localStorage` além do necessário.

Performance / Responsividade
- [ ] Verificar aparência em desktop, tablet e mobile.
- [ ] Testar comportamento do `cart-sidebar` em telas pequenas.

Como commitar localmente (se tiver `git` instalado):

```bash
cd c:/Users/USER/Downloads/sadd
git init
git add sadads.html QA_CHECKLIST.md
git commit -m "Polimento: textos PT-BR, UI, acessibilidade e admin seguro"
```

Notas
- Não foi possível criar o commit automaticamente porque `git` não está disponível no ambiente.
- Backup automático: `sadads.html.bak` (cópia antes de regravar/UTF-8).
- Para criar admin: no console execute `window.setAdminToken('SEU_TOKEN_SECRETO', 1)` e abra a página com `?admin=SEU_TOKEN_SECRETO`.
