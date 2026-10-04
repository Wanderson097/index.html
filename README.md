# Kit Emprego com IA: página de venda

Página de venda de uma página só (HTML e CSS, sem frameworks) para o **Kit Emprego com IA**: modelos de currículo, comandos prontos para usar na IA, guia de LinkedIn e treino de entrevista.

O pagamento é feito por **Pix**, com QR code e código "copia e cola" já com o valor definido. Depois de pagar, o cliente envia o comprovante pelo WhatsApp e recebe o material.

## Estrutura

```
.
├── index.html   # a página inteira (HTML, CSS e JS no mesmo arquivo)
└── README.md
```

Não há dependências nem etapa de build. As únicas chamadas externas são as fontes do Google Fonts (Outfit e Nunito Sans), e a página funciona com fontes do sistema se elas não carregarem.

## Rodar localmente

Abra o `index.html` no navegador. Se preferir um servidor local:

```bash
python3 -m http.server 8000
```

Depois acesse `http://localhost:8000`.

## Publicar na Vercel

1. Suba este repositório no GitHub.
2. Na Vercel, clique em **Add New > Project** e importe o repositório.
3. Deixe as configurações padrão (é um site estático, sem comando de build) e clique em **Deploy**.

A cada `git push`, a Vercel publica a nova versão automaticamente. O link já vem com HTTPS.

## Como editar

Tudo fica no `index.html`.

| O que mudar | Onde |
|---|---|
| Cores e fontes | Bloco `:root` no começo do `<style>` |
| Textos e perguntas frequentes | Corpo do HTML, seção por seção |
| Preço exibido | Seção `offer`, no elemento `.price` |
| Link do WhatsApp | Botão "Enviar comprovante", no atributo `href` (`wa.me/55DDDNUMERO`) |

### Atenção ao mudar o preço ou a chave Pix

O QR code e o código "copia e cola" são gerados com o valor e a chave embutidos. **Se você mudar o preço ou a chave, apenas editar o texto não basta**: é preciso gerar um novo QR code e um novo código Pix com os dados atualizados e substituí-los no HTML. Caso contrário, a página mostra um preço e cobra outro.

Depois de qualquer alteração no Pix, faça um pagamento de teste para confirmar que o valor e o destinatário estão corretos.

## Segurança e cuidados

- **Não coloque o material do kit (PDFs, modelos, comandos) neste repositório.** Ele é público e qualquer pessoa conseguiria baixar de graça. Entregue o material por WhatsApp ou e-mail depois de confirmar o pagamento.
- A chave Pix na página serve apenas para receber valores. Mesmo assim, não publique senhas, tokens ou dados pessoais no repositório.
- Não publique depoimentos que não sejam reais. Se for adicionar, use apenas depoimentos autorizados por clientes.
- A página não promete contratação, e esse aviso deve ser mantido no FAQ.

## Licença

Todos os direitos reservados. O conteúdo do kit e o texto da página não devem ser copiados ou revendidos sem autorização.
