# 便签

在 markdown 中加入如下的代码来使用便签：

```django
{% note success %}
文字 或者 `markdown` 均可
{% endnote %}
```

或者使用 HTML 形式：

```html
<p class="note note-primary">标签</p>
```

> 一般采用上面的那种形式

```django
{% note primary %}
primary
{% endnote %}

{% note secondary %}
secondary
{% endnote %}

{% note success %}
success
{% endnote %}

{% note danger %}
danger
{% endnote %}

{% note warning %}
warning
{% endnote %}

{% note info %}
info
{% endnote %}
```

> 使用这些`{% note primary %}`和`{% endnote %}`需要单独一行

{% note primary %}
primary
{% endnote %}

{% note secondary %}
secondary
{% endnote %}

{% note success %}
success
{% endnote %}

{% note danger %}
danger
{% endnote %}

{% note warning %}
warning
{% endnote %}

{% note info %}
info
{% endnote %}

# 行内标签

在 markdown 中加入如下的代码来使用 Label：

```django
{% label primary @text %}
```

或者使用 HTML 形式：

```html
<span class="label label-primary">Label</span>
```

可选 Label：

{% label primary @标签 %}

{% label default @标签 %}

{% label info @标签 %}

{% label success @标签 %}

{% label warning @标签 %}

{% label danger @标签 %}

