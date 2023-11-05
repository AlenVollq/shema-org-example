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
    <meta itemprop="telephone" content="70000000000">
    <div itemprop="address" itemscope="" itemtype="https://schema.org/PostalAddress">
      <meta itemprop="streetAddress" content="street address">
      <meta itemprop="addressLocality" content="city">
      <meta itemprop="postalCode" content="101010">
      <meta itemprop="addressCountry" content="RU">
    </div>
  </div>
  <span itemprop="reviewRating" itemscope itemtype="https://schema.org/Rating">
    <span itemprop="ratingValue">4</span>
    <meta itemprop="worstRating" content="0">
    <meta itemprop="bestRating" content="5">
  </span>
  <span itemprop="name">Review title</span>
  <link itemprop="url" href="https://example.ru/review/">
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
      "name": "Organization name",
      "telephone": "70000000000",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "street address",
        "addressLocality": "city",
        "postalCode": "101010",
        "addressCountry": "RU"
      }
    },
    "reviewRating": {
      "@type": "Rating",
      "ratingValue": "4",
      "worstRating": "0",
      "bestRating": "5"
    },
    "name": "Review title",
    "url": "https://example.ru/review/",
    "reviewBody": "Review description",
    "datePublished": "2023-11-04 12:45:57"
  }
</script>
```