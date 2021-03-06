# Seu primeiro projeto Django!

Nós vamos criar um blog simples!

O primeiro passo é iniciar um novo projeto Django. Basicamente, isso significa que devemos rodar alguns scripts providos pelo Django que vão criar um esqueleto de projeto Django para nós. O resultado é um conjunto de diretórios e arquivos que nós iremos utilizar e modificar mais tarde.

Os nomes de alguns arquivos e diretórios são muito importantes para o Django. Você não deve renomear os arquivos que estamos prestes a criar. Mover para um lugar diferente também não é uma boa idéia. O Django precisa manter uma certa estrutura para conseguir encontrar algumas coisas importantes.

<!--sec data-title="Create project: Windows" data-id="django_start_project_windows" data-collapse=true ces-->

No seu terminal, rode o seguinte comando (**não esqueça de adicionar o ponto `.` no final!**):

{% filename %}command-line{% endfilename %}

    ~/djangogirls$ django-admin startproject mysite .


> O ponto `.` é crucial por que ele diz para o script instalar o Django no diretório atual (o ponto `.` é um atalho para referenciar este diretório).
>

<!--endsec-->

`django-admin` é um script que criará os diretórios e arquivos para você. Agora, você deve ter uma estrutura de diretório parecida com isso:

    djangogirls
    ├───manage.py
    ├───mysite
    │        settings.py
    │        urls.py
    │        wsgi.py
    │        __init__.py
    └───requirements.txt


> **Dica:** Para visualizar os arquivos de uma pasta em seu terminal digite `ls` no Linux/Ubuntu ou `dir` no Windows.

`manage.py` é um script que ajuda com a gestão do site. Com ele, podemos iniciar um servidor de web no nosso computador sem instalar nada, entre outras coisas.

O arquivo `settings.py` contém a configuração do seu site.

Lembra de quando falamos sobre um carteiro verificando onde entregar uma carta? O arquivo `urls.py` contém uma lista dos padrões usados por `urlresolver`.

Vamos ignorar os outros arquivos por enquanto pois não vamos modificá-los. Só precisamos lembrar de não excluí-los acidentalmente!

## Mudando as configurações

Vamos fazer algumas alterações no `mysite/settings.py`. Abra o arquivo usando o editor de código que você instalou anteriormente.

**Observação:** Lembre-se de que o `settings.py` é um arquivo comum, como qualquer outro. Você pode abri-lo de dentro do editor de código usando as ações de menu "Arquivo-> Abrir". Assim, você deve encontrá-lo na janela usual para selecionar arquivos e abri-lo. Ou então, é possível abrir o arquivo navegando até o diretório do djangogirls e abrindo o arquivo com o botão direito. Uma vez clicado, selecione o seu editor de código preferido da lista. Selecionar o editor apropriado é importante uma vez que você pode ter outros programas instalados que podem abrir o arquivo, mas não editá-lo.

Para começar, seria bom ter a hora correta no nosso site. Para isto, você configurar o fuso horário correto de onde está. Se você estiver no Brasil, é bem provável que o fuso horário seja `America/Sao_Paulo` (aqui conhecido como horário de Brasília). Caso queira saber mais, vá para [Wikipedia's list of time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) e copie e cole o fuso horário correspondende à sua localização.

Em `settings.py`, localize a linha que contém `TIME_ZONE` e modifique para escolher seu próprio fuso horário:

{% filename %}mysite/settings.py{% endfilename %}

```python
TIME_ZONE = 'America/Sao_Paulo'
```

Um código de idioma se refere à língua, por exemplo, `en` para inglês ou `pt` para português e o código do país, por exemplo, `br` para Brasil ou `pt` para a Portugal. Já que o inglês provavelmente não é sua língua nativa, você pode pode adicionar um novo código de país para deixar os botões padrão e notificações de Django em seu idioma. Assim, você teria por exemplo um botão "Cancel" traduzido para a língua da sua escolha (ex: "Cancelar" em português). O [Django vem com um monte de traduções já preparadas](https://docs.djangoproject.com/en/2.0/ref/settings/#language-code).

Se você quiser um idioma diferente do inglês, especifique o código de idioma alterando a seguinte linha:

{% filename %}mysite/settings.py{% endfilename %}

```python
LANGUAGE_CODE = 'pt-BR'
```

Também precisamos adicionar o caminho para os arquivos estáticos. (Discutiremos tudo sobre arquivos estáticos e CSS mais adiante no tutorial.) Vá até o *final* do arquivo e, logo abaixo da linha com `STATIC_URL`, adicione uma nova variável chamada `STATIC_ROOT`:

{% filename %}mysite/settings.py{% endfilename %}

```python
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
```

<!--Quando `DEBUG` for `True` e `ALLOWED_HOSTS` estiver vazia, o domínio do site será validado como `['localhost', '127.0.0.1', '[::1]']`. Isso não corresponderá ao nosso domínio no PythonAnywhere quando implantarmos a nossa aplicação, então vamos mudamos a seguinte configuração:-->

<!--{% filename %}mysite/settings.py{% endfilename %}-->

<!--```python
ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']
```-->

## Configurando um banco de dados

Existem vários softwares de banco de dados diferentes que podem armazenar dados para o seu site. Nós vamos usar o padrão do Django, o `sqlite3`.

Isto já está configurado nesta parte do seu arquivo `mysite/settings.py`:

{% filename %}mysite/settings.py{% endfilename %}

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```

Para criar um banco de dados para o nosso blog, vamos executar o seguinte comando no terminal. Digite: `python3 manage.py migrate` (precisamos estar no diretório que contém o arquivo `manage.py` `djangogirls`). Se isso der certo, você deve ver algo assim:

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ python3 manage.py migrate
    Operations to perform:
      Apply all migrations: auth, admin, contenttypes, sessions
    Running migrations:
      Rendering model states... DONE
      Applying contenttypes.0001_initial... OK
      Applying auth.0001_initial... OK
      Applying admin.0001_initial... OK
      Applying admin.0002_logentry_remove_auto_add... OK
      Applying contenttypes.0002_remove_content_type_name... OK
      Applying auth.0002_alter_permission_name_max_length... OK
      Applying auth.0003_alter_user_email_max_length... OK
      Applying auth.0004_alter_user_username_opts... OK
      Applying auth.0005_alter_user_last_login_null... OK
      Applying auth.0006_require_contenttypes_0002... OK
      Applying auth.0007_alter_validators_add_error_messages... OK
      Applying sessions.0001_initial... OK


Pronto! Hora de iniciar o servidor web e ver se nosso site está funcionando!

## Iniciando o servidor web

Você precisa estar no diretório que contém o arquivo `manage.py` (o diretório `djangogirls`). No terminal, nós podemos iniciar o servidor web executando o `python3 manage.py runserver`:

{% filename %}command-line{% endfilename %}

    ~/djangogirls$ python3 manage.py runserver


Se você estiver no Windows e o comando falhar com `UnicodeDecodeError`, use o comando alternativo:

{% filename %}command-line{% endfilename %}

    ~/djangogirls$ python manage.py runserver 0:8000


Agora, precisamos verificar se o nosso site está rodando. Abra seu browser (Firefox, Chrome, Safari, Internet Explorer ou qualquer outro que você utilizar) e digite o endereço:

{% filename %}browser{% endfilename %}

    http://127.0.0.1:8000/


Parabéns! Você criou seu primeiro site e o executou usando um servidor web! Não é impressionante?

![Instalação funcionou!](images/install_worked.png)

Enquanto o servidor estiver rodando, o prompt do terminal não estará disponível para receber novos comandos. Na realidade, o terminal permite que você escreva texto, mas não irá executar nenhum comando. Isto acontece porque o servidor bloqueia o terminal enquanto ele mesmo recebe novos comandos.

Para escrever novos comandos enquanto o servidor estiver rodando, abra uma nova janela do terminal. Para interromper o seu servidor, volte para a janela onde ele está rodando e pressione CTRL + C -- botões Control e C juntos (no Windows; tente Ctrl+Break se o primeiro não funcionar).

Pronta para o próximo passo? Está na hora de criar conteúdo!
