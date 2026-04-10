# ⏭️ Próximos Passos — Setup Final (30 minutos)

## 🎯 Objetivo
Completar o setup de Google Analytics e Google Search Console para começar a receber tráfego orgânico.

---

## 📋 Checklist de Ações

### ✅ Task 1: Google Analytics 4 Setup (5 minutos)

#### Passo 1: Criar Conta
1. Ir a https://analytics.google.com/
2. Clicar "Começar"
3. Preencher:
   - Nome da conta: `O Festival`
   - Nome da propriedade: `minimbafalso.pt`
   - Fuso horário: `Portugal (GMT+0)` ou `Portugal (GMT+1)`
   - Moeda: `EUR`

#### Passo 2: Criar Web Stream
1. Selecionar "Web"
2. Preencher:
   - Website URL: `https://minimbafalso.pt/`
   - Nome da stream: `Website`
3. Criar

#### Passo 3: Copiar ID
1. Copiar o ID (formato: `G-XXXXXXXXXX`)
2. ⚠️ **NOTA**: Este é o teu ID único

#### Passo 4: Editar HTML
1. Abrir `index.html` (linha ~120)
2. Procurar: `<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>`
3. Substituir `G-XXXXXXXXXX` pelo teu ID
4. Procurar: `gtag('config', 'G-XXXXXXXXXX');`
5. Substituir novamente com teu ID

#### Passo 5: Deploy
1. Fazer commit das mudanças
2. Deploy do `index.html` atualizado
3. Esperar 10 minutos para começar a ver dados em GA

---

### ✅ Task 2: Google Search Console Verification (15 minutos)

#### Passo 1: Ir ao GSC
1. Ir a https://search.google.com/search-console/
2. Clicar "Começar" ou "Ir ao Search Console"

#### Passo 2: Adicionar Propriedade
1. Clicar "+ Adicionar propriedade"
2. Selecionar "URL prefix"
3. Digitar: `https://minimbafalso.pt/`
4. Clicar "Continuar"

#### Passo 3: Copiar Token
1. Google vai mostrar um token (parece assim):
   ```
   google1234567890abcdefghijklmnop
   ```
2. ⚠️ **Copiar o token inteiro**

#### Passo 4: Editar HTML
1. Abrir `index.html` (linha ~40)
2. Procurar: `<meta name="google-site-verification" content="TODO_ADICIONA_TOKEN_DO_GSC">`
3. Substituir `TODO_ADICIONA_TOKEN_DO_GSC` com o token do GSC
4. **Exemplo:**
   ```html
   <meta name="google-site-verification" content="google1234567890abcdefghijklmnop">
   ```

#### Passo 5: Deploy
1. Fazer commit das mudanças
2. Deploy do `index.html` atualizado
3. Voltar ao GSC
4. Clicar "Verificar"
5. ✅ Deve aparecer "Propriedade verificada"

#### Passo 6: Submeter Sitemap
1. No painel esquerdo do GSC: "Sitemaps"
2. Clicar "Adicionar novo sitemap"
3. Digitar: `sitemap.xml`
4. Clicar "Enviar"
5. ✅ GSC começará a processar

---

### ✅ Task 3: Validação (10 minutos)

#### Validação 1: Rich Results Test
1. Ir a https://search.google.com/test/rich-results
2. Digitar URL: `https://minimbafalso.pt/`
3. Clicar "Testar URL ativa"
4. ✅ Deve aparecer:
   - "✅ No issues found"
   - Preview com Event schema

#### Validação 2: PageSpeed Insights
1. Ir a https://pagespeed.web.dev/
2. Digitar URL: `https://minimbafalso.pt/`
3. Clicar "Analisar"
4. Esperar resultado
5. ✅ Verificar:
   - Performance score > 70
   - LCP < 2.5s
   - Nenhum erro crítico

#### Validação 3: Mobile-Friendly Test
1. Ir a https://search.google.com/test/mobile-friendly
2. Digitar URL: `https://minimbafalso.pt/`
3. Clicar "Testar URL"
4. ✅ Deve aparecer:
   - "✅ Page is mobile friendly"

---

## 📊 Depois de Deploy — O Que Esperar

### Primeiras 24 Horas
- [ ] Google Analytics começa a rastrear
- [ ] Google Search Console verifica domínio
- [ ] Primeiros dados aparecem em Analytics

### Primeira Semana
- [ ] GSC mostra "Processando sitemap"
- [ ] Primeiras URLs começam a ser crawladas
- [ ] ~0-10 impressões de search

### Segunda Semana
- [ ] GSC mostra URLs descobertas
- [ ] Primeiras URLs indexadas
- [ ] ~10-50 impressões/dia

### Terceira/Quarta Semana
- [ ] 50%+ de indexação
- [ ] Primeiros cliques (tráfego orgânico)
- [ ] Primeiros rankings para long-tail keywords

---

## 🔍 Como Monitorar Depois

### Google Search Console
```
Login → Painel → Verificar:
- Performance (Cliques, Impressões, CTR, Posição)
- Cobertura (URLs indexadas)
- Erros de crawling (se houver)
- Core Web Vitals
```

### Google Analytics
```
Login → Analytics → Verificar:
- Usuários/Sessões (tráfego)
- Origem do tráfego (Organic Search)
- Taxa de rejeição
- Páginas populares
```

### Weekly
- [ ] Verificar GSC por erros
- [ ] Verificar Analytics por tráfego novo
- [ ] Notar keywords que começam a rankear

### Monthly
- [ ] Revisar Performance em GSC
- [ ] Revisar Core Web Vitals
- [ ] Analisar comportamento do usuário em GA

---

## ⚠️ Erros Comuns a Evitar

```
❌ Esquecer ID do Google Analytics
   → Não terá dados de tráfego

❌ Typo no token do GSC
   → Domínio não será verificado

❌ Não fazer deploy após editar
   → Mudanças não ficam ativas

❌ Editar ficheiros errados
   → Verifica a linha correta antes de editar

❌ Não esperar tempo suficiente
   → Google leva 1-4 semanas para indexar

✅ Dupla verificação antes de deploy!
```

---

## 📝 Ficheiros para Editar

```
index.html
├── Linha ~40   → Meta tag de GSC verification
│                (procura: google-site-verification)
│
└── Linha ~120  → Google Analytics script
                 (procura: googletagmanager.com/gtag)
```

---

## 🎬 Resumo Rápido

1. **Analytics** (5 min)
   - Criar ID em analytics.google.com
   - Editar index.html com ID
   - Deploy

2. **Search Console** (15 min)
   - Ir a search.google.com/search-console/
   - Copiar token
   - Editar index.html com token
   - Deploy
   - Submeter sitemap.xml

3. **Validação** (10 min)
   - Rich Results Test ✅
   - PageSpeed Insights ✅
   - Mobile-Friendly Test ✅

4. **Esperar**
   - 1 semana: Indexação começa
   - 2-4 semanas: Primeiros resultados
   - 2-6 meses: Rankings melhores

---

## ✨ Quando Tudo Estiver Pronto

```
✅ Google Analytics rastreando tráfego
✅ Google Search Console indexando páginas
✅ Sitemap processado
✅ Rich Results validados
✅ Mobile-friendly confirmado
✅ Performance otimizado

🎉 O Festival está online no Google!
```

---

## 📞 Suporte

Se tiveres dúvidas:

1. **Google Analytics Help**: https://support.google.com/analytics
2. **Search Console Help**: https://support.google.com/search-console/
3. **Rich Results Help**: https://developers.google.com/search/docs/advanced/rich-results

---

## 🎯 Resultado Final

Depois de completar estes passos, o site O Festival estará:

✅ 100% otimizado para SEO
✅ Rastreando tráfego com Google Analytics
✅ Indexado e rankando no Google
✅ Pronto para crescimento orgânico

**Tempo até resultados: 2-4 semanas**
**Tempo até top 10: 2-6 meses**

---

**Última atualização**: 2026-04-10
**Status**: Pronto para implementação
**Tempo estimado**: 30 minutos
