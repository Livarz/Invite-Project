# Invite Project — Jornada de Usuário e Produto

## Visão geral

O Invite Project é uma plataforma para criar convites interativos, engraçados e virais. A ideia é permitir que qualquer pessoa crie convites com pegadinhas simples sem precisar programar.

A primeira experiência é o template **Não Clicável**, onde o botão negativo foge e o positivo dispara a confirmação.

## Público-alvo

- Casais e crushes.
- Amigos e grupos de rolê.
- Comunidades gamer/Discord.
- Streamers e criadores de conteúdo.
- Pessoas que querem criar trends para Instagram/TikTok.
- Usuários sem conhecimento técnico que querem um link divertido pronto.

## Proposta de valor

> Crie um convite impossível de recusar em menos de 1 minuto.

Diferencial: transformar uma trend técnica de programador em produto no-code, personalizável e compartilhável.

## Jornada principal — Criador do convite

### 1. Home

Objetivo: explicar rapidamente a ideia e levar o usuário para criar.

Elementos:

- Headline: `Crie convites impossíveis de recusar.`
- Subheadline: `Escolha uma pegadinha, personalize a pergunta e envie um link divertido.`
- CTA principal: `Criar convite grátis`
- Galeria de templates.
- Exemplos prontos.
- Seção “Como funciona”.
- Planos grátis/pago.

### 2. Escolha de template

O usuário escolhe um modelo:

- Não Clicável.
- Não Encolhe.
- Não Vira Sim.
- Roleta Viciada.
- Contrato Absurdo.
- Chat Fake.
- Captcha Emocional.

Para o MVP, só o **Não Clicável** precisa estar funcional.

### 3. Editor

Campos do editor:

- Pergunta principal.
- Texto auxiliar.
- Emoji/ícone principal.
- Texto do botão positivo.
- Texto do botão negativo.
- Mensagem de sucesso.
- Número do WhatsApp.
- Mensagem enviada no WhatsApp.
- URL personalizada opcional.
- Tema visual.

Exemplo:

```txt
Pergunta: Vamos jogar LoL hoje?
Texto auxiliar: Tem ranked e call no Discord 😈
Botão Sim: Tô entrando no Discord
Botão Não: Sou um vacilão e não vou
Mensagem WhatsApp: Aceitei jogar LoL hoje 😔
```

### 4. Preview

- Preview em tempo real.
- Botão “Não” fugindo no desktop e mobile.
- Simulação da mensagem final.
- Validação dos campos obrigatórios.

### 5. Geração do link

No plano grátis:

- Gera URL temporária.
- Link dura 10 minutos.
- Marca d’água discreta.

No plano pago:

- Link por 24h/7 dias/permanente.
- URL personalizada.
- Sem marca d’água.
- Analytics.
- Redirect customizado após aceitar.

### 6. Compartilhamento

- Copiar link.
- Enviar no WhatsApp.
- Compartilhar via Web Share API.
- Baixar imagem vertical para story.
- Gerar QR Code.
- Texto pronto para postar.

## Jornada — Pessoa convidada

1. Recebe o link.
2. Abre a página do convite.
3. Lê a pergunta.
4. Tenta clicar no botão negativo.
5. O botão negativo foge e muda de texto.
6. Clica no botão positivo.
7. Vê mensagem de sucesso e animação.
8. É direcionada para WhatsApp ou URL configurada.

## User cases

### Romântico

```txt
Pergunta: Quer sair comigo?
Sim: Quero muito
Não: Prefiro sofrer sozinha
WhatsApp: Aceito sair com você 💖
```

### Gamer

```txt
Pergunta: Vamos jogar LoL hoje?
Sim: Tô entrando no Discord
Não: Sou um vacilão e não vou
WhatsApp: Aceitei jogar LoL hoje 😔
```

### Rolê

```txt
Pergunta: Vai no churrasco sábado?
Sim: Levo refri
Não: Sou inimigo da alegria
WhatsApp: Confirmo presença no churrasco 🍖
```

### Festa junina

```txt
Pergunta: Vai dançar quadrilha comigo?
Sim: Já tô com a camisa xadrez
Não: Tenho medo da sanfona
WhatsApp: Aceitei ir pro arraiá 🌽
```

### Pedido de desculpas

```txt
Pergunta: Aceita minhas desculpas?
Sim: Tá perdoado
Não: Vou guardar rancor eterno
WhatsApp: Tá perdoado, mas pisa fofo 😤
```

## Templates futuros

- **Não Encolhe:** botão negativo diminui até sumir.
- **Não Vira Sim:** botão negativo troca de texto/função e vira confirmação.
- **Roleta Viciada:** todas as opções terminam em “Sim”.
- **Contrato Absurdo:** pessoa assina um contrato fake aceitando o convite.
- **Chat Fake:** interface simula conversa e bloqueia o vácuo.
- **Captcha Emocional:** pessoa prova que não é vacilona marcando opções positivas.

## Viabilidade técnica

### Frontend Lovable

Viável para home, galeria de templates, editor visual, preview ao vivo, tela de link gerado e página pública simulada.

### Backend WordPress Plugin

Recomendado para criar convites reais, salvar dados, expirar URLs gratuitas em 10 minutos, registrar views/aceites, gerenciar planos pagos e integrar pagamentos no futuro.

### Compartilhamento Instagram

Postagem automática em Story não é realista pela web simples. Alternativas viáveis: imagem 1080x1920, GIF curto, botão de download, Web Share API e texto pronto para copiar.

## Modelo de dados

```ts
type InviteData = {
  id?: string;
  template: string;
  question: string;
  subtitle: string;
  emoji: string;
  yesText: string;
  noText: string;
  successMessage: string;
  whatsappNumber: string;
  whatsappMessage: string;
  redirectUrl?: string;
  theme: string;
  expiresAt?: string;
  isPaid?: boolean;
};
```

## REST API sugerida

```txt
POST /wp-json/convite-troll/v1/invites
GET /wp-json/convite-troll/v1/invites/{publicId}
POST /wp-json/convite-troll/v1/invites/{publicId}/accept
```

## MVP recomendado

1. Lovable visual: home, template, editor, preview e geração fake.
2. Template dinâmico com `inviteConfig`.
3. Plugin WordPress com tabela custom, REST API, expiração e página pública.
4. Viral/share com QR Code, imagem de story e marca d’água grátis.
5. Monetização com URLs personalizadas, convites permanentes, analytics e pagamentos.
