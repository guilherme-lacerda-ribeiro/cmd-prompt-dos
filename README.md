# cmd-prompt-dos

## comandos comuns
- `type` / `more` listar conteúdo do arquivo
- fc  comoarar arquivos
- tar compactar (-cf, -xf, -tf)
- tree arvore de diretórios
- mkdir rmdir cria e apaga diretório
- help ajuda
- move copy rename del manipulação básica de arquivos
- cls limpa o terminal
- systeminfo date informações do sistema
- shutdown desliga ou reinicia
- find similar ao grep linux

## variáveis de ambiente 
Path
- `echo %path%` ou `set`
- `set msg=Olá Mundo!`
seta uma variável no prompt, fechou perdeu

<pre>
@echo off 
rem limpando a tela
cls
set /p nome=Digite seu nome completo =
set /p email=Digite seu e-mail principal =
pause
echo ..................................................................................
echo Seu nome é %nome% e seu e-mail %email%
</pre>

- [`setx`](https://learn.microsoft.com/pt-br/windows-server/administration/windows-commands/setx)
Adicionar variavel de ambiente de modo permanente, **prompt como administrador**.

`C:\Windows\system32>setx path "%path%;C:\Users\Emerson\Desktop\prompt\bin" /M`

## exemplos de scripts
<pre>
cls
echo executando o script
move *.log .\Backup
pause
</pre>

<pre>
@echo off
echo Compactando arquivos
tar -cf notas.zip *.xml
</pre>

## tratamento erros
Códigos no terminal com significados específicos:
- Zero (0) significa a entrada de um comando no terminal;
- Um (stdout) representa a saída do comando no terminal;
- Dois (2) significa a saída de erro.

<pre>
@echo off
echo Compactando arquivos
tar -cf notas.zip *.xml 2> erros.txt
</pre>

<pre>
@echo off
echo Compactando arquivos
tar -cf notas.zip *.xml 2> erros.txt
IF %ERRORLEVEL% NEQ 0 (echo "Erro na execução do script")
</pre>

## winget gerenciador pacotes
A partir do Win 10. [Documentação](https://learn.microsoft.com/pt-br/windows/package-manager/winget/).

winget --info

winget search Java

winget install -e --id Oracle.JDK.19

alternativa para abaixo de win 10 é o [chocolatey](https://chocolatey.org/).

## alternativas ao cmd
- PowerShell
- cmder (não é da microsoft)
- Windows Terminal `winget install -e --id Microsoft.WindowsTerminal`
