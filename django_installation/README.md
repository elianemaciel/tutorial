# Instalação do Django

Para este tutorial, usaremos um novo diretório `djangogirls` no seu diretório home:

{% filename %}command-line{% endfilename %}

    $ mkdir djangogirls
    $ cd djangogirls

## Instalando o Django

Antes de fazer isto, devemos garantir que temos instalada a última versão do `pip`, que é o software que usamos para instalar o Django:

{% filename %}command-line{% endfilename %}

    ~$ python3 -m pip install --upgrade pip


### Instalando pacotes com requisitos

O arquivo "requirements.txt" guarda as depenências que serão instaladas utilizando o `pip install`:

Procure em seu computador o programa `Gedit`. Este programa é um editor de texto, ele vai te ajudar a criar todos os seus códigos!

<!--Primeiramente, crie um arquivo `requirements.txt` dentro da pasta `djangogirls/`:-->

<!--
    djangogirls
    └───requirements.txt
-->

<!--E adicione o seguinte texto ao arquivo `djangogirls/requirements.txt`:-->

Na tela em branco, adicione o seguinte texto:

{% filename %}djangogirls/requirements.txt{% endfilename %}

    Django~=2.2


E salve o arquivo com o nome `requirements.txt` dentro da pasta `djangogirls/`.

Agora, no terminal execute `pip install -r requirements.txt` para instalar o Django.

{% filename %}command-line{% endfilename %}

    ~$ pip install -r requirements.txt
    Collecting Django~=2.2 (from -r requirements.txt (line 1))
      Downloading Django-2.2-py3-none-any.whl (7.1MB)
    Installing collected packages: Django
    Successfully installed Django-2.2


<!--sec data-title="Installing Django: Windows" data-id="django_err_windows"
data-collapse=true ces-->

> Se você receber um erro ao chamar o pip na plataforma Windows, verifique se o caminho do projeto contém espaços, acentos ou caracteres especiais (exemplo, `C:\Users\User Name\djangogirls`). Se sim, considere movê-lo para outro lugar sem espaços, acentos ou caracteres especiais (sugestão: `C:\djangogirls`).

<!--endsec-->

<!--sec data-title="Installing Django: Windows 8 and Windows 10" data-id="django_err_windows8and10"
data-collapse=true ces-->

> Sua linha de comando pode congelar depois de você tentar instalar o Django. Neste caso, ao invés do comando acima, use:
>
> {% filename %}command-line{% endfilename %}
>
>     C:\Users\Name\djangogirls> python -m pip install -r requirements.txt
>     

<!--endsec-->

É isto! Você agora (finalmente) está pronta para criar uma aplicação Django!
