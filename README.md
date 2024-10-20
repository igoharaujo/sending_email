# Documentação do Script de Envio de E-mail com Anexo

## Visão Geral
Este script utiliza a biblioteca `smtplib` para enviar um e-mail com anexo, juntamente com um corpo de texto. O arquivo anexo é um Excel (`teste.xlsx`), e o conteúdo do e-mail inclui uma reflexão de Albert Einstein.

## Dependências
- `smtplib`: Usada para enviar e-mails utilizando o protocolo SMTP.
- `email.mime`: Para construir o e-mail com diferentes partes, incluindo texto e anexos.
- `encoders`: Para codificar o anexo em base64.

## Explicação do Código

1. **Importações**:
   - O código importa as bibliotecas necessárias para compor e enviar um e-mail com anexo, além de codificar o arquivo de forma adequada.

2. **Variáveis**:
   - `caminho_anexo`: Caminho do arquivo que será anexado (neste caso, um arquivo Excel chamado `teste.xlsx`).
   - `corpo_email`: Texto do e-mail, que inclui uma reflexão de Albert Einstein.

3. **Criação da Mensagem**:
   - Uma mensagem de e-mail multipart é criada utilizando `MIMEMultipart()`.
   - As propriedades do e-mail, como remetente (`From`), destinatário (`To`) e assunto (`Subject`), são definidas.

4. **Corpo do E-mail**:
   - O texto definido em `corpo_email` é anexado ao corpo do e-mail com `MIMEText`.

5. **Anexando Arquivo**:
   - O arquivo especificado em `caminho_anexo` é aberto no modo binário.
   - O conteúdo do arquivo é codificado em base64 e anexado à mensagem.

6. **Envio do E-mail**:
   - Um servidor SMTP é criado utilizando o servidor do Gmail (`smtp.gmail.com`).
   - A conexão é estabelecida através de TLS com o método `starttls()`.
   - As credenciais de login (remetente e senha) são usadas para autenticação.
   - O e-mail é enviado utilizando o método `sendmail()`.

## Considerações
- **Remetente, destinatário e senha**: Estes valores precisam ser definidos antes da execução do código.
- **Configurações de SMTP**: O script está configurado para o Gmail, então é necessário permitir acesso a aplicativos menos seguros nas configurações da conta de e-mail ou usar uma senha de aplicativo.

## Exemplo de Uso
Este script pode ser utilizado para enviar e-mails automaticamente com um arquivo anexo, como relatórios ou documentos, a partir de um sistema Python.

