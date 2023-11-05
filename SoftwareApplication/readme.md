# SoftwareApplication

Информация о приложении.

- [schema.org](https://schema.org/SoftwareApplication)
- [google](https://developers.google.com/search/docs/appearance/structured-data/software-app)
- [yandex](https://yandex.ru/support/webmaster/supported-schemas/software.html)

|itemprop| type| required | description                                           |
| -- | - |--------|-------------------------------------------------------|
|[https://schema.org/SoftwareApplication](https://schema.org/SoftwareApplication)||        |                                                       |
|`name`|Text| *      | Название приложения                                   |
|`offers`|Offer| *      | Стоимость конкретного экземпляра приложения           |
|`aggregateRating`|AggregateRating| *      | Оценка приложения или отзыв                           |
|`operatingSystem`|Text|        | Операционные системы                           |
|`applicationCategory`|Text|        | Тип приложения [Поддерживаемые типы приложений](https://developers.google.com/search/docs/appearance/structured-data/software-app)     |

## Microdata

```html
<div itemscope itemtype="https://schema.org/SoftwareApplication">
  <span itemprop="name">Angry Birds</span>
  <span itemprop="description">Application description</span>
  <span itemprop="operatingSystem">ANDROID</span>
  <span itemprop="applicationCategory">GameApplication</span>
  <div itemprop="aggregateRating" itemscope itemtype="https://schema.org/AggregateRating">
    <span itemprop="ratingValue">4.6</span>
    <span itemprop="ratingCount">8864</span>
  </div>
  <div itemprop="offers" itemscope itemtype="https://schema.org/Offer">
    <span itemprop="price">1.00</span>
    <meta itemprop="priceCurrency" content="USD" />
  </div>
</div>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "SoftwareApplication",
    "name": "Angry Birds",
    "description": "Application description",
    "operatingSystem": "ANDROID",
    "applicationCategory": "GameApplication",
    "aggregateRating": {
      "@type": "AggregateRating",
      "ratingValue": "4.6",
      "ratingCount": "8864"
    },
    "offers": {
      "@type": "Offer",
      "price": "1.00",
      "priceCurrency": "USD"
    }
  }
</script>
```