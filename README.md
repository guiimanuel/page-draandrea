# Dra. Andrea Dória — Landing Page

Landing page institucional desenvolvida para a **Dra. Andrea Dória**, médica hepatologista (CRM/PE 10930 · RQE 693) atendendo em Recife/PE. O site apresenta a especialista, as condições tratadas, o fluxo de atendimento, conteúdo educativo do Instagram e a localização dos consultórios, com chamadas diretas para agendamento de consulta.

🔗 **Site no ar:** [page-draandrea.vercel.app](https://page-draandrea.vercel.app)

---

## Sobre o projeto

O projeto é uma landing page **one-page**, focada em conversão (agendamento de consulta) e em transmitir confiança clínica através de uma apresentação clara da atuação médica. O conteúdo é centralizado em um único arquivo de página (`index.astro`), o que facilita a edição de textos, cards e dados sem precisar mexer em lógica de aplicação.

Principais seções da página:

| Seção | Âncora | Descrição |
| --- | --- | --- |
| Hero | `#inicio` | Apresentação da médica, credenciais (CRM/RQE) e CTAs para agendar consulta e ver Instagram |
| Faixa de credenciais | — | Destaques rápidos: CRM/PE, RQE, especialidade e área de atendimento |
| Atuação | `#atuacao` | Texto institucional sobre hepatologia e os pilares de atendimento (investigação, prevenção, seguimento) |
| Condições | `#condicoes` | Grade com as principais situações clínicas atendidas (exames alterados, gordura no fígado, hepatites, cirrose) |
| Jornada de cuidado | — | Passo a passo de como funciona a consulta (escuta, leitura de exames, plano de cuidado) |
| Conteúdo educativo | `#conteudo` | Embeds de posts/reels do Instagram com conteúdo sobre saúde do fígado |
| Localização | `#localizacao` | Endereços dos consultórios com mapas incorporados (Google Maps) e link para abrir no app |
| Rodapé | — | Logo, links rápidos e aviso de direitos autorais |

A página também inclui dados estruturados (`schema.org/Physician`) no `<head>`, ajudando mecanismos de busca a identificar a médica, especialidade e endereços de atendimento.

## Tecnologias utilizadas

- **[Astro 5](https://astro.build/)** — framework para geração de site estático (`output: 'static'`)
- **HTML semântico** gerado a partir de componentes `.astro`
- **CSS puro** (sem framework), com variáveis CSS (design tokens) para cores, sombras e espaçamentos
- **Google Fonts**: `DM Sans` (texto) e `Libre Baskerville` (títulos)
- **Embed do Instagram** (`embed.js`) para exibir posts diretamente na página
- **Google Maps** embutido via `iframe` para cada unidade de atendimento
- **Vercel** para hospedagem e deploy contínuo

## Estrutura de pastas

```
page-draandrea/
├── public/
│   └── assets/
│       └── images/
│           ├── brand/      # Logos e símbolos da marca (verde e branco)
│           └── landing/    # Fotos da médica e imagens da página
├── src/
│   ├── pages/
│   │   └── index.astro     # Página principal — conteúdo, dados e marcação
│   └── styles/
│       └── global.css      # Estilos globais, design tokens e responsividade
├── astro.config.mjs        # Configuração do Astro (saída estática)
├── package.json
└── README.md
```

## Conteúdo editável

Praticamente todo o conteúdo dinâmico da página fica centralizado em constantes no início do `src/pages/index.astro`, o que torna a manutenção simples sem precisar alterar a marcação HTML:

- `appointmentUrl` — link de agendamento (Canva Site)
- `instagramUrl` — perfil do Instagram
- `locations` — lista de consultórios (nome, endereço, link e embed do mapa)
- `credentials` — CRM, RQE, especialidade e cidade de atendimento
- `focusItems` — pilares do atendimento (investigação, prevenção, seguimento)
- `conditions` — condições/situações clínicas atendidas
- `journeySteps` — etapas da jornada de cuidado/consulta
- `instagramPosts` — posts/reels exibidos na seção de conteúdo educativo
- `schema` — dados estruturados (JSON-LD) para SEO

## Como rodar localmente

Pré-requisitos: [Node.js](https://nodejs.org/) instalado.

```bash
# Clonar o repositório
git clone https://github.com/guiimanuel/page-draandrea.git
cd page-draandrea

# Instalar dependências
npm install

# Ambiente de desenvolvimento (com hot reload)
npm run dev

# Build de produção (gera a pasta dist/)
npm run build

# Pré-visualizar o build de produção
npm run preview
```

Por padrão, o `npm run dev` sobe o servidor local em `http://localhost:4321`.

## Deploy

O projeto é configurado com `output: 'static'` no `astro.config.mjs`, gerando um site totalmente estático na pasta `dist/`, pronto para qualquer hospedagem estática (Vercel, Netlify, GitHub Pages, etc.). O deploy atual está publicado na **Vercel**.

## Design

A identidade visual segue uma paleta em tons de verde e dourado sobre fundo creme, transmitindo sobriedade e confiança clínica:

- Cores principais: verde escuro (`--green-950`, `--green-800`, `--green-650`), dourado (`--gold`) e fundo creme (`--cream`)
- Tipografia: `Libre Baskerville` (serifada) para títulos e `DM Sans` para textos
- Layout totalmente **responsivo**, com breakpoints para tablets (`1020px`), celulares (`760px`) e telas pequenas (`420px`)

## Autor

Desenvolvido por [**Guilherme Manuel**](https://github.com/guiimanuel).

## Licença

Projeto privado, desenvolvido sob demanda para a Dra. Andrea Dória. Todos os direitos reservados.
