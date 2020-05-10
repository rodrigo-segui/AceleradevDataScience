# Tutorial de como fazer deploy de sua aplicação streamlit no heroku
Tutorial desenvolvido durante aprendizado de realizar o deploy de uma aplicaçao streamlit no heroku


<p align="center">
  <a href="#tecnologias">Tecnologias</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#tutorial">Tutorial</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
</p>

### Tecnologias

Esse tutorial foi desenvolvido com as seguintes tecnologias:

- [Streamlit](https://www.streamlit.io/)
- [Heroku](https://www.heroku.com/)

### Tutorial

###  1. construir aplicação streamlit: 
    Exemplo: ./Tutorial.py

###  2. requirements.txt:

instale a lib pipreqs para gerar o arquivo requirements.txt
```bash
$ pip install pipreqs
```
no diretório do projeto para criar o arquivo requirements.txt digite: 
```bash
$ pipreqs ./
```

###  3. setup.sh : crie o arquivo com o modelo, substituindo-o pelo seu email:
    mkdir -p ~/.streamlit/

    echo "\
    [general]\n\
    email = \"seu-email@dominio.com\"\n\
    " > ~/.streamlit/credentials.toml
    echo "\
    [server]\n\
    headless = true\n\
    enableCORS=false\n\
    port = $PORT\n\
    " > ~/.streamlit/config.toml
      
###  4. Procfile: crie o arquivo com as seguintes configurações:

    web: sh setup.sh && streamlit run Tutorial.py

###  5. [Crie uma conta no Heroku](https://www.heroku.com/)
 
###  6. [instale o (CLI Heroku Command line Interface)](https://devcenter.heroku.com/articles/getting-started-with-python#set-up)

###  7. Configure o heroku:
```bash
$ heroku login
```
```bash
$ heroku create <nome_projeto>
```
### 8. Configure git:
```bash
$ git init
```
```bash
$ git status
```
```bash
$ git add .
```
```bash
$ git commit -m "some message"
```
```bash
$ git push heroku master
```



