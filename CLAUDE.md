# Content Akademy — LP "O Método"

## Produto
**Nome:** O Método — Content Akademy  
**Tipo:** Infoproduto (guia prático / curso)  
**Público:** Social medias, criadores de conteúdo e profissionais de comunicação  
**Dor central:** Criam conteúdo genérico, não sabem usar IA de forma estratégica, trabalham no achismo  
**Promessa:** Método validado em clientes reais que transforma IA em diretor criativo  
**Preço:** R$297 (pagamento único)  
**Garantia:** 7 dias incondicional  

---

## Arquivo
```
lp-akademy/
├── index.html        ← página completa (HTML + CSS + JS embutidos, sem framework)
└── provas/           ← screenshots de depoimentos do Instagram (6 PNGs)
    ├── IMG_6248.PNG  → @ferguxta
    ├── IMG_6250.PNG  → @raphaellareiis
    ├── IMG_6254.PNG  → @jenniferklayn
    ├── IMG_6260.PNG  → @patiliberato
    ├── IMG_6262.PNG  → @_jusouza
    └── IMG_6263.PNG  → @jvarchanjo
```

---

## Design

### Paleta de cores
| Variável | Valor | Uso |
|---|---|---|
| `--accent` | `#F59E0B` | Âmbar — cor principal de destaque |
| `--accent-light` | `#FCD34D` | Hover do botão |
| `--accent-hover` | `#D97706` | Acento escuro |
| `--accent-dim` | `rgba(245,158,11,0.08)` | Fundos de badge e check |
| `--accent-glow` | `rgba(245,158,11,0.22)` | Sombra do botão no hover |
| `--bg-primary` | `#0c0a07` | Fundo principal (quente escuro) |
| `--bg-secondary` | `#110f0b` | Fundo seções alternadas |
| `--bg-card` | `#181410` | Fundo de cards |
| `--bg-offer` | `#080601` | Fundo seção de oferta (mais escuro) |
| `--text-primary` | `#F5F0E8` | Texto principal (creme) |
| `--text-secondary` | `#8a7e6e` | Texto de apoio |
| `--text-muted` | `#524840` | Texto micro / labels |
| `--border` | `rgba(245,158,11,0.10)` | Borda padrão |
| `--border-strong` | `rgba(245,158,11,0.25)` | Borda de destaque |
| `--border-subtle` | `rgba(255,255,255,0.06)` | Borda de cards |

### Tipografia
- **Fonte:** Inter (Google Fonts) — weights 400, 500, 600, 700, 800, 900
- **Headlines:** weight 900, letter-spacing -0.03em a -0.05em
- **Section label:** 11px, weight 700, uppercase, letter-spacing 0.16em, cor `--text-muted`
- **Corpo:** 16–18px, weight 400–500, line-height 1.65–1.75

### Raios de borda
- `--radius`: 14px (cards menores, FAQ)
- `--radius-lg`: 22px (cards maiores, módulos, oferta)

---

## Estrutura das seções

| # | Classe | Conteúdo | Fundo |
|---|---|---|---|
| 1 | `.hero` | Headline, subheadline, CTA (sem logo) | `--bg-primary` + grid âmbar + glow |
| 2 | `.section-pain` | "Isso soa familiar?" — 3 cards de dor | `--bg-secondary` |
| 3 | `.section-turn` | Frase de virada grande | `--bg-primary` + linha vertical âmbar |
| 4 | `.section-solution` | Badge + título do produto + foto placeholder | `--bg-secondary` |
| 5 | `.section-forwhom` | 4 itens com check âmbar | `--bg-primary` |
| 6 | `.section-modules` | 4 cards de módulo (04 = bônus roxo) | `--bg-secondary` |
| 7 | `.section-proof` | 6 screenshots reais de depoimentos do Instagram (pasta `provas/`) | `--bg-primary` |
| 8 | `.section-offer` | Lista incluso + preço R$297 + CTA | `--bg-offer` |
| 9 | `.section-faq` | Accordion com 5 perguntas | `--bg-secondary` |
| 10 | `.section-warranty` | Escudo + garantia 7 dias | `--bg-primary` |
| 11 | `.section-final-cta` | Headline + botão final | `--bg-secondary` + grid |
| — | `.footer` | Copyright + links (sem logo) | `--bg-primary` |

**Âncora da oferta:** `id="oferta"` na seção 8 — todos os botões CTA apontam para `#oferta`

---

## Módulos do produto

| # | Título | Descrição |
|---|---|---|
| 01 | Desmistificando criação de conteúdo | Como conteúdo que funciona é construído |
| 02 | O Método | Processo criativo usado em clientes reais |
| 03 | IA como Diretor Criativo | Aplicar o método para usar IA com intenção |
| 04 ★ | Propostas que Convertem (Bônus) | Template de proposta comercial — valor R$97 |

---

## Placeholders para substituir

| Placeholder | Localização | Observação |
|---|---|---|
| `[FOTO DO DIRETOR CRIATIVO]` | Seção 4 — Solução | Proporção 3:4, max-width 360px |
| `href="#"` no botão de compra | Seção 8 — Oferta | Trocar pelo link de checkout real |

---

## Comportamentos JavaScript

- **Fade-in:** `IntersectionObserver` com threshold 0.12 — adiciona `.visible` ao entrar na viewport. Delays via `.delay-1` a `.delay-4` (0.1s–0.4s).
- **Accordion FAQ:** abre o item clicado e fecha os demais via `max-height` animado. Classe `.open` controla cor da pergunta e rotação do chevron.

---

## Decisões de design (não alterar sem motivo)

- **Cor âmbar** é a cor do projeto — não usar verde
- Fundo quente escuro (`#0c0a07`) harmoniza com âmbar — não trocar por azul-navy
- `section-label` uppercase muted acima de cada título cria hierarquia visual — manter em todas as seções
- Cards de dor usam número (`01`, `02`, `03`) em vez de ícone — decisão estética deliberada
- Hover nos itens "para quem" faz `translateX(6px)` — não remover, dá sensação de interatividade
- Card bônus (módulo 04) usa paleta roxa independente para se destacar dos demais
- Linha vertical âmbar na seção de virada é CSS puro via `::after` — não adicionar imagem
