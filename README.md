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

6. Sincronização de Conteúdo entre Branches
Aprendemos como mover arquivos de uma ramificação para outra localmente antes de enviar para a nuvem.

git merge master: Estando na branch main, este comando trouxe todo o conteúdo atualizado da master para a main.

Fast-forward: Quando uma branch está puramente "atrás" da outra, o Git apenas move o ponteiro para frente, alinhando as duas histórias instantaneamente.

7. Renomeando e Limpando o Repositório
Para manter o projeto organizado e com nomes personalizados, realizamos a renomeação de branches tanto no ambiente local quanto no remoto (GitHub).

git branch -m master desenvolvimento1: Renomeia a branch local de master para desenvolvimento1.

git push origin desenvolvimento1: Cria a nova branch com o nome atualizado no GitHub.

git push origin --delete master: Deleta a branch com o nome antigo no servidor remoto.

git branch -d master: Deleta a branch antiga localmente (modo seguro).

8. Comandos de Verificação e Navegação
git branch: Lista todas as branches locais. O asterisco (*) indica em qual você está "pisando".

git branch -a: Lista todas as branches (locais e as que existem no GitHub).

git checkout <nome>: Alterna entre as ramificações existentes.

9. O Arquivo .gitignore
Aprendemos como dizer ao Git para ignorar arquivos ou pastas específicas que não devem ser versionados (como senhas, arquivos de configuração local ou pastas pesadas de bibliotecas).

touch .gitignore: Cria o arquivo de configuração (deve estar na raiz do projeto).

Funcionamento: Qualquer nome de arquivo ou padrão de pasta escrito dentro dele será ignorado pelo comando git status.

Exemplos Comuns:

node_modules/ (Pastas de dependências de projetos Node.js/React).

.env (Arquivos com chaves secretas e senhas de banco de dados).

*.log (Arquivos de log gerados pelo sistema).

10. Ciclo de Vida do .gitignore
Um ponto crucial que aprendemos é que o próprio arquivo .gitignore precisa ser rastreado pelo Git.

Criar o .gitignore.

Adicionar as regras de exclusão dentro dele.

Executar git add .gitignore.

Executar git commit -m "Configura regras de exclusão".

Nota de Segurança: Se um arquivo já foi "comitado" uma vez, adicioná-lo ao .gitignore depois não fará o Git parar de rastreá-lo automaticamente. É preciso remover o arquivo do cache do Git primeiro.