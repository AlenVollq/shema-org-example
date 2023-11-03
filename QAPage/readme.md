# QAPage

Страница вопросов и ответов содержит вопрос, после которого перечислены ответы на него.
> Если посетители сайта могут добавлять ответы на вопрос, опубликованный на отдельной странице.

- [schema.org](https://schema.org/QAPage)
- [google](https://developers.google.com/search/docs/appearance/structured-data/qapage)
- [yandex](https://yandex.ru/support/webmaster/supported-schemas/q-and-a.html)

|itemprop| type| required |description|
| -- | -- |--------| -- |
|[https://schema.org/QAPage](https://schema.org/QAPage)||        ||
|`mainEntity`|Question | *      |Массив элементов|
|[https://schema.org/Question](https://schema.org/Question)||        ||
|`acceptedAnswer/suggestedAnswer`|Answer| *      |acceptedAnswer - Лучший ответ на вопрос. suggestedAnswer - Один возможный ответ, не принятый в качестве лучшего|
|`name`|Text| *      |Весь текст краткой формы вопроса|
|`answerCount`|Integer| *      |Общее количество ответов на вопрос. Например, если всего ответов 15, но из-за разбивки на страницы показываются лишь 10, то значение будет равно 15. Если ответов вообще нет, оно будет равно 0|
|`upvoteCount`|Integer|        |Общее количество голосов, которые получил вопрос. Если на странице поддерживаются голоса за и против, то для свойства upvoteCount следует указать одно общее среднее значение. Например, если ответ получил 5 голосов за и 2 – против, то общее значение upvoteCount составит 3. Если ответ получил 5 голосов за, а голоса против не принимаются, то значение upvoteCount будет равно 5|
|`text`|Text|        |Весь текст вопроса в полной форме|
|[https://schema.org/Answer](https://schema.org/Answer)||        ||
|`text`|Text| *      |Весь текст ответа|
|`upvoteCount`|Integer|        |Общее количество голосов, которые получил ответ|
|`url`|URL|        |URL прямой ссылки на ответ|

## Microdata

```html
<section itemscope itemtype="https://schema.org/QAPage">
  <div itemprop="mainEntity" itemscope itemtype="https://schema.org/Question">
    <h2 itemprop="name">How long does it take for Google to index a new website?</h2>
    <p itemprop="text">Here I want to know how much time google taken any new website indexing. And also know what do when any new web/landing page was not index in long time.</p>
    <div itemprop="answerCount">2</div>
    <div itemprop="upvoteCount">10</div>

    <!-- Item -->
    <div itemprop="acceptedAnswer" itemscope itemtype="https://schema.org/Answer">
      <div itemprop="upvoteCount">12</div>
      <div itemprop="text">Google can index your website as soon as Google crawlers can find your website. Make sure you have webmaster account with sitemap submitted and your website has been linked with multiple other websites so that crawlers have multiple routes to find your new website. This whole process of indexation can take about an hour to several weeks depending upon how you make crawlers journey to find your website easy.</div>
    </div>

    <!-- Item -->
    <div itemprop="suggestedAnswer" itemscope itemtype="https://schema.org/Answer">
      <div itemprop="upvoteCount">0</div>
      <div itemprop="text">Anywhere between a few minutes and frankly never. Pages may or may not be indexed. How long it takes for them to be 'discovered' is undefined, as is if Google thinks they ware worth indexing. And if worth indexing how long that will take.</div>
      <a itemprop="url" href="https://example.com/question#suggestedAnswer">Answer Link</a>
    </div>
  </div>
</section>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "QAPage",
    "mainEntity": {
      "@type": "Question",
      "name": "How long does it take for Google to index a new website?",
      "text": "Here I want to know how much time google taken any new website indexing. And also know what do when any new web/landing page was not index in long time.",
      "answerCount": 2,
      "upvoteCount": 10,
      "acceptedAnswer": {
        "@type": "Answer",
        "upvoteCount": 12,
        "text": "Google can index your website as soon as Google crawlers can find your website. Make sure you have webmaster account with sitemap submitted and your website has been linked with multiple other websites so that crawlers have multiple routes to find your new website. This whole process of indexation can take about an hour to several weeks depending upon how you make crawlers journey to find your website easy."
      },
      "suggestedAnswer": [
        {
          "@type": "Answer",
          "upvoteCount": 0,
          "text": "Anywhere between a few minutes and frankly never. Pages may or may not be indexed. How long it takes for them to be 'discovered' is undefined, as is if Google thinks they ware worth indexing. And if worth indexing how long that will take.",
          "url": "https://example.com/question#suggestedAnswer"
        }
      ]
    }
  }
</script>
```