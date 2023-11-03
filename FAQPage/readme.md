# FAQPage
Список часто задаваемых вопросов по определенной теме с ответами на них.
> Если на сайте опубликованы часто задаваемые вопросы, но пользователи не могут отправлять свои ответы в дополнение к имеющимся.

- [schema.org](https://schema.org/FAQPage)
- [google](https://developers.google.com/search/docs/appearance/structured-data/faqpage)
- yandex - не поддерживает

|itemprop| type|required|description|
| -- | -- | -- | -- |
|[https://schema.org/FAQPage](https://schema.org/FAQPage)||||
|`mainEntity`| Question |*| Массив элементов|
|[https://schema.org/Question](https://schema.org/Question)||||
|`acceptedAnswer`| Answer   | *|Ответ на вопрос|
|`name`|Text|*|Полный текст вопроса|
|[https://schema.org/Answer](https://schema.org/Answer)||||
|`text`|Text|*|Полный ответ на вопрос. Поддерживаемые html теги `<h1>–<h6>, <br>, <ol>, <ul>, <li>, <a>, <p>, <div>, <b>, <strong>, <i> и <em>`|

## Microdata

```html
<section itemscope itemtype="https://schema.org/FAQPage">
  <h2>FAQ</h2>

  <!--  Item -->
  <div itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
    <h3 itemprop="name">What is the purpose of schema.org?</h3>
    <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer" >
      <p itemprop="text">Schema.org is a joint effort, in the spirit of sitemaps.org, to improve the web by creating a structured data markup schema supported by major  search engines. On-page markup helps search engines understand the  information on web pages and provide richer search results. A shared  markup vocabulary makes easier for webmasters to decide on a markup  schema and get the maximum benefit for their efforts. Search engines  want to make it easier for people to find relevant information on the  web. Markup can also enable new tools and applications that make use of  the structure.</p>
    </div>
  </div>

  <!--  Item -->
  <div itemscope itemprop="mainEntity" itemtype="https://schema.org/Question">
    <h3 itemprop="name">Why are Google, Bing, Yandex and Yahoo! collaborating? Aren't you competitors?</h3>
    <div itemscope itemprop="acceptedAnswer" itemtype="https://schema.org/Answer">
      <p itemprop="text">Currently, there are many standards and schemas for marking up different types of information on web pages. As a result, it is difficult for webmasters to decide on the most relevant and supported markup standards to use. Creating a schema supported by all the major search engines makes it easier for webmasters to add markup, which makes it easier for search engines to create rich search features for users.</p>
    </div>
  </div>
</section>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity": [
      {
        "@type": "Question",
        "name": "What is the purpose of schema.org?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "Schema.org is a joint effort, in the spirit of sitemaps.org, to improve the web by creating a structured data markup schema supported by major search engines. On-page markup helps search engines understand the information on web pages and provide richer search results. A shared markup vocabulary makes easier for webmasters to decide on a markup schema and get the maximum benefit for their efforts. Search engines want to make it easier for people to find relevant information on the web. Markup can also enable new tools and applications that make use of the structure."
        }
      },
      {
        "@type": "Question",
        "name": "Why are Google, Bing, Yandex and Yahoo! collaborating? Aren't you competitors?",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "Currently, there are many standards and schemas for marking up different types of information on web pages. As a result, it is difficult for webmasters to decide on the most relevant and supported markup standards to use. Creating a schema supported by all the major search engines makes it easier for webmasters to add markup, which makes it easier for search engines to create rich search features for users."
        }
      }
    ]
  }
</script>
```