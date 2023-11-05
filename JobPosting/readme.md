# JobPosting

Объявления о вакансиях в Google Поиск.

- [schema.org](https://schema.org/JobPosting)
- [google](https://developers.google.com/search/docs/appearance/structured-data/job-posting)
- yandex - нет

|itemprop| type|required| description                                                       |
| -- | - | - |-------------------------------------------------------------------|
|[https://schema.org/JobPosting](https://schema.org/JobPosting)|||                                                                   |
|`title`|Text|*| Название должности                                                |
|`datePosted`|Date|*| Дата публикации вакансии. Указывается согласно стандарту ISO 8601 |
|`description`|Text|*| Полное описание вакансии в формате HTML. Распознаются следующие теги HTML: `<p>, <ul> и <li>`|
|`hiringOrganization`|Organization|*|Организация-работодатель                                               |
|`jobLocation`|Place|*|Физическое местоположение места работы                                                |
|[https://schema.org/PostalAddress](https://schema.org/PostalAddress)||     |                                                                                                                                                               |
|`streetAddress`| Text   |     | Адрес                                                                                                                                                         |
|`addressLocality`|Text|     | Населенный пункт                                                                                                                                              |
|`postalCode`|Text|     | Почтовый индекс                                                                                                                                               |
|`addressCountry`|Text или Country|     | Страна. Например, Россия либо двухбуквенный код страны ISO 3166−1 alpha-2                                                                                     |

## Microdata

```html
<div itemscope itemtype="https://schema.org/JobPosting">
  <h2 itemprop="title">Software Engineer</h2>
  <span itemprop="datePosted">2016-02-18</span>
  <div itemprop="description"> 
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. 
    Aut cum distinctio ducimus magni maiores minima modi mollitia, 
    non obcaecati optio qui quis voluptas voluptates. Dolores illo maxime similique sit suscipit.
  </div>
  <div itemprop="hiringOrganization" itemscope itemtype="https://schema.org/Organization">
    <span itemprop="name">Organization name</span>
    <meta itemprop="telephone" content="70000000000">
    <div itemprop="address" itemscope itemtype="https://schema.org/PostalAddress">
      <meta itemprop="streetAddress" content="street address">
      <meta itemprop="addressLocality" content="city">
      <meta itemprop="postalCode" content="101010">
      <meta itemprop="addressCountry" content="RU">
    </div>
  </div>
  <div itemprop="jobLocation" itemscope itemtype="https://schema.org/Place">
    <span itemprop="name">Organization name</span>
    <meta itemprop="telephone" content="70000000000">
    <div itemprop="address" itemscope itemtype="https://schema.org/PostalAddress">
      <span itemprop="streetAddress">555 Clancy St</span>
      <span itemprop="addressLocality">Detroit</span>
      <span itemprop="postalCode">48201</span>
      <span itemprop="addressCountry">US</span>
    </div>
  </div>
</div>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context" : "https://schema.org/",
    "@type" : "JobPosting",
    "title" : "Software Engineer",
    "datePosted" : "2016-02-18",
    "description" : "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aut cum distinctio ducimus magni maiores minima modi mollitia, non obcaecati optio qui quis voluptas voluptates. Dolores illo maxime similique sit suscipit.",
    "hiringOrganization" : {
      "@type" : "Organization",
      "name" : "Organization name",
      "telephone": "70000000000",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "street address",
        "addressLocality": "city",
        "postalCode": "101010",
        "addressCountry": "RU"
      }
    },
    "jobLocation": {
      "@type": "Place",
      "name" : "Organization name",
      "telephone": "70000000000",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "555 Clancy St",
        "addressLocality": "Detroit",
        "postalCode": "48201",
        "addressCountry": "US"
      }
    }
  }
</script>
```