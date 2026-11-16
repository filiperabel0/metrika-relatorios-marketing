# Metrika · Relatórios de marketing para clientes

Plataforma web que junta os números de Instagram, Meta Ads, Google Analytics, YouTube e outras fontes em relatórios, painéis e envios automáticos para os clientes de uma agência. Está no ar em **https://metrika.rbldesign.com.br**.

![Site do Metrika](img/site.png)

## Que problema resolve, e para quem

Na RBL Design, minha agência, o relatório mensal de cada cliente dependia de uma ferramenta paga e de trabalho manual para montar e enviar. Criei o Metrika para resolver isso dentro de casa: a equipe conecta as contas do cliente uma vez e o sistema monta o relatório, compara períodos, avisa quando uma meta foi batida ou um limite de investimento foi ultrapassado e envia o link por e-mail no dia combinado. O cliente abre o relatório pelo link, sem precisar de login.

## Tecnologias

- **Aplicação:** Next.js 16, React, TypeScript, Tailwind CSS 4 e Recharts
- **Banco de dados:** PostgreSQL na Neon
- **Hospedagem e rotinas:** Vercel, com GitHub Actions disparando as automações de hora em hora
- **Integrações:** OAuth 2.0 com Google (Google Analytics 4 e YouTube) e Meta (Instagram e Facebook), envio de e-mail pela Resend
- **Segurança:** contas individuais com senha em hash scrypt, perfis de acesso conferidos no servidor, tokens de integração criptografados com AES-256-GCM, proteção contra CSRF, limite de tentativas de login e cabeçalhos CSP e HSTS

## Qual foi a minha parte

Projeto individual. Defini as regras de negócio, desenhei a interface e desenvolvi o sistema, com apoio de IA (Claude Code) na escrita do código. Também cuidei da publicação: domínio, banco, rotinas agendadas e o cadastro dos aplicativos OAuth no Google Cloud e na Meta for Developers, incluindo as páginas de privacidade, termos e exclusão de dados exigidas por essas plataformas.

Alguns resultados concretos:
- Em produção desde 04/11/2026, no domínio da agência.
- Conexão real testada com a conta de Instagram de uma cliente e com uma propriedade do Google Analytics 4.
- App OAuth do Google publicado em produção, com a marca verificada pelo Google.
- Encontrei e corrigi um bug em que uma regra do `.gitignore` tirava a rota de dados do build, e os relatórios em produção ficavam sem números.

## Como acessar

- Site e solicitação de acesso: https://metrika.rbldesign.com.br
- O sistema é de uso interno da agência e exige login. O código-fonte é privado por ser um produto comercial; posso mostrá-lo em uma conversa ou entrevista.
