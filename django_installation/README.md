# Instalação do Django

Para este tutorial, usaremos um novo diretório `djangogirls` no seu diretório home:

{% filename %}command-line{% endfilename %}

    $ mkdir djangogirls
    $ cd djangogirls

## Instalando o Django

Primeiro, instale o pip. Quando pedir a senha, digite `set01linf`. Sua senha não vai aparecer, e está correto! Se houver dúvidas, chame uma treinadora.

{% filename %}command-line{% endfilename %}

    ~$ sudo apt install python3-pip

Após, atualize o pip:

<!-- Antes de fazer isto, devemos garantir que temos instalada a última versão do `pip`, que é o software que usamos para instalar o Django: -->

<!--sec data-title="Lembrete Python" data-id="lembrete_python"
data-collapse=true ces-->

Lembre-se: se estiver utilizando Linux/Ubuntu o comando deve ser `python3`. Em Windows utiliza-se `python`.

<!--endsec-->

<!-- {% filename %}command-line{% endfilename %} -->

    ~$ sudo python3 -m pip install --upgrade pip

Agora, digite o seguinte comando para realizar a instalação do Django.

{% filename %}command-line{% endfilename %}

    sudo python3 -m pip install Django==2.0

Você verá a seguinte mensagem na tela.

{% filename %}command-line{% endfilename %}

    ~$ python3 -m pip install Django~=2.2
    Collecting Django~=2.2
      Downloading Django-2.2-py3-none-any.whl (7.1MB)
    Installing collected packages: Django
    Successfully installed Django-2.2


<!--sec data-title="Installing Django: Windows" data-id="django_err_windows"
data-collapse=true ces-->

> Se você receber um erro ao chamar o pip na plataforma Windows, verifique se o caminho do projeto contém espaços, acentos ou caracteres especiais (exemplo, `C:\Users\User Name\djangogirls`). Se sim, considere movê-lo para outro lugar sem espaços, acentos ou caracteres especiais (sugestão: `C:\djangogirls`).

<!--endsec-->

É isto! Você agora (finalmente) está pronta para criar uma aplicação Django!
