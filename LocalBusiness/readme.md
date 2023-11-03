# LocalBusiness
Информация о компании, показываемая в блоке знаний Google, в частности время работы, оценки, схема проезда, инструкции по бронированию или оформлению заказа и т. д.

- [schema.org](https://schema.org/LocalBusiness)
- [google](https://developers.google.com/search/docs/appearance/structured-data/local-business)
- [yandex](https://yandex.ru/support/webmaster/supported-schemas/address-organization.html)

|itemprop| type| required | description                                                                                                                                                   |
| -- | -- |-----|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|[https://schema.org/LocalBusiness](https://schema.org/LocalBusiness)||     |                                                                                                                                                               |
|`name`|Text| *   | Название компании                                                                                                                                             |
|`url`|URL| *   | URL сайта                                                                                                                                                     |
|`telephone`|Text| *   | Номер телефона                                                                                                                                                |
|`address`|PostalAddress| *   | Фактическое местоположение                                                                                                                                    |
|`email`|Text|     | E-mail                                                                                                                                                        |
|`image`|URL|     | Логотип                                                                                                                                                       |
|`priceRange`|Text|     | Ориентировочный порядок цен в компании, выраженный числовым диапазоном (например, "$10–15") или соответствующим количеством символов валюты (например, "$$$") |
|`geo`|GeoCoordinates|     | Географические координаты                                                                                                                                     |
|`openingHoursSpecification`|DayOfWeek|     | Время работы для организации. Массив или отдельный объект OpeningHoursSpecification                                                                           |
|`department`|LocalBusiness|     | Вложенный элемент для отдела компании                                                                                                                                                              |
|[https://schema.org/PostalAddress](https://schema.org/PostalAddress)||     |                                                                                                                                                               |
|`streetAddress`| Text   |     | Адрес                                                                                                                                                         |
|`addressLocality`|Text|     | Населенный пункт                                                                                                                                              |
|`postalCode`|Text|     | Почтовый индекс                                                                                                                                               |
|`addressCountry`|Text или Country|     | Страна. Например, Россия либо двухбуквенный код страны ISO 3166−1 alpha-2                                                                                     |
|[https://schema.org/GeoCoordinate](https://schema.org/GeoCoordinates)|||                                                                                                                                                               |
|`latitude`|Number|     | Широта                                                                                                                                                        |
|`longitude`|Number|     | Долгота                                                                                                                                                       |
|[http://schema.org/OpeningHoursSpecification](http://schema.org/OpeningHoursSpecification)|||                                                                                                                                                               |
|`dayOfWeek`|DayOfWeek|     | День недели.                                                                                                                                                  |
|`opens`|Time|     | Время, в которое компания начинает работат "чч:мм:сс"                                                                                                         |
|`closes`|Time|     | Время, когда компания заканчивает работать "чч:мм:сс".                                                                                                        |


## Microdata

```html
<div itemscope itemtype="https://schema.org/LocalBusiness">
  <meta itemprop="name" content="Market">
  <link itemprop="image" href="https://example.ru/image/logo.svg">
  <link itemprop="url" href="https://example.ru/">
  <meta itemprop="priceRange" content="$$">
  <meta itemprop="telephone" content="70000000000">
  <meta itemprop="email" content="info@example.ru">
  <div itemprop="address" itemscope itemtype="https://schema.org/PostalAddress">
    <meta itemprop="streetAddress" content="street address">
    <meta itemprop="addressLocality" content="city">
    <meta itemprop="postalCode" content="101010">
    <meta itemprop="addressCountry" content="RU">
  </div>
  <div itemprop="geo" itemscope itemtype="https://schema.org/GeoCoordinates">
    <meta itemprop="latitude" content="55.00">
    <meta itemprop="longitude" content="55.00">
  </div>
  <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
    <link itemprop="dayOfWeek" href="http://schema.org/Monday">
    <meta itemprop="opens" content="10:00">
    <meta itemprop="closes" content="21:00">
  </div>
  <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
    <link itemprop="dayOfWeek" href="http://schema.org/Tuesday">
    <meta itemprop="opens" content="10:00">
    <meta itemprop="closes" content="21:00">
  </div>
  <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
    <link itemprop="dayOfWeek" href="http://schema.org/Wednesday">
    <meta itemprop="opens" content="10:00">
    <meta itemprop="closes" content="21:00">
  </div>
  <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
    <link itemprop="dayOfWeek" href="http://schema.org/Thursday">
    <meta itemprop="opens" content="10:00">
    <meta itemprop="closes" content="21:00">
  </div>
  <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
    <link itemprop="dayOfWeek" href="http://schema.org/Friday">
    <meta itemprop="opens" content="10:00">
    <meta itemprop="closes" content="21:00">
  </div>
  <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
    <link itemprop="dayOfWeek" href="http://schema.org/Saturday">
    <meta itemprop="opens" content="09:00">
    <meta itemprop="closes" content="20:00">
  </div>
  <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
    <link itemprop="dayOfWeek" href="http://schema.org/Sunday">
    <meta itemprop="opens" content="09:00">
    <meta itemprop="closes" content="20:00">
  </div>
  <div itemprop="department" itemscope itemtype="https://schema.org/LocalBusiness">
    <meta itemprop="name" content="Market Department">
    <link itemprop="image" href="https://example.ru/image/logo.svg">
    <link itemprop="url" href="https://example.ru/">
    <meta itemprop="priceRange" content="$$">
    <meta itemprop="telephone" content="71111111111">
    <meta itemprop="email" content="info@example.ru">
    <div itemprop="address" itemscope itemtype="https://schema.org/PostalAddress">
      <meta itemprop="streetAddress" content="street address department">
      <meta itemprop="addressLocality" content="city">
      <meta itemprop="postalCode" content="101010">
      <meta itemprop="addressCountry" content="RU">
    </div>
    <div itemprop="geo" itemscope itemtype="https://schema.org/GeoCoordinates">
      <meta itemprop="latitude" content="60.00">
      <meta itemprop="longitude" content="60.00">
    </div>
    <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
      <link itemprop="dayOfWeek" href="http://schema.org/Monday">
      <meta itemprop="opens" content="09:00">
      <meta itemprop="closes" content="20:00">
    </div>
    <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
      <link itemprop="dayOfWeek" href="http://schema.org/Tuesday">
      <meta itemprop="opens" content="09:00">
      <meta itemprop="closes" content="20:00">
    </div>
    <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
      <link itemprop="dayOfWeek" href="http://schema.org/Wednesday">
      <meta itemprop="opens" content="09:00">
      <meta itemprop="closes" content="20:00">
    </div>
    <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
      <link itemprop="dayOfWeek" href="http://schema.org/Thursday">
      <meta itemprop="opens" content="09:00">
      <meta itemprop="closes" content="20:00">
    </div>
    <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
      <link itemprop="dayOfWeek" href="http://schema.org/Friday">
      <meta itemprop="opens" content="09:00">
      <meta itemprop="closes" content="20:00">
    </div>
    <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
      <link itemprop="dayOfWeek" href="http://schema.org/Saturday">
      <meta itemprop="opens" content="09:00">
      <meta itemprop="closes" content="20:00">
    </div>
    <div itemprop="openingHoursSpecification" itemscope itemtype="http://schema.org/OpeningHoursSpecification">
      <link itemprop="dayOfWeek" href="http://schema.org/Sunday">
      <meta itemprop="opens" content="09:00">
      <meta itemprop="closes" content="20:00">
    </div>
  </div>
</div>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "LocalBusiness",
    "name": "Market",
    "image": "https://example.ru/image/logo.svg",
    "url": "https://example.ru/",
    "telephone": "70000000000",
    "email": "info@example.ru",
    "priceRange": "$$",
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "street address",
      "addressLocality": "city",
      "postalCode": "101010",
      "addressCountry": "RU"
    },
    "geo": {
      "@type": "GeoCoordinates",
      "latitude": 55.00,
      "longitude": 55.00
    },
    "openingHoursSpecification": [{
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": [
        "Monday",
        "Tuesday",
        "Wednesday",
        "Thursday",
        "Friday"
      ],
      "opens": "10:00",
      "closes": "21:00"
    },{
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": [
        "Saturday",
        "Sunday"
      ],
      "opens": "09:00",
      "closes": "20:00"
    }],
    "department": [{
      "@type": "LocalBusiness",
      "name": "Market Department",
      "image": "https://example.ru/image/logo.svg",
      "url": "https://example.ru/",
      "telephone": "71111111111",
      "email": "info@example.ru",
      "priceRange": "$$",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "street address department",
        "addressLocality": "city",
        "postalCode": "101010",
        "addressCountry": "RU"
      },
      "geo": {
        "@type": "GeoCoordinates",
        "latitude": 60.00,
        "longitude": 60.00
      },
      "openingHoursSpecification": [{
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": [
          "Monday",
          "Tuesday",
          "Wednesday",
          "Thursday",
          "Friday",
          "Saturday",
          "Sunday"
        ],
        "opens": "09:00",
        "closes": "20:00"
      }]
    }]
  }
</script>
```