# Markdown com diagramas do Mermaid JS no MkDocs

[![asciicast](https://asciinema.org/a/716342.svg)](https://asciinema.org/a/716342)

1. Vamos criar um diretório chamado `arco`:

   - mkdir -v arco
   - cd arco


4. Dentro deste diretório, criaremos o arquivo `requirements.txt`:

   - touch requirements.txt
   - micro requirements.txt

   (Ctr+S: Salvar; Ctrl+Q: Sair)
	
5. Criaremos um ambiente virtual do Python (`venv`)

   - apt install -y python3-venv
   - python3 -m venv .venv
	
6. Ativaremos o novo ambiente virtual

   - source .venv/bin/activate

7. Instalaremos os requisitos

   - pip install -r requirements.txt

8. Criação do projeto no diretório atual (`.`)

   - mkdocs new .

9. Edição do arquivo de configuração do projeto

   - micro mkdocs.yml

10. Habilitação do servidor HTTP

   - systemctl enable --now apache2.service

11. Verificação das portas abertas do protocolo TCP

    - ss -tl
    - ss -tnl

12. Vamos limpar e editar a página inicial

    - echo > docs/index.md
    - micro docs/index.md

13. Insira diagramas, gere sua documentação e visite o site

    - mkdocs build
    - Visite: <http://192.168.56.77>

## Publicação da documentação no GitHub pages

Precisaremos do pacote `gh`

Uso básico do gh:

1. Autenticação

   - gh auth login

2. Criação de repositório

   - gh repo create arco -d "Arq. de Red. de COmp." --add-readme -g Python --public

3. Iniciar um repositório do git no diretório atual e 
renomear branch para `main`

   - git init .
   - git branch -m main

3. Adicionar o repositório remoto ao diretório atual	

```
git remote -v
git remote add origin https://github.com/USUARIO/arco.git
				    \_____/
				     O seu
git remote -v	                                        
```

4. Vamos trazer as mudanças do repo remoto e mesclá-la no repo local

```
git fetch
git pull origin main
```

5. Vamos ver as alterações que devem ser registradas

```
git status
git add .
```

6. Vamos verificar as configurações do usuário

```
git config --global user.name
git config --global user.email

git config --global user.name 'Fulano de Tal'
git config --global user.email 'fulano.tal@info.lab'

git config --global user.name
git config --global user.email
```

7. Vamos registrar as mudanças

```
git commit -m 'Demonstração de diagramas do Mermaid JS'
```

8. Enviar as mudanças para o repositório remoto

   - git push origin main
  
9. Publicar página no GitHub Pages

   - mkdocs gh-deploy
  

