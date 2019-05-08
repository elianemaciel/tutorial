## Ambiente virtual

Antes de instalar o Django, vamos instalar uma ferramenta muito útil para ajudar a manter o ambiente de trabalho no nosso computador organizado. Você pode pular esse passo, mas ele é altamente recomendado. Começar com a melhor instalação possível poupará você de muito trabalho no futuro!

Vamos criar um **ambiente virtual** (também chamado um *virtualenv*). O virtualenv isolará seu código Python/Django em um ambiente organizado por projetos. Isso significa que as alterações que você fizer em um website não afetarão os outros projetos que você estiver desenvolvendo ao mesmo tempo. Legal, né?

Tudo o que você precisa fazer é encontrar o diretório em que você quer criar o `virtualenv`; seu diretório Home, por exemplo. No Windows, pode aparecer como `C:\Users\Name` (onde `Nome` é seu usuário de login).

> ** Observação:** No Windows, certifique-se de que esse diretório não contém palavras acentuadas ou caracteres especias; se o seu usuário contém caracteres acentuados, use um diretório diferente, por exemplo: ` C:\djangogirls`.

Para este tutorial, usaremos um novo diretório `djangogirls` no seu diretório home:

{% filename %}command-line{% endfilename %}

    $ mkdir djangogirls
    $ cd djangogirls

## Instalando o Django

Agora que você tem seu `virtualenv` ativo, pode instalar o Django.

Antes de fazer isto, devemos garantir que temos instalada a última versão do `pip`, que é o software que usamos para instalar o Django:

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ python3 -m pip install --upgrade pip


### Instalando pacotes com requisitos

O arquivo "requirements.txt" guarda as depenências que serão instaladas utilizando o `pip install`:

Primeiramente, crie um arquivo `requirements.txt` dentro da pasta `djangogirls/`:

    djangogirls
    └───requirements.txt


E adicione o seguinte texto ao arquivo `djangogirls/requirements.txt`:

{% filename %}djangogirls/requirements.txt{% endfilename %}

    Django~={{ book.django_version }}


Agora, execute `pip install -r requirements.txt` para instalar o Django.

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ pip install -r requirements.txt
    Collecting Django~={{ book.django_version }} (from -r requirements.txt (line 1))
      Downloading Django-{{ book.django_version }}-py3-none-any.whl (7.1MB)
    Installing collected packages: Django
    Successfully installed Django-{{ book.django_version }}


<!--sec data-title="Installing Django: Windows" data-id="django_err_windows"
data-collapse=true ces-->

> Se você receber um erro ao chamar o pip na plataforma Windows, verifique se o caminho do projeto contém espaços, acentos ou caracteres especiais (exemplo, `C:\Users\User Name\djangogirls`). Se sim, considere movê-lo para outro lugar sem espaços, acentos ou caracteres especiais (sugestão: `C:\djangogirls`). Crie um novo virtualenv no diretório recém-criado, exclua o mais velho e tente novamente executar o comando acima. (Mover o diretório de virtualenv não vai funcionar pois o virtualenv usa caminhos absolutos.)

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
