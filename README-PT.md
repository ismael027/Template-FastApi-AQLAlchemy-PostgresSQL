# CHAMELEON STACK - KANBAN

## Linguagens do README
- [English version](README.md)

### 📋 PRÉ-REQUISITOS

- Docker
- Python
- Pipenv

## 🔧 INSTALANDO PRÉ-REQUISITOS

### Instalando o Python

Acesse o seguinte link e baixe a versão LTS

```
    https://www.python.org/downloads/
```

Após isso é só clicar duas vezes no arquivo que foi baixado e instalar o Python clicando em next até sua instalação. Execute o seguinte comando em um terminal(cmd,gitbash ou outros) para verificar a versão:

```
    python --version
```

### Instalando o Pipenv

Execute o seguinte comando em um terminal(cmd,gitbash ou outros) e verifique a versão:

```
    pip install pipenv
```

```
    pipenv --version
```

### Instalando o Docker

O primeiro passo é configurar o docker. Para cada sistema operacional é necessário seguir um passo a passo:

- Linux

```
               https://docs.docker.com/desktop/install/linux-install/
```

- Windows (Necessário ter o WSL instalado e configurado)

```
               https://docs.docker.com/desktop/install/windows-install/
```

- MAC

```
               https://docs.docker.com/desktop/install/mac-install/
```

### Instalando o container que irá rodar no projeto

Para instalar o container que será rodado no projeto é necessário colocar o seguinte comando no terminal:

```
docker run --name postgres -e POSTGRES_PASSWORD=mypassword -p 5432:5432 -d postgres
```

#### Nessa etapa instale um SGBD e conecte com as credenciais do docker

## ⚙️ CONFIGURANDO O PROJETO

### Adicionando valores de conexão do banco ao config.toml

Conecte ao banco criado com as variáveis que você utilizou para criar a imagem do docker.
Crie um arquivo chamado "config.toml" na raiz do projeto e adicione as variáveis contidas no arquivo "example.config.toml" com o valor da url(postgres://username:password@localhost:5432/database_name) de conexão do banco de dados. O arquivo ".config.toml", de acordo com o que container criado, ficaria aproximadamente assim:

```
DATABASE_URI=postgres://postgres:mypassword@localhost:5432/chameleon
```

O SECRET_KEY pode ser gerado nesse link: https://djecrety.ir

### Instalando pacotes Pipenv

Rode o seguinte comando no projeto:

```
pipenv shell 
```

```
pipenv install 
```

### Iniciando o projeto

Rode os seguintes comandos no projeto:

```
uvicorn app:app --port 8080 --host 0.0.0.0
```