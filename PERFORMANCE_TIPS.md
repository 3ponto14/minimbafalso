# ⚡ Performance & Core Web Vitals Optimization

## 🎯 Objetivo
Melhorar Core Web Vitals para ranking melhor no Google (fator crítico desde 2024)

---

## 📊 Core Web Vitals Atual

### O que são?
- **LCP** (Largest Contentful Paint): Tempo até aparecer maior elemento visível
- **FID** (First Input Delay): Latência ao clicar/interagir
- **CLS** (Cumulative Layout Shift): Movimentação de elementos durante carregamento

### Targets Ideais
- LCP: < 2.5 segundos ✅ Bom
- FID: < 100 milisegundos ✅ Bom
- CLS: < 0.1 ✅ Bom

---

## 🔧 Otimizações Implementadas

### 1. **Fonts Optimization** ✅
```html
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="preload" as="style" href="...fonts.googleapis.com...">
```
**Impacto**: -300-500ms em LCP

### 2. **Image Lazy Loading** ✅
```html
<img ... loading="lazy">
```
**Impacto**: Menos JavaScript bloqueado, melhor LCP

### 3. **Alt Text Otimizado** ✅
Agora com descrições detalhadas para acessibilidade e SEO

### 4. **DNS Prefetch** ✅
```html
<link rel="dns-prefetch" href="https://fonts.googleapis.com">
```
**Impacto**: -50-100ms em DNS lookup

---

## 🚀 Otimizações Recomendadas (Manual)

### A. Minificar CSS Inline
**Ganho**: -10-20% do tamanho inicial

Atualmente o CSS está bem organizado. Em produção:
```bash
# Instalar minifier
npm install -g cssnano

# Minificar
cssnano style.css > style.min.css
```

### B. Reduzir Animações em Mobile
**Problema**: Muitas animações (grain, sunburst, marquee) consomem CPU/bateria

**Solução**: Respeitar `prefers-reduced-motion`
```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
  }
  body::before { animation: none; }
  .hero-sunburst { animation: none; }
  /* etc */
}
```

**Ganho**: +20-30% em performance em mobile

### C. Lazy Load Background Images
**Problema**: Hero tem múltiplos gradients + overlays carregados imediatamente

**Solução** (exemplo):
```css
.hero {
  background-color: #C84000; /* fallback rápido */
  background-image: none; /* carregado depois */
}

.hero.loaded {
  background-image: radial-gradient(...);
}
```

```js
window.addEventListener('load', () => {
  document.querySelector('.hero').classList.add('loaded');
});
```

**Ganho**: -200-400ms em LCP

### D. Compress Images
**Problema**: Imagens Unsplash em tamanho grande

**Solução**: Converter para WebP + usar picture tag
```html
<picture>
  <source srcset="...image.webp?w=800" type="image/webp">
  <img src="...image.jpg?w=800" alt="...">
</picture>
```

**Ganho**: -30-50% em tamanho de imagem

### E. Implementar Service Worker (Offline/Cache)
```js
// sw.js
self.addEventListener('install', event => {
  event.waitUntil(
    caches.open('v1').then(cache => {
      return cache.addAll([
        '/',
        '/index.html',
        '/sitemap.xml'
      ]);
    })
  );
});
```

**Ganho**: Carregamento offline + cache

---

## 📈 Medição

### Google PageSpeed Insights
1. Ir a https://pagespeed.web.dev/
2. Digitar: `https://minimbafalso.pt/`
3. Verificar:
   - Performance score (alvo: 90+)
   - Accessibility score
   - Best Practices
   - SEO score

### Chrome DevTools Lighthouse
1. Abrir DevTools (F12)
2. Tab "Lighthouse"
3. Selecionar "Mobile" ou "Desktop"
4. Clicar "Analyze page load"
5. Esperar resultado

### Web Vitals em Produção
```js
// Adicionar ao index.html antes do </body>
<script>
  const vitals = {
    lcp: (metric) => console.log('LCP', metric.value),
    fid: (metric) => console.log('FID', metric.value),
    cls: (metric) => console.log('CLS', metric.value)
  };
  
  import('https://unpkg.com/web-vitals@3').then(({ getCLS, getFID, getFCP, getLCP, getTTFB }) => {
    getCLS(console.log);
    getFID(console.log);
    getFCP(console.log);
    getLCP(console.log);
    getTTFB(console.log);
  });
</script>
```

---

## 🔍 Checklist de Performance

### ✅ Já Implementado
- [x] Font preload/preconnect
- [x] Image lazy loading
- [x] Alt text otimizado
- [x] DNS prefetch
- [x] Sitemap + robots.txt
- [x] Structured data (JSON-LD)

### ⏳ Para Fazer (Recomendado)
- [ ] Respeitar `prefers-reduced-motion`
- [ ] Lazy load background images
- [ ] Minificar CSS inline
- [ ] Converter imagens para WebP
- [ ] Implementar Service Worker
- [ ] Analytics 4 (já com placeholder)

### 🔮 Avançado (Opcional)
- [ ] Edge cache com CDN
- [ ] Image optimization com Next.js Image
- [ ] Critical CSS extraction
- [ ] Async/defer JavaScript
- [ ] Bundle splitting

---

## 📋 Performance Budget

| Métrica | Limite | Atual | Status |
|---------|--------|-------|--------|
| Bundle HTML | 200KB | ~600KB | ⚠️ |
| CSS | 100KB | inline | ℹ️ |
| Fonts | 50KB | ~100KB | ⚠️ |
| Images | 200KB | 150KB* | ✅ |
| JavaScript | 50KB | ~10KB | ✅ |

*Por imagem com lazy loading

---

## 🎬 Próximos Passos

1. **Imediato**: Verificar PageSpeed Insights
2. **Esta semana**: Implementar `prefers-reduced-motion`
3. **Este mês**: Otimizar imagens (WebP)
4. **Monitorar**: Core Web Vitals no GSC

---

## 📚 Referências

- https://web.dev/vitals/
- https://developer.chrome.com/docs/lighthouse/
- https://pagespeed.web.dev/
- https://caniuse.com/ (compatibilidade)

---

**Último update**: 2026-04-10
**Status**: 70% otimizado ⚡
