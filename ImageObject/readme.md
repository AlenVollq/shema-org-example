# ImageObject

Если указать метаданные изображения, то в Google Картинках будут показываться дополнительные сведения, например информация об авторе изображения, о правах на использование, а также сведения о соавторах.

- [schema.org](https://schema.org/ImageObject)
- [google](https://developers.google.com/search/docs/appearance/structured-data/image-license-metadata)
- yandex - нет

| itemprop                                                         | type                                    | required | description    |
|------------------------------------------------------------------|-----------------------------------------|----------|----------------|
| [https://schema.org/ImageObject](https://schema.org/ImageObject) |                                         |          |                |
| `contentUrl`                                                     |URL                                      | *        | URL изображения |
| `creator`                                                        |Organization или Person| *        |Автор изображения|
| `height`                                                         |Distance или QuantitativeValue|          |Высота изображения|
| `width`                                                          |Distance или QuantitativeValue|          |Ширина изображения|
| [ https://schema.org/Person](https://schema.org/Person)          |                                         |          |                |
| `name`                                                           |Text| *        |Имя автора|

## Microdata

```html
<div itemscope itemtype="https://schema.org/ImageObject">
  <img itemprop="contentUrl" src="https://example.ru/image/image.jpg" alt="Image alt" />
  <meta itemprop="height" content="344px">
  <meta itemprop="width" content="344px">
  <span itemprop="creator" itemtype="https://schema.org/Person" itemscope>
    <meta itemprop="name" content="User name" />
  </span>
</div>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org/",
    "@type": "ImageObject",
    "contentUrl": "https://example.ru/image/image.jpg",
    "creator": {
      "@type": "Person",
      "name": "User name"
    },
    "height": "344px",
    "width": "344px"
  }
</script>
```