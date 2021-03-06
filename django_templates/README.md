# Templates do Django

Hora de exibir dados! O Django já vem com algumas **tags de template** que são úteis pra isso.

## O que são tags de template?

Sabe, em HTML não podemos incluir código Python porque os browsers só entendem HTML. Sabemos que o HTML é bem estático, enquanto o Python é muito mais dinâmico.

**Tags de template Django** nos permitem transformar código similar a Python em código HTML para que você possa construir sites dinâmicos mais rápido e mais facilmente. Legal!

## Templates para lista de posts

No capítulo anterior, fornecemos para o nosso template uma lista de postagens e a variável <o>posts</o>. Agora vamos exibi-las em HTML.

Pra mostrar uma variável em um template do Django, usamos chaves duplas com o nome da variável, assim:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{{ posts }}
```

Tente fazer isso no seu template `blog/templates/blog/post_list.html`. Substitua tudo desde o segundo `<div>` até o terceiro `</div>` por `{{ posts }}`. Salve o arquivo e atualize a página para ver o resultado:

![Figura 13.1](images/step1.png)

Como você pode ver, obtivemos apenas:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<QuerySet [<Post: My second post>, <Post: My first post>]>
```

Isto significa que o Django entende essa variável como uma lista de objetos. Em **Introdução ao Python** aprendemos como exibir listas, lembra? Sim, com laços "for"! Em um template do Django você pode criá-los assim:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% for post in posts %}
    {{ post }}
{% endfor %}
```

Tente fazer isso no seu template.

![Figura 13.2](images/step2.png)

Funciona! Mas nós queremos que eles sejam exibidos como os posts estáticos que criamos anteriormente no capítulo de **Introdução a HTML**. Nós podemos misturar HTML com tags de template. O conteúdo da tag `body` ficará assim:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div>
    <h1><a href="/">Django Girls Blog</a></h1>
</div>

{% for post in posts %}
    <div>
        <p>publicado em: {{ post.published_date }}</p>
        <h1><a href="">{{ post.title }}</a></h1>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endfor %}
```

{% raw %}Tudo o que você colocar entre `{% for %}` e `{% endfor %}` será repetido para cada objeto na lista. Atualize a página:{% endraw %}

![Figura 13.3](images/step3.png)

Você notou que dessa vez nós usamos uma notação um pouco diferente (`{{ post.title }}` ou `{{ post.text }}`)? Estamos acessando os dados em cada um dos campos que definimos no modelo do `Post`. Além disso, `|linebreaks` está passando o texto do post por um filtro, convertendo quebras de linha em parágrafos.

Parabéns!! Estamos orgulhosas! Afaste-se do seu computador um pouco, você merece uma pausa. :)

![Figura 13.4](images/donut.png)
