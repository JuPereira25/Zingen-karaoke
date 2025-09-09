# Zingen - Landing Page Responsiva

## Sobre o Projeto

O projeto foi desenvolvido como **estudo prático de responsividade**, demonstrando técnicas modernas de design responsivo e CSS Grid/Flexbox.
pode ser acessado no link: https://jupereira25.github.io/Zingen-karaoke/


## Objetivos do Estudo

- **Mobile-First Design**: Desenvolver primeiro para dispositivos móveis
- **CSS Grid Avançado**: Implementar layouts complexos e responsivos
- **Media Queries Modernas**: Utilizar sintaxe `@media (width >= 80em)` 
- **Flexbox**: Organizar elementos de forma flexível
- **Variáveis CSS**: Sistema de design tokens escalável
- **Breakpoints Inteligentes**: Transições suaves entre tamanhos de tela

## Tecnologias Utilizadas

- **HTML5** semântico
- **CSS3** com variáveis customizadas
- **Design System** próprio com tokens
- **Grid Layout** para layouts complexos
- **Flexbox** para alinhamentos
- **Media Queries** modernas

## Estrutura de Arquivos

```
Zingen/
├── index.html              # Estrutura HTML principal
├── styles/
│   ├── global.css          # Estilos globais e variáveis
│   ├── utility.css         # Classes utilitárias e grid
│   ├── cards.css           # Estilos dos cards
│   ├── features.css        # Layout da seção de funcionalidades
│   ├── hero.css            # Estilos da seção hero
│   ├── header.css          # Estilos do cabeçalho
│   ├── about.css           # Estilos da seção sobre
│   ├── pricing.css         # Estilos da seção de preços
│   ├── download.css        # Estilos da seção de download
│   ├── footer.css          # Estilos do rodapé
│   ├── buttons.css         # Estilos dos botões
│   ├── sections.css        # Estilos gerais das seções
│   └── social.css          # Estilos das redes sociais
└── assets/                 # Imagens e ícones
```

## Sistema de Design

### Variáveis CSS (Design Tokens)

```css
:root {
  /* Cores */
  --bg-color: #09090b;
  --surface-color: #18181b;
  --stroke-color: #27272a;
  --text-color-primary: #f4f4f5;
  --brand-color-primary: #f7b733;
  
  /* Tipografia */
  --ff-sans: 'Inter', system-ui, sans-serif;
  --fw-base: 400;
  --fw-bold: 800;
  
  /* Espaçamentos */
  --py-base: 1rem;
  --py-lg: 1.5rem;
  --py-xl: 3rem;
}
```

### Breakpoints Responsivos

- **Mobile**: `< 80em` (1280px) - Layout em coluna única
- **Desktop**: `>= 80em` (1280px) - Layout em múltiplas colunas

##  Técnicas de Responsividade Implementadas

### 1. **Mobile-First Approach**
- Estilos base para dispositivos móveis
- Media queries para adicionar funcionalidades desktop

### 2. **CSS Grid Responsivo**
```css
.even-columns {
  display: grid;
  gap: 1rem;
}

@media (width >= 80em) {
  .even-columns {
    grid-auto-flow: column;
    grid-auto-columns: 1fr;
  }
}
```

### 3. **Classes Utilitárias Responsivas**
- `.desktop-only`: Elementos visíveis apenas em desktop
- `.container`: Largura máxima responsiva
- Sistema de espaçamentos escaláveis

### 4. **Layout Complexo com Grid**
A seção de funcionalidades utiliza um grid complexo que se adapta:
- **Mobile**: Layout em coluna única
- **Desktop**: Grid 4x2 com posicionamento absoluto de imagens

### 5. **Tipografia Escalável**
```css
@media (width >= 80em) {
  :root {
    --fs-lg: 2rem;    /* 1.25rem → 2rem */
    --fs-xl: 3rem;    /* 1.5rem → 3rem */
    --fs-2xl: 4rem;   /* 2.5rem → 4rem */
  }
}
```

## Seções da Landing Page

1. **Header**: Navegação responsiva com menu mobile
2. **Hero**: Título principal e call-to-action
3. **Smartphones**: Imagem de demonstração
4. **About**: Descrição do app com layout adaptativo
5. **Features**: Cards em grid complexo responsivo
6. **Pricing**: Planos com layout em colunas
7. **Download**: Call-to-action final
8. **Footer**: Links e redes sociais

## Conceitos de Responsividade Demonstrados

### **Container Fluido**
```css
.container {
  --max-width: 375px;  /* Mobile */
  width: min(var(--max-width), 100% - var(--px-lg) * 2);
  margin-inline: auto;
}

@media (width >= 80em) {
  .container {
    --max-width: 80rem;  /* Desktop */
  }
}
```

### **Elementos Condicionais**
```css
.desktop-only {
  display: none;  /* Hidden on mobile */
}

@media (width >= 80em) {
  .desktop-only {
    display: initial;  /* Visible on desktop */
  }
}
```

### **Grid Adaptativo**
```css
#features .cards {
  grid-template-columns: 17.5rem 1fr 1fr 17.5rem;
  grid-template-rows: 25rem 25rem;
  gap: 2rem;
}
```

### **Vantagens da Abordagem Mobile-First**
- Código mais limpo e focado
- Performance melhor em dispositivos móveis
- Facilita a criação de layouts responsivos

### **CSS Grid vs Flexbox**
- **Grid**: Para layouts complexos e bidimensionais
- **Flexbox**: Para alinhamentos e distribuições simples

### **Design Tokens**
- Facilita manutenção e consistência
- Permite mudanças globais rápidas
- Melhora a escalabilidade do projeto

### **Media Queries Modernas**
- Sintaxe mais intuitiva: `@media (width >= 80em)`
- Melhor performance que `min-width`
- Código mais legível
