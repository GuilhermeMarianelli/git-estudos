# git-estudos

Guia de Estudo: Primeiros Passos com Git e GitHub
Este repositório foi criado para praticar os fundamentos do controle de versão, desde a inicialização local até a sincronização com o servidor remoto.

1. Infraestrutura e Inicialização
O primeiro passo foi preparar a pasta local para ser monitorada pelo Git.

git init: Inicializa o repositório local, criando a pasta oculta .git.

ls -a: Comando Linux para listar todos os arquivos, incluindo os ocultos (como o .git).

2. O Ciclo de Trabalho (As 3 Áreas)
Aprendemos que o Git não salva tudo automaticamente; ele precisa de instruções claras.

touch tarefas.txt: Cria um novo arquivo via terminal.

git status: O comando mais importante para ver em qual das 3 áreas (Working Directory, Staging ou Repository) seus arquivos estão.

git add tarefas.txt: Move o arquivo da Área de Trabalho para a Staging Area (preparação).

git commit -m "mensagem": Tira um "snapshot - foto" dos arquivos que estavam na Staging Area e os guarda permanentemente no Repositório Local.

3. Conexão com o Repositório Remoto
Conectamos o nosso computador ao servidor do GitHub para garantir que o código tenha um backup na nuvem.

git remote add origin <URL>: Apresenta o servidor (GitHub) ao seu computador sob o apelido de "origin".

git remote -v: Verifica se a conexão foi feita corretamente.

4. Sincronização e Resolução de Históricos Divergentes
Como o repositório remoto foi criado com um arquivo (README.md) e o local com outro (tarefas.txt) de forma independente, precisamos unir as histórias.

git config pull.rebase false: (mesclagem) Define que, ao baixar arquivos, o Git deve tentar uma mesclagem (merge) padrão.

git pull origin main --allow-unrelated-histories: O comando crucial que baixa os arquivos do GitHub e força a união de dois históricos que não tinham uma origem comum.

git push origin main: Faz o "upload" dos arquivos e do histórico unificado do seu PC para o GitHub.

5. Organização em Ramificações (Branches)
Criamos "universos paralelos" para trabalhar em diferentes partes do projeto sem afetar a linha principal (main).

git branch <nome>: Cria uma nova ramificação.

git checkout <nome> (ou git switch): Alterna entre as ramificações.

git branch: Lista todas as ramificações existentes.
