# Review

Отзыв или оценка с сайта.

- [schema.org](https://schema.org/Review)
- [google](https://developers.google.com/search/docs/appearance/structured-data/review-snippet)
- yandex - нет

|itemprop| type                                                                                                                                        | required |description|
| -- |---------------------------------------------------------------------------------------------------------------------------------------------|----------| -- |
|[https://schema.org/Review](https://schema.org/Review)|                                                                                                                                             |          ||
|`author`| Person или Organization                                                                                                                     | *        |Автор отзыва|
|`itemReviewed`| [Один из действительных типов](https://developers.google.com/search/docs/appearance/structured-data/review-snippet?hl=ru#review-properties) | *        |Элемент, к которому относятся отзывы|
|`reviewRating`| Rating                                                                                                                                      | *        |Оценка, которая содержится в отзыве|
|`name`| Text                                                                                                                                        |          |Заголовок отзыва|
|`reviewBody`| Text                                                                                                                                        |          |Текст отзыва|
|`datePublished`| Date                                                                                                                                        |          |Дата публикации отзыва в формате ISO-8601|

## Microdata

```html
<div itemscope itemtype="https://schema.org/Review">
  <span itemprop="author" itemscope itemtype="https://schema.org/Person">
    <span itemprop="name">John Doe</span>
  </span>
  <div itemprop="itemReviewed" itemscope itemtype="https://schema.org/Organization">
    <img itemprop="image" src="https://example.ru/image/image.jpg" alt="Image alt"/>
    <span itemprop="name">Organization name</span>
  </div>
  <span itemprop="reviewRating" itemscope itemtype="https://schema.org/Rating">
    <span itemprop="ratingValue">4</span>
    <meta itemprop="worstRating" content="0">
    <meta itemprop="bestRating" content="5">
  </span>
  <span itemprop="name">Review title</span>
  <div itemprop="reviewBody">
    Review description
  </div>
  <meta itemprop="datePublished" content="2023-11-04 12:45:57">
</div>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org/",
    "@type": "Review",
    "author": {
      "@type": "Person",
      "name": "John Doe"
    },
    "itemReviewed": {
      "@type": "Organization",
      "image": "https://example.ru/image/image.jpg",
      "name": "Organization name"
    },
    "reviewRating": {
      "@type": "Rating",
      "ratingValue": "4",
      "worstRating": "0",
      "bestRating": "5"
    },
    "name": "Review title",
    "reviewBody": "Review description",
    "datePublished": "2023-11-04 12:45:57"
  }
</script>
```