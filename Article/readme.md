# Article

Статья.\
[NewsArticle](https://schema.org/NewsArticle) - новостная статья.\
[BlogPosting](https://schema.org/BlogPosting) - статья в блоге.

- [schema.org](https://schema.org/BreadcrumbList)
- [google](https://developers.google.com/search/docs/appearance/structured-data/article)
- yandex - нет

|itemprop| type| required | description                                               |
| -- | - |----------|-----------------------------------------------------------|
|[https://schema.org/NewsArticle](https://schema.org/NewsArticle)||          |                                                           |
|`headline`|Text|          |Заголовок статьи                                           |
|`image`|ImageObject или URL|          |Ссылка на изображение                                      |
|`datePublished`|DateTime|          |Дата и время первой публикации, указанные в формате ISO 8601 |
|`dateModified`|DateTime|          |Время и дата последних изменений, указанные в формате ISO 8601 |
|`articleBody`|Text|          |Текст статьи                                               |
|`author`|Person или Organization|          |Автор статьи                                               |
|[https://schema.org/Person](https://schema.org/Person)||          |                                                           |
|`name`|Text|          |Имя автора                                              |
|`url`|URL|          |Ссылка на веб-страницу, посвященную автору данной статьи                                              |
## Microdata

```html
<div itemscope itemtype="https://schema.org/NewsArticle">
  <h1 itemprop="headline">Title</h1>
  <meta itemprop="image" content="https://example.ru/image/image.jpg" />
    <span itemprop="datePublished" content="2023-02-05T08:00:00+08:00">05.02.2023</span>
    <span itemprop="dateModified" content="2023-11-09T08:00:00+08:00">Last modified: 09.11.2023</span>
    <span itemprop="author" itemscope itemtype="https://schema.org/Person">
      <a itemprop="url" href="https://example.ru/johndoe">
        <span itemprop="name">John Doe</span>
      </a>
    </span>
  <div itemprop="articleBody">Article body</div>
</div>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "NewsArticle",
    "headline": "Title",
    "image": "https://example.ru/image/image.jpg",
    "datePublished": "2023-02-05T08:00:00+08:00",
    "dateModified": "2023-11-09T08:00:00+08:00",
    "author": [{
      "@type": "Person",
      "name": "John Doe",
      "url": "https://example.ru/johndoe"
    }],
    "articleBody": "Article body"
  }
</script>
```