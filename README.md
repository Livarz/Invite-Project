# Invite Project

Convites interativos e trolls para WhatsApp, Instagram, Discord e grupos sociais.

O primeiro template do projeto é o **Não Clicável**: um convite onde o botão negativo foge do mouse/toque e a pessoa praticamente só consegue aceitar.

## Objetivo

Transformar a trend de “convite feito por programador” em uma ferramenta no-code:

1. A pessoa escolhe um modelo de convite.
2. Personaliza pergunta, textos dos botões, WhatsApp e aparência.
3. Gera um link temporário.
4. Envia para outra pessoa.
5. O convidado interage com a pegadinha e confirma pelo WhatsApp ou por URL configurada.

## Estrutura inicial

```txt
docs/
  jornada-usuario.md

templates/
  nao-clicavel/
    index.html
```

## Template inicial

### Não Clicável

- Botão “Não” foge do cursor/toque.
- Botão “Sim” confirma a ação.
- Mensagem final com animação de emojis.
- Redirecionamento para WhatsApp.

## Próximas fases

- Frontend Lovable com home, galeria de templates, editor e preview.
- Backend WordPress/REST API para salvar convites temporários.
- Expiração gratuita em 10 minutos.
- Planos pagos com URL personalizada, duração maior e analytics.
- Geração de imagem/story para compartilhamento social.
