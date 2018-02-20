На данной странице находится описание по работе с метрикой сервиса Qiberty. Она работает в схожей манере с Google.Analytics и Яндекс.Метрикой, но имеет свои отличия. На данный момент, использование возможно в 2 вариантах:
1. Через JS-скрипт
2. Через REST API

## Начало работы
Для начала работы вам необходимо будет создать счетчик и получить его идентефикатор.


## Использование через JS-скрипт
Для работы с метрикой Qiberty можно использовать реализованный нами JS-скрипт. Ниже приводится описание того, как реализовать этот вариант на вашем сайте.

### 1. Размещение счетчика Qiberty на сайте
Первым делом необходимо разместить данный JS код в блоке `<head>...</head>` на всех страницах вашего сайта:
```js
<!-- Qiberty counter -->
<script type="text/javascript" async>
  (function (d, w) {
    var ts = d.createElement("script"); ts.type = "text/javascript"; ts.async = true;
    ts.src = "//metrics.qiberty.com/js/counter.js";
    var f = function () {var s = d.getElementsByTagName("script")[0]; s.parentNode.insertBefore(ts, s);};
    if (w.opera == "[object Opera]") { d.addEventListener("DOMContentLoaded", f, false); } else { f(); }
  })(document, window);
  window.onload = function() {
    window.qiberty_visit(counter_id);
  }
</script>
<!-- /Qiberty counter -->
```
Данный код делает 2 вещи
1. Он подключает методы из реализованного JS-скрипта, и теперь вы можете вызывать их в коде страницы.
2. При посещении страницы, он регистрирует посещение и регистирует в системе метрик Qiberty.

**Заметьте,** что вместо `counter_id` вам необходимо подставить идентефикатор счетчика, полученный при его создании.



## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/zydins/qiberty-metrics/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/zydins/qiberty-metrics/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
