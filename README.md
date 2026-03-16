# Automação de Documentação Contábil (Gmail -> Drive)

Script desenvolvido em **Google Apps Script** para automatizar a coleta e organização de notas, boletos e comprovantes que chegam via e-mail.

### O Problema
A coleta mensal de documentos para a contabilidade era feita manualmente, buscando anexos em e-mails enviados e recebidos. Isso gerava perda de tempo, risco de esquecer arquivos e bagunça com nomes de arquivos duplicados (ex: vários arquivos chamados "boleto.pdf").

### A Solução
Criei um pipeline que faz o trabalho pesado:

1. **Filtro Inteligente:** Busca no Gmail apenas e-mails com anexos dentro do mês de competência.
2. **Padronização:** Renomeia cada arquivo com um timestamp (Data/Hora) único para evitar que um arquivo sobrescreva o outro.
3. **Organização:** Cria automaticamente uma pasta no Google Drive com o nome do mês (ex: "Relatório Contábil - 02/2026") e move tudo para lá.
4. **Notificação:** Envia um e-mail para o responsável com o link pronto da pasta para revisão.

### Tecnologias
* **Google Apps Script** (JavaScript)
* **APIs:** Gmail, Drive e MailApp

### Como rodar o projeto
1. O código principal está na pasta `src/`.
2. Basta ajustar a constante `EMAIL_DESTINO` no script.
3. No painel do Apps Script, configure um acionador (Trigger) para rodar a função uma vez por mês.

---

**Impacto:** O processo de triagem de documentos, que antes tomava tempo e era passível de erro, agora é executado de forma automática e auditável.
