# NEXO — Site institucional (mockup)

Estrutura do projeto:

```
nexo-site/
├── index.html          → estrutura e conteúdo do site
├── css/
│   └── styles.css      → todo o visual (cores, tipografia, layout)
└── imagens/
    ├── socio-1.jpg      → foto do sócio 1 (adicionar aqui)
    └── socio-2.jpg      → foto do sócio 2 (adicionar aqui)
```

## Como rodar localmente

Não precisa instalar nada além de um navegador. Duas opções:

1. **Rápida**: clique duas vezes em `index.html` — ele abre no navegador padrão.
2. **Recomendada para editar**: abra a pasta no VS Code, instale a extensão
   "Live Server" e clique com o botão direito em `index.html` →
   "Open with Live Server". O navegador atualiza sozinho a cada alteração salva.

## Onde editar cada coisa

| O que mudar                          | Onde procurar                          |
|---------------------------------------|-----------------------------------------|
| Nome da empresa                       | `index.html`, buscar por `NEXO`         |
| E-mail / telefone / endereço          | `index.html`, seção `id="contato"`      |
| Textos e nomes da equipe              | `index.html`, seção `id="equipe"`       |
| Cores do site                         | `css/styles.css`, bloco `:root { ... }` |
| Fontes                                | `css/styles.css`, variáveis `--display`, `--body`, `--mono` |

## Adicionar fotos da equipe

1. Coloque o arquivo de imagem dentro de `imagens/` (ex: `imagens/socio-1.jpg`).
2. No `index.html`, dentro da seção `id="equipe"`, localize a tag:
   ```html
   <img src="" alt="Foto do sócio 1">
   ```
   e troque para:
   ```html
   <img src="imagens/socio-1.jpg" alt="Foto do sócio 1">
   ```
3. Na `<div class="team-photo">` logo acima dessa linha, adicione a classe
   `has-img`, ficando `<div class="team-photo has-img">`. Isso faz a foto
   substituir o quadro de placeholder.

## Publicar no GitHub Pages (deploy automático)

O projeto já inclui `.github/workflows/deploy.yml`, que publica o site
automaticamente no GitHub Pages a cada `git push` na branch `main`.
Basta criar o repositório no GitHub e ativar o Pages uma única vez —
depois disso, todo commit em `main` já dispara o deploy sozinho.

## Antes de publicar

- [ ] Trocar nome, e-mail e telefone reais
- [ ] Adicionar fotos e bios reais da equipe
- [ ] Conectar o formulário de contato a um serviço de envio real
      (hoje ele só mostra um alerta de exemplo — ver `onsubmit` no
      formulário dentro de `index.html`)
- [ ] Revisar todos os textos de exemplo
