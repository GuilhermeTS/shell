# SHELL BASH

# OBS: Alguns comandos não funcionaram no SHELL

## Variáveis
- Variável local: <nome_variavel=valor>
- Apagar variável: unset <nome_variavel>
- Declaração de array: <nome_do array=(valores separados por espaço sem vígula)>
- Uso do array: echo $<nome_do_array> mostrará apenas ao primeiro elemento do array, echo ${<nome_do_array>[*]} mostrará todo os elementos, echo ${<nome_do_array>[posição]} mostrará o item na posição específica, a contagem do array começa do 0, assim como a variável ela pode ser apagado com o comando unset, EX: unset <nome_do_array>[*], isso removerá todas as posições do array, para remover uma posição específica unset <nome_do_array>[posição].
- Ao declarar a variável ou vetor ela só será vista na janela de sessão, se for abrir uma nova aba ou abrir shell ela não será vista.

- Variável global: export <nome_variavel=valor>, export <nome_vetor=(valores)>
- Á variável ou vetor só será vista em outro shell se estiver na mesma sessão.

## Aliases
- Declaração: alias <nome_alias='comando'>
- Listar alias do sistema: alias
- Apagar aliases: unsetalias <nome_alias>
- Serve para abreviar comandos.
## Funções
- O bash também permite a criação de funções parecidas com alias. EX: 
teste() {
cd ~
echo 'Teste' >> arquivo_teste
}

## Arquivos de configurações do Bash
- /etc/profile - Arquivo de inicialização, executado durante o login e álido para todo sistema.

- /etc/bashrc / /etc/bash.bashrc - Arquivo de inicialização, válido para todo o sistema, executado pelo .bashrc do usuário para cada bash iniciado.

- ~/.bash_profile - Se existir será executado após /etc/profile durante o login.

- ~/.bash_login - Se o bash_profile não existir, será executado automaticamente no login.

- ~/.profile - Se nenhum dos dois anteriores existirem, será executado automaticamente no login.

- ~/.bashrc - Executado automaticamente quando o bash é iniciado.

- ~/inputrc - Contém variáveis e configurações do mode operação do bash em relação as teclas.

- ~/.bash_logout - Executado automaticamente no logout.

### Shell login - Executa os arquivos /etc/profile, ~/.bash_login, ~/.bash_profile, ~/.profile.
### Shell interativo - Executa os arquivos ~/.bashrc, /etc/bashrc / /etc/bash.bashrc.
### Shell não-interativo - Verifica a variável de ambiente BASH_ENV por padrão não é configurada


##Arquivos de script
- Ao criar um script não é necessário especificar a exetensão do arquivo que normalmente é .sh. Para criar um arquivo de script é necessário especificar na primeira linha qual o tipo de shell que será usado para rodar o script Ex: #!/bin/bash. Lembrando que o # é usado para adicionar um comentário, mas com exceção da primeira linha que é usado para especificar o shell que será usado e a combinação com !. Exemplo de script:
#!/bin/bash
echo "Hello World"
ls ~
echo "Diretório Home"
Para executar o script é necessário da permissão chmod a+x, que é equivalente a chmod 755 e opcionalmente adcionar no PATH ou colocar em algum diretório que seja visto pelo PATH, caso não esteja adicionado no PATH é necessário especificar o diretório onde se encontra o arquivo e em seguida o arquivo Exemplo de execução: ./script. O ponto indica o diretório atual, para executar um comando e o resultado sair na mesma linha do comando echo coloca-se o -n.
#!bin/bash
echo -n "Diretório atual: "
pwd

### Usando variáveis
#!/bin/bash
# Script que mostra nome usuário que está estudando shell
frase = "está estudando shell"
echo "$USER $frase"
