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
- `set`
seta uma variável no prompt, fechou perdeu
- [`setx`](https://learn.microsoft.com/pt-br/windows-server/administration/windows-commands/setx)
Adicionar variavel de ambiente de modo permanente

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

`
@echo off
echo Compactando arquivos
tar -cf notas.zip *.xml 2> erros.txt
`

`
@echo off
echo Compactando arquivos
tar -cf notas.zip *.xml 2> erros.txt
IF %ERRORLEVEL% NEQ 0 (echo "Erro na execução do script")
`

