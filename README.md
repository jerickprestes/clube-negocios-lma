# Clube de Negócios LMA

Landing page institucional para o **Clube de Negócios LMA**, desenvolvida como projeto de estudo em HTML, CSS e JavaScript (GSAP), sem uso de frameworks ou processo de build — arquivos estáticos, prontos para rodar em qualquer servidor simples ou diretamente no navegador.

> ⚠️ Projeto desenvolvido para fins de estudo. Conteúdo, depoimentos e alguns dados de contato são fictícios.

---

## 📁 Estrutura do projeto

```
.
├── index.html
├── main.css
└── assets/
    ├── background-section-hero/
    │   ├── backgrounds/     # fotos de fundo do hero (SVG com imagem embutida)
    │   └── obj/              # objetos 3D (não utilizados na versão atual)
    ├── logo-lockup-*.png     # variações do logo
    ├── leandro-pointing.png  # foto do fundador, recortada
    ├── testimonial-*.png     # fotos dos depoimentos
    └── ...                   # demais imagens do site
```

Não há dependências de build — basta abrir `index.html` num navegador ou servir a pasta com qualquer servidor estático (ex.: `python3 -m http.server`, Live Server do VS Code, etc.).

---

## 🧱 Seções da página

Da primeira à última, todas dentro do sistema de painéis (ver abaixo):

1. **Hero** — logo em destaque + foto do fundador, com slider de fundo em fade
2. **Sobre nós** (`#sobre`) — apresentação do clube + cards de diferenciais (Credibilidade, Prosperidade, Facilidade), com slider infinito arrastável
3. **Serviços** (`#servicos`) — chamada para associação + vídeo + cards de oferta (Brasil, Emirados Árabes, China)
4. **Curso** (`#membro`) — apresentação do fundador e do curso, com selo de excelência
5. **Depoimentos** (`#depoimentos`) — 6 depoimentos de membros em layout de colunas
6. **Formulário de contato** (`#contato`) — formulário (nome, e-mail, mensagem) + imagem
7. **Rodapé** — links institucionais, redes sociais, newsletter e mapa-múndi decorativo

---

## ⚙️ Funcionalidades e comportamento

### Navegação por painéis (desktop)
No desktop, as seções acima funcionam como um **carrossel de tela cheia com loop infinito**: cada gesto de rolagem do mouse (ou clique nos indicadores laterais, ou seta do teclado) avança exatamente um painel, com transição em *crossfade*. Ao passar do último painel volta ao primeiro, e vice-versa — o ciclo nunca "acaba".

- Os indicadores laterais (bolinhas) mostram a posição atual e permitem navegação direta.
- O menu (superior e mobile) navega para o painel correto ao clicar em cada item.
- O item do menu correspondente à seção visível é destacado automaticamente.

### Rolagem normal (mobile)
Abaixo de 900px de largura, o sistema de painéis é **desativado por completo** — as seções voltam ao fluxo normal do documento, empilhadas verticalmente, com rolagem comum (sem captura de gestos).

### Efeitos de entrada (fade-in)
Elementos-chave de cada seção entram com fade-in escalonado (um após o outro) toda vez que o painel correspondente é exibido — no desktop, isso se repete a cada troca de painel.

### Slider infinito e arrastável (cards de diferenciais)
Os cards "Credibilidade / Prosperidade / Facilidade" deslizam automaticamente em loop e também podem ser arrastados com o mouse ou o dedo — o movimento retoma de onde o usuário soltar, sem saltos visuais.

### Menu off-canvas (mobile)
Menu lateral deslizante, com overlay e fechamento por clique, toque fora da área, tecla Esc ou clique em qualquer link.

---

## 🛠️ Tecnologias utilizadas

| Tecnologia | Uso |
|---|---|
| **HTML5 / CSS3** | Estrutura e estilo, sem pré-processadores |
| **[GSAP](https://gsap.com)** (core + Draggable + Observer) | Animações, slider arrastável e sistema de navegação por painéis |
| **[Lucide Icons](https://lucide.dev)** | Ícones vetoriais, carregados via CDN e renderizados em runtime |

Todas as bibliotecas são carregadas via CDN ([unpkg.com](https://unpkg.com)) — não há `npm install` nem etapa de build.

---

## 🖼️ Créditos de imagens

- Fotos de bandeiras (Brasil, Emirados Árabes Unidos, China): [Wikimedia Commons](https://commons.wikimedia.org)
- Fotos de pessoas nos depoimentos e na seção de contato: [Pexels](https://www.pexels.com) (uso livre, sem necessidade de atribuição)
- Demais imagens (logo, fotos do fundador, selo, objetos): fornecidas como material de referência do projeto

> ⚠️ Algumas imagens (bandeiras e fotos do Pexels) estão referenciadas via link direto (hotlink) às respectivas CDNs, e não salvas localmente na pasta `assets/`. Para um ambiente de produção, recomenda-se baixar esses arquivos e hospedá-los localmente.

---

## 📱 Responsividade

O layout se adapta em três faixas principais:

- **Desktop** (> 900px): layout completo, navegação por painéis
- **Tablet / mobile** (≤ 900px): menu off-canvas, seções empilhadas, rolagem normal
- **Mobile pequeno** (≤ 560px): ajustes finos de tipografia e espaçamento

---

## ⚠️ Limitações conhecidas

- O formulário de contato e o formulário de newsletter **não enviam dados de verdade** — não há backend/endpoint conectado. Para funcionar, é preciso integrar um serviço (ex.: Formspree, EmailJS, endpoint próprio).
- Links de rodapé como "Política de Privacidade", "Termos de Uso", "Blog", entre outros, são placeholders (`href="#"`) — as páginas ainda não existem.
- Dependência de conexão com a internet para carregar as bibliotecas via CDN e as imagens hotlinked.

---

## ▶️ Como rodar localmente

```bash
# Qualquer servidor estático funciona. Exemplo com Python:
python3 -m http.server 8000

# Depois acesse:
# http://localhost:8000
```

Ou simplesmente abra o arquivo `index.html` diretamente no navegador.
