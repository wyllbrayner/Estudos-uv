# UV + Dev Containers com VS Code

Este projeto é uma extensão do projeto <a href="">Dev Containers com VS Code</a> e visa se utilizar dos conhecimentos obtidos em seus estudo para montar a estrutura deste projeto.

__obs:__ _Este projeto visa aprofundar os conhecimentos na utilização da ferramenta <a href="https://docs.astral.sh/uv/">uv</a> em um ambiente de desenvolvimento Linux._

# Procedimentos para utilização do uv em projeto python
## Instalar o uv
* Se possuir o pip instalado em seu ambiente, pode executar o comando __pip install uv__ em seu terminal.
* Caso prefira, pode utilizar o comando __curl -LsSf https://astral.sh/uv/install.sh | sh__ em seu terminal.

__obs:__ Para confirmar a correta instalação do uv, execute o comando __uv --version__ para identificar a versão instalada.

¹ Caso o terminal retorne algo como _uv 0.6.3_, a instalação foi realizada com sucesso.

² Caso o terminal retorne algo completamente diferente do exemplo acima, pode ser necessário inserir o caminho do uv ao PATH do Sistema Operacional com o comando __export PATH="$HOME/.local/bin:$PATH"__ no linux. Execute este comando e refaça o teste de versão descrito acima.

## Criar a estrutura de um novo projeto com uv
Execute o comando __uv init nome_projeto__ em seu terminal. Este comando criará nova pasta chamada _nome_projeto_ em seu diretório que conterá os seguintes arquivos iniciais:

* README.md 

    Arquivo README.md do projeto criado pelo uv.

* main.py

    Arquivo main para teste básico.

* pyproject.toml

    Arquivo contendo informações do projeto, tais como:
    
    (i) o nome do projeto;
    
    (ii) versão do python utilizada no projeto;
    
    (iii) a relação de dependências instaladas no projeto.

## Executar o programa
Execute o comando __uv run main.py__ em seu terminal. Este comando executará o programa presente no arquivo _main.py_.


__obs:__ A primeira vez que este comando for executado, o uv criará um novo arquivo e uma nova pasta, são eles:

* uv.lock (arquivo)

    Auxilia na definição das dependências instaladas do projeto.

* .venv (pasta)

    Ambiente virtual utilizado pelo uv para instalar as dependências do projeto e para executar o programa junto com suas dependências.

## Adicionar novas dependências ao projeto

Execute o comando __uv add nome_pacote__ no terminal.
    
    Este comando adicionará "nome_pacote" ao projeto e atualizará os arquivos pyproject.toml e uv.lock com suas dependências.

Execute o comando __uv add -r requirements.txt__ no terminal.
    
    Este comando adicionará todas os pacotes presentes no arquivo "requirements.txt" ao projeto uv.

## Remover dependências do projeto

Execute o comando __uv remove nome_pacote__ no terminal.

    Este comando removerá "nome_pacote" do projeto e atualizará os arquivos pyproject.toml e uv.lock.

## Sincronizar o ambiente com as dependências presentes nos arquivos de configuração

Execute o comando __uv sync__ no terminal.

    Este comando sincronizará o ambiente virtual com os pacotes e dependências presentes nos arquivos pyproject.toml e uv.lock.

    Este comando é útil quando adições e remoções de pacotes são realizadas diretamente nos arquivos de configuração e precisam ser atualizadas no ambiente de desenvolvimento.

## Listar as versões do Python disponíveis

Execute o comando __uv python list__ no terminal.

    Este comando listará todas as versões do python disponíveis em seu Sistema Operacional.

__obs:__ Execute __uv python install__, para instalar a versão mais atualizada disponível, ou __uv python install 3.12.0__, para instalar a versão 3.12.0 (exemplo) em seu projeto, ou execute __uv python install '>=3.9,<3.11'__, para instalar a versão disponível do python que atenda à restrição descrita.

## Criar arquivo requirements.txt a partir de um projeto uv

Execute o comando __uv export --format requirements-txt > requirements.txt__ no terminal.

    Criará novo arquivo requirements.txt com os pacotes e dependências instaladas no projeto.

## Limpar o cache do uv

Execute o comando __uv clean cache__ no terminal.
