# Hub Literário v1.0 — Validação do modelo Dom Casmurro

## Escopo validado
- 17 páginas HTML (incluindo 404).
- Percurso pedagógico: Preparação → Leitura → Compreensão → Aprofundamento → Revisão → Teste.
- Guia de leitura com estimativas e roteiros por capítulos.
- Acesso gratuito à obra por fonte oficial, por estar em domínio público.
- Idade recomendada, nível de leitura e estimativa do percurso completo exibidos na página central e no guia.
- Navegação sequencial entre as etapas.
- Exercícios autorais com respostas comentadas.
- Metadados básicos: title, description, robots, Open Graph e theme-color.
- Na versão de staging para GitHub Pages, todas as páginas usam `noindex, nofollow` para evitar indexação antes do endereço definitivo.
- Favicon, robots.txt e .nojekyll preparados para hospedagem estática.
- Links internos: nenhum destino inexistente encontrado na validação automatizada.
- HTML servido localmente com resposta HTTP 200.

## Ajustes editoriais finais
- Distinção entre publicação em 1899 (República) e período imperial reconstruído pela memória de Bentinho.
- Revisão do exercício de contexto histórico para evitar confusão cronológica.
- Remoção de menção prematura a links de afiliados.
- Manutenção da diretriz de que o Hub complementa e não substitui a leitura integral.

## Pendências dependentes do endereço público
- canonical absoluto.
- sitemap.xml com URLs absolutas.
- og:url.
- validação final do endereço publicado e testes de compartilhamento.

## GitHub e publicação segura
- Repositório dedicado: `pmorollo/hub-literario`.
- O app GitHub no ChatGPT é usado para leitura/análise. A documentação oficial da OpenAI direciona geração, edição e push de código para o Codex.
- Para a primeira carga sem Codex disponível nesta sessão, o procedimento seguro é carregar pelo próprio GitHub **o conteúdo desta pasta**, mantendo `index.html` na raiz do repositório.
- Não fazer upload do ZIP como arquivo único: GitHub Pages não o descompacta.
- Só ativar GitHub Pages depois de conferir a árvore de arquivos no repositório.
- Staging deve permanecer `noindex, nofollow` até a decisão do endereço definitivo.
