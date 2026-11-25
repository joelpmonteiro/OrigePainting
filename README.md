# Orige Painting - Luxury Website

Site institucional premium desenvolvido com Astro e Tailwind CSS v4, seguindo design luxury com paleta preta e dourada.

## 🎨 Características do Design

- **Paleta de Cores**: Preto (#0A0A0A) e Dourado (#D4AF37)
- **Tipografia**: Serif (Georgia) para títulos, Sans-serif para textos
- **Estilo**: Premium, elegante, sofisticado
- **Animações**: Fade-in, slide-in para elementos principais

## 🚀 Tecnologias

- **Astro 5.16+** - Framework moderno SSG
- **Tailwind CSS v4** - Utility-first CSS (via Vite plugin)
- **TypeScript** - Tipagem estática (modo strict)
- **Formspree** - Serviço de formulários
- **SVG Icons** - Ícones personalizados em linha

## 📦 Instalação e Execução

```bash
# Instalar dependências
pnpm install

# Desenvolvimento (localhost:4321)
pnpm dev

# Build para produção
pnpm build

# Preview do build
pnpm preview
```

## 📁 Estrutura do Projeto

```
/
├── public/
│   └── logo.jpeg              # Logo da empresa
├── src/
│   ├── components/            # (Não usado neste projeto - tudo em páginas)
│   ├── layouts/
│   │   └── Layout.astro       # Layout principal com header/footer
│   ├── pages/                 # Rotas do site
│   │   ├── index.astro        # Home (Hero, Expertise, Process)
│   │   ├── services.astro     # Serviços detalhados
│   │   ├── process.astro      # Processo de trabalho
│   │   ├── portfolio.astro    # Portfólio e depoimentos
│   │   └── contact.astro      # Formulário de contato
│   └── styles/
│       └── global.css         # Estilos globais + variáveis CSS
└── astro.config.mjs           # Config Astro + Tailwind Vite
```

## 🎯 Páginas Implementadas

### Home (`/`)

- Hero fullscreen com imagem de fundo
- Seção "Our Expertise" (4 cards: Interior, Exterior, Cabinets, Power Washing)
- Seção "Our Process" (4 etapas com ícones circulares)
- CTA final

### Services (`/services`)

- Hero section
- 4 serviços detalhados com descrição e benefícios
- Layout alternado (imagem esquerda/direita)
- Links para orçamento

### Our Process (`/process`)

- Hero section
- 4 etapas detalhadas com descrição completa
- Separadores decorativos entre etapas
- CTA final

### Portfolio (`/portfolio`)

- Hero section
- Filtros de categoria
- Grid de projetos (placeholders)
- Seção de depoimentos (3 clientes)
- CTA final

### Contact (`/contact`)

- Hero section
- Formulário completo (Nome, Phone, Email, Service, Message)
- Informações de contato (Phone, Email, Horário)
- Mapa placeholder
- Lista "Why Choose Us"

## 🛠️ Configuração Necessária

### 1. Logo

O logo já está configurado em `/public/logo.jpeg`. Para substituir:

- Coloque seu logo em `/public/logo.jpeg`
- Ou atualize os caminhos em `src/layouts/Layout.astro` (linhas 29 e 128)

### 2. Formspree (Formulário de Contato)

1. Acesse [formspree.io](https://formspree.io) e crie uma conta
2. Crie um novo form
3. Copie o Form ID
4. Edite `src/pages/contact.astro` linha 24:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST"></form>
   ```

### 3. Informações de Contato

Atualize em `src/layouts/Layout.astro` (footer) e `src/pages/contact.astro`:

- **Telefone**: (508) 901-7609 → Seu telefone
- **Email**: info@origepainting.com → Seu email
- **Horários**: Atualize conforme necessário

### 4. Imagens

#### Hero Background

Atualmente usa Unsplash. Para usar sua própria imagem:

- Adicione em `/public/hero-bg.jpg`
- Edite `src/pages/index.astro` linha 12:
  ```html
  <div
  	class="absolute inset-0 bg-[url('/hero-bg.jpg')] bg-cover bg-center"
  ></div>
  ```

#### Imagens de Serviços/Portfolio

Os placeholders cinza (`bg-gray-800`) devem ser substituídos:

- Adicione imagens em `/public/images/`
- Substitua as divs com `<img>` tags

Exemplo em `services.astro`:

```astro
<!-- De: -->
<div class="bg-gray-800 h-96 rounded-lg"></div>

<!-- Para: -->
<img src="/images/interior-painting.jpg" alt="Interior Painting" class="w-full h-96 object-cover rounded-lg" />
```

## 🎨 Customização de Cores

As cores estão definidas em `src/styles/global.css`:

```css
:root {
	--color-gold: #d4af37; /* Dourado principal */
	--color-gold-light: #e8c547; /* Dourado claro (hover) */
	--color-gold-dark: #b8941f; /* Dourado escuro */
	--color-dark: #0a0a0a; /* Preto principal */
	--color-dark-secondary: #1a1a1a; /* Preto secundário */
}
```

Para mudar a paleta, edite esses valores.

## 📱 Classes CSS Personalizadas

### Botões

- `.btn-gold` - Botão dourado preenchido
- `.btn-outline-gold` - Botão com borda dourada

### Cards

- `.card-luxury` - Card com borda e hover effect

### Outros

- `.icon-circle` - Ícone circular com borda dourada
- `.divider-gold` - Linha divisória dourada
- `.text-gold`, `.bg-gold`, `.border-gold` - Utilit\u00e1rias de cor

### Animações

- `.animate-fade-in` - Fade in suave
- `.animate-fade-in-delay` - Fade in com atraso
- `.animate-slide-in-left` - Slide da esquerda
- `.animate-slide-in-right` - Slide da direita

## 🚀 Deploy

### Cloudflare Pages

```bash
Build command: pnpm build
Build output: dist
Node version: 18+
```

### Vercel

```bash
pnpm dlx vercel
```

Ou conecte o repositório GitHub diretamente - configuração automática.

## 🔍 SEO

Meta tags incluídas em cada página:

- Title personalizado
- Description personalizada
- Generator meta (Astro)
- Responsive viewport

Para melhorar:

1. Adicione Open Graph tags
2. Adicione Schema.org markup
3. Crie `robots.txt` e `sitemap.xml`

## ⚡ Performance

- CSS minificado automaticamente
- HTML minificado automaticamente
- Imagens devem ser otimizadas (use `.webp` ou `.avif`)
- Zero JavaScript no cliente (exceto menu mobile)

## 📄 Licença

Projeto livre para uso e modificação.

---

## 🎯 Próximos Passos

1. ✅ Configurar Formspree
2. ✅ Atualizar informações de contato
3. ✅ Adicionar imagens reais
4. ✅ Adicionar projetos reais no portfolio
5. ✅ Configurar analytics (Google Analytics, etc.)
6. ✅ Deploy para produção
7. ✅ Testar em dispositivos móveis

## 💡 Dicas

- Use imagens de alta qualidade para manter o estilo premium
- Mantenha a paleta de cores consistente
- Teste a responsividade em vários dispositivos
- Otimize imagens antes do upload (use TinyPNG ou similar)
