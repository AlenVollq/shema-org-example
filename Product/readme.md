# Product

Пользователи будут видеть сведения о стоимости и наличии товаров, отзывы с оценками, информацию о доставке и многое
другое.

- [schema.org](https://schema.org/Product)
- [google](https://developers.google.com/search/docs/appearance/structured-data/product)
- [yandex](https://yandex.ru/support/webmaster/supported-schemas/goods-prices.html)

| itemprop                             | type                           | required | description                                                                                                                                                                       |
|--------------------------------------|--------------------------------|--|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [https://schema.org/Product)         |                                |  |                                                                                                                                                                                   |
| `name`                               | Text                           | * | Название товара                                                                                                                                                                   |
| `aggregateRating, review или offers` | AggregateRating, Review, Offer | * | Одно из свойств                                                                                                                                                                   |
| `sku`| Text                           |  | Артикул, идентификатор товара                                                                                                                                                     |
| `url`| URL                            |  | Ссылка на товар                                                                                                                                                                   |
| `description`| Text                           |  | Описание товара                                                                                                                                                                   |
| `image`| ImageObject или URL            |  | Изображение товара                                                                                                                                                                |
| `brand`| Brand или Organization |  | Бренд                                                                                                                                                                             |
| `additionalProperty`| PropertyValue |  | Пара свойство-значение, представляющая дополнительную характеристику объекта, например. особенность продукта или другая характеристика, для которой нет соответствующего свойства |
|[http://schema.org/Offer](http://schema.org/Offer)||  |                                                                                                                                                                                   |
|`price`|Number| * | Цена товара                                                                                                                                                                       |
|`priceCurrency`|Text|  | Валюта, в которой указана цена товара. Используйте трехбуквенный формат ISO 4217                                                                                                  |
|`availability`|ItemAvailability|  | [Используйте один наиболее подходящий статус доступности](https://developers.google.com/search/docs/appearance/structured-data/product?hl=ru#offer-properties)                                                                                                                     |
|`itemCondition`|OfferItemCondition|  | Предопределенное значение из OfferItemCondition, указывающее состояние продукта или услуги либо продуктов или услуг, включенных в предложение                                                                                                                                     |
|`priceValidUntil`|Date|  | Дата в формате ISO 8601, после которой цена перестанет действовать                                                                                                                |

## Microdata

```html
<div itemtype="https://schema.org/Product" itemscope>
  <meta itemprop="name" content="Product name"/>
  <meta itemprop="sku" content="4104">
  <link itemprop="url" href="https://example.ru/product/">
  <meta itemprop="description" content="Product description"/>
  <meta itemprop="image" content="https://example.ru/image/image.jpg">
  <div itemprop="brand" itemtype="https://schema.org/Brand" itemscope>
    <meta itemprop="name" content="Brand name">
  </div>
  <div itemprop="aggregateRating" itemtype="https://schema.org/AggregateRating" itemscope>
    <meta itemprop="reviewCount" content="1"/>
    <meta itemprop="ratingValue" content="5"/>
    <meta itemprop="bestRating" content="5">
  </div>
  <div itemprop="review" itemscope="" itemtype="http://schema.org/Review">
    <span itemprop="author" itemscope="" itemtype="https://schema.org/Person">
      <span itemprop="name">Author name</span>
    </span>
    <link itemprop="url" href="https://example.ru/product/">
    <meta itemprop="datePublished" content="2023-09-04">
    <div itemprop="reviewRating" itemscope="" itemtype="http://schema.org/Rating">
      <meta itemprop="ratingValue" content="5">
      <meta itemprop="bestRating" content="5">
      <meta itemprop="worstRating" content="1">
    </div>
    <meta itemprop="reviewBody" content="Review description">
    <div itemprop="itemReviewed" itemscope="" itemtype="https://schema.org/Organization">
      <meta itemprop="name" content="Organization name">
      <meta itemprop="telephone" content="70000000000">
      <div itemprop="address" itemscope="" itemtype="https://schema.org/PostalAddress">
        <meta itemprop="streetAddress" content="street address">
        <meta itemprop="addressLocality" content="city">
        <meta itemprop="postalCode" content="101010">
        <meta itemprop="addressCountry" content="RU">
      </div>
    </div>
  </div>
  <div itemprop="offers" itemscope="" itemtype="http://schema.org/Offer">
    <meta itemprop="price" content="10980">
    <meta itemprop="priceCurrency" content="RUB">
    <meta itemprop="availability" content="https://schema.org/InStock">
    <meta itemprop="itemCondition" content="https://schema.org/NewCondition">
    <meta itemprop="priceValidUntil" content="2029-09-14T21:30">
  </div>
  <div itemprop="additionalProperty" itemscope="" itemtype="https://schema.org/PropertyValue">
    <span itemprop="name">Color</span>
    <span itemprop="value">White</span>
  </div>
  <div itemprop="additionalProperty" itemscope="" itemtype="https://schema.org/PropertyValue">
    <span itemprop="name">Weight</span>
    <span itemprop="value">200</span>
  </div>
</div>
```

## JSON-LD

```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "Product",
    "name": "Product name",
    "sku": "4104",
    "url": "https://example.ru/product/",
    "description": "Product description",
    "image": "https://example.ru/image/image.jpg",
    "brand": {
      "@type": "Brand",
      "name": "Brand name"
    },
    "aggregateRating": {
      "@type": "AggregateRating",
      "reviewCount": "1",
      "ratingValue": "5",
      "bestRating": "5"
    },
    "review": {
      "@type": "Review",
      "author": {
        "@type": "Person",
        "name": "Author name"
      },
      "url": "https://example.ru/product/",
      "datePublished": "2023-09-04",
      "reviewRating": {
        "@type": "Rating",
        "ratingValue": "5",
        "bestRating": "5",
        "worstRating": "1"
      },
      "reviewBody": "Review description",
      "itemReviewed": {
        "@type": "Organization",
        "name": "Organization name",
        "telephone": "70000000000",
        "address": {
          "@type": "PostalAddress",
          "streetAddress": "street address",
          "addressLocality": "city",
          "postalCode": "101010",
          "addressCountry": "RU"
        }
      }
    },
    "offers": {
      "@type": "Offer",
      "price": "10980",
      "priceCurrency": "RUB",
      "availability": "https://schema.org/InStock",
      "itemCondition": "https://schema.org/NewCondition",
      "priceValidUntil": "2029-09-14T21:30"
    },
      "additionalProperty": [{
      "@type": "PropertyValue",
      "name": "Color",
      "value": "White"
    }, {
      "@type": "PropertyValue",
      "name": "Weight",
      "value": "200"
    }]
  }
</script>
```