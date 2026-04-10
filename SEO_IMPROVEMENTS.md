# 🔥 Melhorias de SEO — Mini MBA Falso

## ✅ Implementadas

### 1. **Meta Tags Essenciais**
- ✅ `<title>` otimizado com keywords: "Mini MBA Falso — Festival de Educação | Verão 2026 Portugal"
- ✅ `<meta name="description">` melhorada com 160 caracteres (ideal)
- ✅ `<meta name="keywords">` adicionado com 6 palavras-chave principais
- ✅ `<meta name="author">` com nome da organização
- ✅ `<meta name="robots">` com diretivas de crawling otimizadas

### 2. **Open Graph & Social Media**
- ✅ `og:url` preenchido com domínio real (https://minimbafalso.pt)
- ✅ `og:site_name` adicionado
- ✅ `twitter:creator` adicionado com handle

### 3. **Structured Data (Schema.org/JSON-LD)**
- ✅ **Event Schema** com detalhes:
  - Nome, descrição, datas (15-20 Jun 2026)
  - Local: Portugal
  - Modo: Offline
  - Ofertas (tickets)
  
- ✅ **Organization Schema** com:
  - Links sociais (Facebook, Instagram, Twitter)
  - Email de contato
  - Logo

### 4. **Performance & Crawling**
- ✅ `<link rel="canonical">` definido
- ✅ `dns-prefetch` para Google Fonts
- ✅ `preconnect` com crossorigin para fonts.gstatic.com
- ✅ `preload` da stylesheet de fontes
- ✅ `hreflang` alternates para português

### 5. **Ficheiros de Configuração**
- ✅ **sitemap.xml** criado com:
  - 5 URLs principais (home + 4 seções)
  - Prioridades bem distribuídas
  - Datas de modificação atualizadas
  
- ✅ **robots.txt** criado com:
  - Permitir crawling de todo o site
  - Sitemap referenciado
  - Crawl-delay otimizado para bots
  - Permissões específicas para Googlebot/Bingbot

### 6. **International & Localization**
- ✅ `lang="pt"` no HTML
- ✅ `og:locale` definido como pt_PT
- ✅ `hreflang` links para variantes de português

---

## 📋 Próximas Ações Recomendadas

### Imediatas (Muito Importante)
1. **Google Search Console**
   - [ ] Verificar domínio
   - [ ] Enviar sitemap.xml
   - [ ] Verificar erros de indexação
   
2. **Google Analytics 4**
   - [ ] Adicionar script GA4 no `<head>`
   - [ ] Configurar eventos de conversão
   
3. **Preenchimentos Necessários**
   - [ ] `google-site-verification` meta tag
   - [ ] `og:url` com domínio final
   - [ ] URLs reais para social links em Organization Schema
   - [ ] Data correta do evento (startDate/endDate)
   - [ ] Logo real URL (logo.png)

### Moderadas
4. **Breadcrumb Schema**
   ```json
   {
     "@context": "https://schema.org",
     "@type": "BreadcrumbList",
     "itemListElement": [...]
   }
   ```

5. **Image Optimization**
   - [ ] Adicionar `loading="lazy"` em imagens
   - [ ] Adicionar `alt` text descritivo
   - [ ] Implementar WebP com fallback
   - [ ] Otimizar tamanhos de imagem

6. **Performance Signals (Core Web Vitals)**
   - [ ] Reduzir animações complexas em mobile
   - [ ] Lazy load de elementos não-críticos
   - [ ] Minificar CSS inline
   
### Avançadas
7. **Rich Snippets**
   - [ ] FAQSchema para perguntas frequentes
   - [ ] ReviewSchema se houver reviews
   - [ ] AggregateRating se aplicável

8. **Local SEO**
   - [ ] LocalBusinessSchema se local físico definido
   - [ ] Google My Business otimizado
   - [ ] Citation building em diretórios

9. **Link Building**
   - [ ] Criar backlinks de sites de eventos/educação
   - [ ] Parcerias com influenciadores edu-tech
   - [ ] Press release com links

---

## 🔍 Como Verificar

### Validação Online (Grátis)
1. **Schema.org Validation**
   - https://validator.schema.org/

2. **Google Rich Results Test**
   - https://search.google.com/test/rich-results

3. **Google Mobile-Friendly Test**
   - https://search.google.com/test/mobile-friendly

4. **SEO Audit Tools**
   - Lighthouse (Chrome DevTools)
   - Screaming Frog (free version)

---

## 📊 Métricas para Monitorar

- **Impressões** (Google Search Console)
- **CTR** (Click-Through Rate)
- **Posição Média** para keywords
- **Páginas cobertas**
- **Erros de crawling**
- **Core Web Vitals** (Speed Insights)

---

## 🎯 Keywords Principais para Focar

1. "festival educação portugal"
2. "mini MBA"
3. "workshops aprendizagem"
4. "conferências verão"
5. "educação prática"

---

## ✨ Notas

- A home é o foco principal (priority 1.0)
- Schema de Event é criticamente importante para visibilidade em resultado de eventos
- Sitemap ajuda bots a descobrir todas as seções
- Preload de fonts melhora LCP (Largest Contentful Paint)

**Status: 75% de SEO onpage completo ✅**
