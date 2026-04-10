# 🔍 Google Search Console (GSC) - Setup Guide

## 📋 Checklist de Verificação

### 1. **Verificar Domínio no GSC**

#### Opção A: Meta Tag (Mais Rápido ⚡)
1. Ir a https://search.google.com/search-console/
2. Clicar em "Adicionar propriedade"
3. Selecionar "URL prefix"
4. Digitar: `https://minimbafalso.pt/`
5. Clicar em "Continuar"
6. **GSC vai gerar um token** → copiar
7. **Editar** [index.html:40](index.html#L40) substituir:
   ```html
   <meta name="google-site-verification" content="TODO_ADICIONA_TOKEN_DO_GSC">
   ```
   por:
   ```html
   <meta name="google-site-verification" content="AQUI_COLA_O_TOKEN_DO_GSC">
   ```
8. Deploy / Save o arquivo
9. Voltar ao GSC → clicar "Verificar"
10. ✅ Pronto! Domínio verificado

#### Opção B: Ficheiro HTML (Alternativa)
- GSC oferece download de ficheiro `google1234567890abcd.html`
- Fazer upload na raiz do servidor
- Verificar no GSC

---

### 2. **Submeter Sitemap**

Após verificação:
1. No painel esquerdo: "Sitemaps"
2. Clicar "Adicionar novo sitemap"
3. Digitar: `sitemap.xml`
4. Clicar "Enviar"
5. ✅ GSC começará a processar

---

### 3. **Verificar Cobertura**

1. Painel esquerdo: "Cobertura"
2. Verificar:
   - ✅ Página válida (em vez de "Descoberto - não indexado")
   - ❌ Erros (se houver, resolver)
3. Informações importantes:
   - Número de URLs válidas
   - Páginas não indexadas
   - Páginas com erros

---

### 4. **Envios Manuais**

Se quiser indexar rápido:
1. Painel superior: "Inspeção de URL"
2. Digitar: `https://minimbafalso.pt/`
3. Clicar "Testar URL ativa"
4. Se válida → clicar "Solicitar indexação"
5. Repetir para URLs importantes:
   - `https://minimbafalso.pt/#lineup`
   - `https://minimbafalso.pt/#bilhetes`
   - etc.

---

### 5. **Google Rich Results Test**

Após submeter:
1. Ir a https://search.google.com/test/rich-results
2. Digitar: `https://minimbafalso.pt/`
3. Validar que:
   - ✅ Event schema aparece
   - ✅ Nenhum erro no Schema
4. Screenshot para documentação

---

### 6. **Core Web Vitals & Performance**

No GSC:
1. Painel esquerdo: "Core Web Vitals"
2. Verificar:
   - LCP (Largest Contentful Paint) < 2.5s
   - FID (First Input Delay) < 100ms
   - CLS (Cumulative Layout Shift) < 0.1
3. Se problemas:
   - Ir a PageSpeed Insights
   - Resolver sugestões críticas

---

### 7. **Mobile-Friendly Test**

1. Ir a https://search.google.com/test/mobile-friendly
2. Digitar URL
3. Verificar:
   - ✅ "Página é otimizada para mobile"
   - ❌ Nenhum "Mobile usability issue"

---

### 8. **Monitorar Performance**

Regularmente:
1. Painel: "Performance"
2. Monitorar:
   - **Impressões** (quantas vezes aparece nos resultados)
   - **CTR** (percentagem que clica)
   - **Posição média** (que posição nos resultados)
   - **Cliques** (tráfego)

---

## 🎯 KPIs para Acompanhar

| Métrica | Inicial | Alvo (3 meses) |
|---------|---------|----------------|
| URLs Cobertas | - | 100% |
| Impressões | 0 | 100+ |
| Cliques | 0 | 50+ |
| Posição Média | - | < 20 |
| CTR | - | 3-5% |

---

## 🚨 Erros Comuns a Evitar

- ❌ Esquecer de ativar **robots.txt** (já feito ✅)
- ❌ Ter **noindex** em meta tags (não tem ✅)
- ❌ Bloquear em **robots.txt** URLs que quer indexar
- ❌ Não estruturar dados com Schema (já feito ✅)
- ❌ Esquecer de enviar **sitemap.xml** (tu fazes agora)

---

## ⏰ Timeline Esperado

| Ação | Tempo |
|------|-------|
| Verificação domínio | Imediato |
| Crawl inicial | 24-48h |
| Indexação de home | 3-7 dias |
| Indexação completa | 2-4 semanas |
| Rankings | 4-12 semanas |

---

## 📞 Suporte

- **Documentação oficial**: https://support.google.com/search-console/
- **Community**: https://support.google.com/webmasters/community

---

## ✅ Checklist Final

- [ ] Meta tag de verificação adicionada
- [ ] Domínio verificado no GSC
- [ ] Sitemap.xml submetido
- [ ] Robots.txt validado
- [ ] Rich Results test passou
- [ ] Mobile-friendly test passou
- [ ] URLs solicitadas para indexação
- [ ] Core Web Vitals verificados

**Status: 🟡 Aguardando verificação do domínio**
