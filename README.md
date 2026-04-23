# 🌙 Moon Ventures — NPS & Atendimento Hub

Dashboard interno da Moon Ventures para acompanhamento de NPS e métricas de atendimento das marcas **Minimal Club** e **Hoomy**, com visão consolidada **MOON** (as duas marcas juntas).

---

## O que é esse arquivo?

Um único arquivo HTML que roda direto no navegador — sem instalação, sem servidor, sem dependências para baixar. Basta abrir o arquivo e fazer login com sua conta Google.

Ele se conecta automaticamente às planilhas do Google Sheets que alimentam os dados, carrega tudo em tempo real e apresenta as informações em gráficos, tabelas e KPIs organizados por área.

---

## Como acessar

1. Faça o download do arquivo `nps_dashboard_v5_6.html`
2. Abra no **Google Chrome** ou **Microsoft Edge**
3. Clique em **Entrar com Google**
4. Autorize o acesso (necessário apenas na primeira vez)
5. Os dados carregam automaticamente

> **Importante:** sua conta Google precisa ter acesso às planilhas do grupo. Caso os dados não apareçam, entre em contato com o responsável pelo B.Ops.

---

## Estrutura do dashboard

O dashboard é organizado em duas grandes frentes, acessíveis pela **barra lateral esquerda**:

### 📊 NPS
Acompanhamento das pesquisas de satisfação enviadas via WhatsApp.

| Seção | O que mostra |
|---|---|
| **NPS — Minimal Club** | NPS Score, promotores, passivos, detratores, tags, comentários e evolução mensal da Minimal |
| **NPS — Hoomy** | Mesmas métricas para a Hoomy, com análise adicional por produto |
| **NPS — MOON** | Visão consolidada comparando Minimal e Hoomy lado a lado |

### ⏱ Atendimento
Métricas de tempo de atendimento dos tickets de suporte.

| Seção | O que mostra |
|---|---|
| **Atendimento — Minimal** | TMA, TME, análise por dia da semana e hora, tabela por atendente |
| **Atendimento — Hoomy** | Mesmas métricas para a Hoomy |
| **Atendimento — MOON** | Comparativo Minimal vs Hoomy com gráficos lado a lado |

---

## Métricas disponíveis

### NPS (por marca)
- **NPS Score** — pontuação geral do período selecionado
- **NPS do Ano** — acumulado do ano corrente
- **Total de Respostas** — quantidade de avaliações no período
- **Promotores / Passivos / Detratores** — contagem e percentual de cada grupo

### Atendimento (por marca)
- **TMA Geral** — Tempo Médio de Atendimento (do início ao fechamento do ticket)
- **TME Geral** — Tempo Médio de Espera (do contato até o primeiro atendimento)
- **TMA Dias Úteis** — TMA considerando apenas horário comercial
- **TME Dias Úteis** — TME considerando apenas horário comercial
- **Fora do Horário** — quantidade de tickets abertos antes das 9h ou após as 18h
- **TMA Fora do Horário** — tempo médio desses tickets específicos

> Os KPIs de TMA e TME são coloridos automaticamente:
> - 🟢 **Verde** — menos de 1 hora
> - 🟡 **Amarelo** — entre 1h e 2h
> - 🔴 **Vermelho** — acima de 2h

---

## Gráficos

### NPS
- **Distribuição de sentimentos** — gráfico de rosca com % de promotores, passivos e detratores
- **Tags mais citadas** — barras horizontais com os principais motivos por sentimento
- **Micro-temas por tag** — análise aprofundada dos sub-motivos, com toggle entre detratores e promotores
- **Evolução mensal do NPS** — linha histórica mês a mês
- **Volume de respostas por dia** — barras empilhadas mostrando o fluxo diário
- **NPS acumulado** — linha que mostra o NPS somado ao longo do tempo
- **Distribuição por produto** — análise de NPS separada por produto (Hoomy)
- **Comparativo Minimal vs Hoomy** — gráficos lado a lado na seção MOON

### Atendimento
- **TMA e TME por dia da semana** — mostra a média de cada dia da semana **corrente** (segunda a domingo), ignorando filtros de data
- **Atendimentos por hora de abertura** — distribuição de quando os tickets são abertos (9h–18h)
- **Atendimentos por hora de fechamento** — distribuição de quando os tickets são encerrados (9h–18h)
- **Tabela de atendentes** — ranking por TMA com TMA, TME, TMA dias úteis, TME dias úteis e total de tickets

---

## Filtros

Cada seção tem seus próprios filtros. Os principais são:

| Filtro | Onde aparece | O que faz |
|---|---|---|
| Ano / Mês | Todas as seções | Filtra pelo período selecionado |
| Data início / Data fim | Todas as seções | Filtro por range de datas personalizado |
| Atendente | Atendimento | Filtra pelos tickets de um atendente específico |
| Sentimento | NPS | Filtra por promotores, passivos ou detratores |
| Produto | NPS Minimal e Hoomy | Filtra por produto específico |
| Tag / Tag Micro | NPS Hoomy | Filtra pelo motivo do contato |
| Nota (0–10) | NPS | Filtra por nota específica dada pelo cliente |

Todos os filtros têm um botão **✕ Limpar** para resetar rapidamente.

---

## Funcionalidades gerais

| Funcionalidade | Como usar |
|---|---|
| **Atualizar dados** | Botão "↻ Atualizar" na barra superior — busca os dados mais recentes das planilhas |
| **Atualização automática** | Os dados são atualizados automaticamente a cada **5 minutos** enquanto o dashboard estiver aberto |
| **Exportar CSV** | Botão "⬇ CSV" — exporta os dados filtrados da seção atual para uma planilha |
| **Tema claro / escuro** | Botão ☀️/🌙 na barra superior — alterna entre os dois temas e salva a preferência |
| **Recolher sidebar** | Botão ☰ no canto superior da barra lateral — deixa a sidebar compacta para ganhar espaço |
| **Comentários** | Clique em qualquer comentário na tabela para abrir o texto completo em um modal |
| **Tags clicáveis** | Clique em qualquer tag nos gráficos para ver todas as respostas com aquela tag |
| **Logout** | Clique no seu nome/avatar no canto superior direito |

---

## Fontes de dados

Os dados vêm de **4 planilhas do Google Sheets**, atualizadas em paralelo a cada refresh:

| Planilha | Marca | Dados |
|---|---|---|
| Base Minimal NPS | Minimal Club | Respostas de NPS |
| Base Hoomy NPS | Hoomy | Respostas de NPS |
| Operações Minimal | Minimal Club | TMA, TME e dados de atendimento |
| Operações Hoomy | Hoomy | TMA, TME e dados de atendimento |

> O acesso é feito de forma segura via login Google (OAuth2). Nenhum dado fica armazenado fora do seu navegador — tudo é carregado na memória local a cada sessão.

---

## Detalhes técnicos (para quem precisar dar manutenção)

- **Arquivo único** — todo o CSS, JavaScript e HTML estão em um único arquivo `.html`, sem dependências externas para instalar
- **Bibliotecas usadas** — Chart.js 4.4.0 (gráficos) e Google Identity Services (login), ambas carregadas via CDN
- **Autenticação** — Google OAuth2 com escopos de leitura de planilhas e perfil do usuário
- **Temas** — controlados por variáveis CSS (`data-theme="dark"` ou `"light"`) e salvos no `localStorage` do navegador
- **Compatibilidade** — otimizado para Chrome e Edge; pode apresentar comportamento diferente em Safari ou Firefox

---

## Navegação rápida

```
🏠 Home
├── 📊 NPS
│   ├── Minimal Club
│   ├── Hoomy
│   └── MOON (Comparativo)
└── ⏱ Atendimento
    ├── Minimal Club
    ├── Hoomy
    └── MOON (Comparativo)
```

---

## Dúvidas ou problemas?

Em caso de dados incorretos, erros de login ou qualquer comportamento inesperado, fale com o time de **B.Ops da Moon Ventures**.
