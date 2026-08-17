# Plano de trabalho — Landing page e nova arquitetura do Hub Literário

## 1. Objetivo

Criar uma landing page institucional na raiz do site para apresentar o Hub Literário, explicar seu método e encaminhar o leitor às obras disponíveis, sem transformar o projeto em enciclopédia e sem iniciar a segunda obra.

Ao final desta etapa:

- `/` será a apresentação institucional e a biblioteca do Hub;
- `/dom-casmurro/` será o painel completo de Dom Casmurro;
- todas as páginas atuais continuarão acessíveis;
- o staging permanecerá em `noindex, nofollow`;
- nenhuma pasta, página ou conteúdo de uma segunda obra será criado.

## 2. Princípios que não podem ser alterados durante a execução

1. O Hub complementa, mas não substitui, a leitura integral.
2. Cada obra funciona como um percurso: **Obter → Preparar → Ler → Compreender → Aprofundar → Revisar → Testar**.
3. A landing apresenta o projeto; não duplica as análises das obras.
4. A quantidade não será usada como promessa. A comunicação será “coleção em desenvolvimento”.
5. Dom Casmurro continuará sendo a única obra publicada nesta fase.
6. Obras em domínio público usam **Baixe gratuitamente**; obras protegidas usarão **Compre o livro**.
7. Nenhuma indexação será liberada antes da definição do endereço definitivo, canonical, sitemap e revisão final.

## 3. Arquitetura aprovada

```text
/
├── index.html                         landing page institucional
├── 404.html
├── sobre.html
├── contato.html
├── politica-privacidade.html
├── termos-de-uso.html
├── favicon.svg
├── robots.txt
└── dom-casmurro/
    ├── index.html                     painel da obra
    ├── guia-de-leitura.html
    ├── resumo.html
    ├── personagens.html
    ├── contexto-historico.html
    ├── capitu-traiu-bentinho.html
    ├── temas-e-simbolos.html
    ├── final-explicado.html
    ├── frases-marcantes.html
    ├── vale-a-pena-ler-hoje.html
    ├── vs-memorias-postumas.html
    ├── questoes-enem-vestibular.html
    └── imagens atuais
```

## 4. Conteúdo da landing page

### 4.1 Abertura

- Marca: Hub Literário.
- Mensagem principal: **Leia grandes obras. Compreenda profundamente. Prepare-se para as provas.**
- Explicação breve da proposta.
- CTA principal: **Explorar Dom Casmurro**.
- CTA secundário: **Entender como funciona**.

### 4.2 Método

Apresentar visualmente as sete etapas:

**Obter → Preparar → Ler → Compreender → Aprofundar → Revisar → Testar**

### 4.3 Diferenciais

- leitura integral em primeiro lugar;
- idade e nível recomendados;
- páginas e tempo estimados;
- roteiros de leitura;
- conteúdos com indicação de spoilers;
- exercícios e gabarito comentado;
- download gratuito ou compra conforme os direitos da obra.

### 4.4 Obra disponível

Card destacado de Dom Casmurro com:

- Machado de Assis;
- a partir de 15 anos;
- nível intermediário–avançado;
- aproximadamente 10 horas para leitura e percurso essencial;
- domínio público;
- botão **Começar Dom Casmurro**;
- botão **Baixar gratuitamente** para a página oficial do MEC.

### 4.5 Coleção

Usar somente a formulação **Coleção em desenvolvimento**. Não exibir doze capas vazias, datas de lançamento nem obras apresentadas como já disponíveis.

### 4.6 Encerramento

- reafirmar que o conteúdo não substitui a obra;
- links para Sobre, Contato, Privacidade e Termos;
- manter canais sociais como “em preparação” enquanto não existirem.

## 5. Migração da página de Dom Casmurro

1. Copiar a atual página raiz de Dom Casmurro para `dom-casmurro/index.html`.
2. Ajustar caminhos relativos de favicon, páginas legais e navegação.
3. Manter o logotipo levando à landing page raiz.
4. Fazer “Voltar a Dom Casmurro” e “Painel de Dom Casmurro” levarem a `dom-casmurro/index.html`.
5. Corrigir breadcrumbs para distinguir **Início** e **Dom Casmurro**.
6. Substituir a antiga raiz somente depois que o novo painel da obra estiver validado localmente.

## 6. Ordem de execução sem improvisação

### Fase A — Inventário e cópia segura

- registrar a árvore atual;
- guardar os hashes dos arquivos publicados;
- criar o novo painel de Dom Casmurro a partir da home atual;
- não alterar ainda a landing publicada.

### Fase B — Ajustes internos da obra

- corrigir todos os links para o novo painel;
- conferir favicon, imagens, rodapé, breadcrumbs e navegação anterior/próxima;
- confirmar que nenhum link da obra retorna à landing quando deveria retornar ao painel.

### Fase C — Construção da landing

- criar a nova home institucional;
- incluir somente funcionalidades reais;
- aplicar o mesmo sistema visual do Hub;
- garantir leitura clara em desktop e celular;
- preservar `noindex, nofollow`.

### Fase D — Validação local

- servir o site por HTTP local;
- testar todas as páginas e recursos;
- validar links internos automaticamente;
- conferir um único H1 por página;
- conferir títulos e descrições únicos;
- testar largura móvel e desktop;
- confirmar ausência de credenciais e arquivos estranhos;
- confirmar que só existe a pasta `dom-casmurro/` para obras.

### Fase E — Publicação controlada

- publicar tudo em um único commit atômico;
- não usar atualização forçada da branch;
- aguardar o GitHub Pages concluir a implantação;
- manter o commit anterior como ponto imediato de reversão.

### Fase F — Validação pública

- testar `/` e `/dom-casmurro/` com HTTP 200;
- testar as 15 páginas regulares e a página 404;
- conferir imagens, favicon e botões externos;
- testar navegação Landing → Dom Casmurro → Guia → Painel → Landing;
- confirmar `noindex, nofollow` em todas as 17 páginas HTML;
- confirmar HTTPS;
- registrar o resultado no status do projeto.

## 7. Critérios de aceite

A etapa só será considerada concluída se:

- a landing explicar a proposta sem depender de Dom Casmurro;
- Dom Casmurro abrir em `/dom-casmurro/` com todo o percurso preservado;
- nenhum link interno estiver quebrado;
- nenhuma página atual desaparecer;
- todos os recursos responderem corretamente no GitHub Pages;
- a navegação for compreensível em celular e desktop;
- o botão gratuito usar fonte institucional;
- não houver promessa de doze obras prontas;
- nenhuma segunda obra tiver sido iniciada;
- o staging continuar fora dos mecanismos de busca.

## 8. Riscos e prevenção

| Risco | Prevenção |
| --- | --- |
| Quebrar links ao mover a home | Mapeamento completo e validação automática antes da publicação |
| Confundir landing com painel da obra | Funções e chamadas para ação distintas |
| Criar uma biblioteca vazia | Mostrar apenas Dom Casmurro como disponível |
| Perder o ponto seguro | Commit atômico e commit anterior preservado |
| Indexar URLs provisórias | Manter `noindex, nofollow` e não criar sitemap ainda |
| Prometer produção excessiva | Usar “coleção em desenvolvimento”, sem cronograma público |
| Link externo gratuito falhar | Usar página institucional verificável e testar no navegador |

## 9. Reversão

Se qualquer critério falhar após a publicação:

1. não liberar indexação;
2. identificar se a falha está na landing, nos caminhos ou no Pages;
3. corrigir em commit pequeno ou retornar a referência da branch ao commit seguro anterior somente se a correção imediata não for confiável;
4. repetir integralmente a validação pública.

## 10. Fora do escopo desta etapa

- iniciar ou escolher definitivamente a segunda obra;
- criar páginas vazias para as demais obras;
- comprar ou configurar domínio;
- liberar indexação;
- adicionar analytics, newsletter, busca, login, comentários ou pagamentos;
- iniciar monetização ou links de afiliados;
- redesenhar a identidade visual completa.

## 11. Ponto de aprovação

Após a aprovação deste plano, a execução começará pela Fase A e seguirá a sequência definida. Qualquer necessidade de mudança estrutural fora do plano deverá ser interrompida e apresentada antes de ser aplicada.

## 12. Atualização de execução — 16 de agosto de 2026

### Concluído

- landing institucional publicada na raiz do GitHub Pages;
- painel de Dom Casmurro preservado em `/dom-casmurro/`;
- páginas institucionais, favicon, 404, robots e sitemap publicados;
- domínio de envio `hub.pmorollo.com` verificado no Resend;
- Worker `hub-literario-api` criado e publicado na Cloudflare;
- chave `RESEND_API_KEY` armazenada como segredo criptografado, sem exposição no repositório;
- formulário de contato conectado à rota pública `/contato`;
- validação de nome, e-mail, assunto e mensagem implementada;
- campo invisível antirrobô, consentimento expresso e aviso para não enviar dados sensíveis implementados;
- Política de Privacidade atualizada para refletir Cloudflare Workers, Resend, finalidade, conservação e direitos do titular;
- destinatário administrativo corrigido para `pagina.virada@yahoo.com`;
- teste público completo realizado e entrega do e-mail confirmada pelo responsável.

### Situação das fases

| Fase | Situação |
| --- | --- |
| A — Inventário e cópia segura | Concluída |
| B — Ajustes internos da obra | Concluída no escopo v1.0 |
| C — Construção da landing | Concluída |
| D — Validação local | Concluída no escopo técnico inicial |
| E — Publicação controlada | Concluída |
| F — Validação pública | Em andamento: contato e entrega de e-mail aprovados; falta auditoria final de interface, acessibilidade e segurança |

### Próximo passo oficial

Executar a **homologação pública final do portal v1.0**, sem iniciar uma segunda obra:

1. testar responsividade a partir de 360 px;
2. testar navegação por teclado, foco visível, contraste e estrutura para leitores de tela;
3. validar novamente todos os links, imagens, favicon, página 404 e percurso Landing → Dom Casmurro → Guia → Painel → Landing;
4. testar mensagens de sucesso e erro do formulário, validações, consentimento, antirrobô e retirada de consentimento;
5. revisar CORS, limites de tamanho, ausência de segredos no código público e minimização de dados;
6. conferir canonical, sitemap, robots e o estado real de indexação antes de qualquer solicitação aos mecanismos de busca;
7. registrar as evidências e declarar ou não Dom Casmurro como padrão definitivo.

### Marco posterior à homologação

Somente após a aprovação integral do portal e de Dom Casmurro:

- iniciar medição de uso e pesquisa de demanda;
- observar até **300 visitantes qualificados ou 150 pesquisas válidas**, além das solicitações e da conversão de avisos opt-in;
- manter marketing de aviso separado, opcional e baseado em consentimento específico;
- revisar a prioridade da segunda obra conforme busca, valor pedagógico e listas atuais de vestibulares;
- não iniciar a segunda obra antes dessa aprovação.
