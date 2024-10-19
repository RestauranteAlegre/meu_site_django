1. Estrutura do Projeto
Criação da Pasta do Projeto
Crie uma pasta para o projeto:
bash

Verify

Open In Editor
Edit
Copy code
mkdir meu_site_django
cd meu_site_django
2. Configuração do Ambiente
Instalação do Poetry
Instale o Poetry, que é uma ferramenta de gerenciamento de dependências e ambientes virtuais para Python:
bash

Verify

Open In Editor
Edit
Copy code
curl -sSL https://install.python-poetry.org | python3 -
Criação do Ambiente Virtual
Crie um novo projeto com o Poetry:
bash

Verify

Open In Editor
Edit
Copy code
poetry new meu_site
cd meu_site
Ativação do Ambiente Virtual
Ative o ambiente virtual criado pelo Poetry:
bash

Verify

Open In Editor
Edit
Copy code
poetry shell
3. Instalação do Django
Instale o Django usando o Poetry:
bash

Verify

Open In Editor
Edit
Copy code
poetry add django
4. Criação do Projeto Django
Crie um novo projeto Django:
bash

Verify

Open In Editor
Edit
Copy code
django-admin startproject meu_site_django .
5. Estrutura Básica do Projeto
A estrutura do projeto deve ser semelhante a:

Verify

Open In Editor
Edit
Copy code
meu_site/
├── meu_site/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
├── manage.py
└── ...
6. Criação de um Aplicativo Django
Crie um novo aplicativo dentro do seu projeto:
bash

Verify

Open In Editor
Edit
Copy code
python manage.py startapp meu_app
7. Configuração do Banco de Dados
Configure o banco de dados no arquivo settings.py do Django. Por exemplo, para usar SQLite (padrão):
python

Verify

Open In Editor
Edit
Copy code
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / "db.sqlite3",
    }
}
8. Instalação de HTML, CSS e JavaScript
Crie uma pasta chamada static e templates dentro do seu aplicativo para armazenar arquivos estáticos e templates HTML:

Verify

Open In Editor
Edit
Copy code
meu_app/
├── static/
├── templates/
9. Exemplo de Template HTML
Crie um arquivo index.html dentro da pasta templates:
html

Verify

Open In Editor
Edit
Run
Copy code
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Site Django</title>
    <link rel="stylesheet" href="{% static 'styles.css' %}">
</head>
<body>
    <h1>Bem-vindo ao meu site!</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
</body>
</html>
10. Adicionando Estilos com CSS
Crie um arquivo styles.css dentro da pasta static:
css

Verify

Open In Editor
Edit
Copy code
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    color: #333;
}
11. Configuração de URLs
No arquivo urls.py, adicione uma rota para renderizar o template:
python

Verify

Open In Editor
Edit
Copy code
from django.urls import path
from .views import index

urlpatterns = [
    path('', index, name='index'),
]
12. Criando a View
No arquivo views.py, crie uma view para renderizar o template:
python

Verify

Open In Editor
Edit
Copy code
from django.shortcuts import render

def index(request):
    return render(request, 'index.html')
13. Rodando o Servidor
Finalmente, rode o servidor de desenvolvimento do Django:
bash

Verify

Open In Editor
Edit
Copy code
python manage.py runserver
Conclusão
Com este plano de estudo, você terá uma base sólida para criar um site utilizando Django, HTML, CSS e JavaScript. Você pode expandir este projeto adicionando mais funcionalidades, como autenticação de usuários, integração com APIs, entre outros.

Se precisar de mais detalhes sobre algum passo específico ou tiver outras perguntas, sinta-se à vontade para perguntar!
