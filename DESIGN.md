# Amorim Global — Design System (LP Global Talent)

Paleta e tipografia herdadas do design system geral da Amorim (`../../DESIGN.md` na raiz do projeto Marketing). Este arquivo documenta apenas o que é específico desta LP.

## Colors
Mesma paleta oficial Amorim — ver `../../DESIGN.md` para os valores hex/OKLCH completos (Azul Marinho `#12193d`, Azul Elétrico `#004DFF`, Verde Neon `#2FCC64`/`#00ff5f`).

## Typography
Manrope, mesmos pesos e escalas do design system geral.

## Components (específicos desta LP)
- `.section_lps-hero` — hero navy com formulário
- `#section-form` / `.section_lps-form` — formulário, fundo `#F7F8FF`
- `.section_lps-benefits` — "Por que o Reino Unido?", 3 cards com foto, fundo branco
- `.gt-oque` — "O que é o visto Global Talent?", texto + foto lado a lado, fundo branco
- `.section_lps-pathways` — "Em quantos países..." (abas por área de endosso) + `.gt-video` "Conheça quem vai conduzir" embutido no mesmo container, fundo branco
- `.reviews-bottom-cta` — componente de CTA reaproveitado em 2 lugares (comparação EB2 NIW e citação da CEO) — **candidato a diferenciação, ver Design Decisions**
- `.section_lps-layout2` — "Um hub 360º de internacionalização", fundo navy `#12193D`
- `.gt-riscos` — "O que costuma dar errado, e como a Amorim controla", tabela problema/ação, fundo branco
- `.section_lps-living` (+ `.vidauk-section`) — "O que acontece depois do endosso", carrossel de cenas, fundo navy `#12193D` — **tem 3 blocos de CSS conflitantes no arquivo (iterações navy → cream → navy), ver Design Decisions**
- `.gt-custo` — "Quanto custa, com clareza desde o início", 2 cards de camada de investimento, fundo `#F6F8FC`
- `.section_lps-reviews` — "Histórias de quem já fez o caminho", depoimentos + badge Google Reviews, fundo `#F7F8FF`
- `.section_lps-faq` — perguntas frequentes, fundo branco
- `.gt-artigos` — "Aprofunde a sua rota até o Reino Unido", fundo padrão

## Design Decisions

### Pendências identificadas (revisão 2026-07-09)
- **Sequência de 4 blocos brancos sem diferenciação**: `section_lps-benefits` → `gt-oque` → `section_lps-pathways`/`gt-video`, todos em `#fff`/`#FFFFFF` sem variação de fundo, textura ou cor de apoio. Precisa de alternância (ex.: um dos blocos em `oklch(95-97% ... 250)` do design system geral) ou de um elemento visual que separe os blocos (borda superior, ícone, textura).
- **CTA duplicado**: `.reviews-bottom-cta` é usado idêntico para "Global Talent ou EB2 NIW" e "Palavra da CEO". Precisam de composição própria cada um (o comparativo pode ganhar ícones das duas rotas lado a lado; a citação da CEO pode ganhar aspas grandes/foto, tratamento mais editorial).
- **CSS morto em `.section_lps-living`**: existem 3 blocos de regras para o mesmo seletor (navy original → direção cream editorial nunca usada → navy médio atual, que é o que renderiza hoje). O bloco cream é código morto e deve ser removido para evitar bugs futuros na cascata.
- **Copy vazada do Migra Brasil**: a versão em inglês do bloco de depoimentos (`section_lps-reviews`) ainda tem "Stories from people who made Brazil their home" — copy residual, não é sobre o Reino Unido.

### Decisões mantidas (funcionam bem, não mexer)
- Alternância navy/branco nos blocos "hub 360º" (`section_lps-layout2`) e "depois do endosso" (`section_lps-living`) — são os únicos pontos de contraste real na página hoje.
- Estratégia de cor "Committed" do design system geral (navy carrega a maior parte da superfície, azul elétrico como accent de ação, verde neon reservado para destaques pontuais).
