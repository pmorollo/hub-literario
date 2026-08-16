# Checklist de implantação — Hub Literário v1.0 (staging)

## Antes do upload
- Repositório: `pmorollo/hub-literario` (público).
- Carregar os arquivos **desta pasta** na raiz do repositório.
- Confirmar que `index.html`, `404.html`, `favicon.svg`, `.nojekyll` e a pasta `dom-casmurro/` aparecem diretamente na raiz.
- Não carregar o ZIP como arquivo único.

## Primeira carga
1. GitHub → repositório `hub-literario` → **Add file → Upload files**.
2. Arrastar todos os arquivos e pastas desta pasta.
3. Conferir a lista antes do commit.
4. Commit inicial: `Publica staging Hub Literário v1.0`.
5. Como o repositório foi criado vazio para esta carga inicial, o commit pode ir diretamente para `main`.

## Conferência antes do Pages
- `index.html` está na raiz.
- `dom-casmurro/guia-de-leitura.html` e demais páginas estão presentes.
- As três imagens JPG estão em `dom-casmurro/`.
- Não há arquivos com credenciais, tokens ou chaves.

## Ativar GitHub Pages
1. Settings → Pages.
2. Source: **Deploy from a branch**.
3. Branch: `main`.
4. Folder: `/(root)`.
5. Save.

## Validação online
- Abrir a home e todas as etapas de Dom Casmurro.
- Testar desktop e celular.
- Conferir imagens, favicon, navegação anterior/próxima e página 404.
- Confirmar que o staging contém `noindex, nofollow`.

## Antes de produção/indexação
- Definir URL/domínio definitivo.
- Adicionar canonical absoluto, `og:url` e `sitemap.xml`.
- Ajustar `robots.txt` no domínio final.
- Trocar `noindex, nofollow` por `index, follow`.
- Fazer nova validação antes de solicitar indexação em mecanismos de busca.

## Reversão
Se a primeira carga estiver errada, não ativar Pages. Corrigir/remover os arquivos no repositório antes de publicar. Depois que houver histórico de commits, alterações futuras devem ser feitas em branch/PR ou em commits pequenos para permitir reversão segura.
