# BreadcrumbList

Информация о том, в каком разделе сайта находится текущая страница.

- [schema.org](https://schema.org/BreadcrumbList)
- [google](https://developers.google.com/search/docs/appearance/structured-data/breadcrumb)
- [yandex](https://yandex.ru/support/webmaster/supported-schemas/navigation-links.html)

|itemprop| type|required|description|
| -- | - | - | -- |
|[https://schema.org/BreadcrumbList](https://schema.org/BreadcrumbList)||||
|`itemListElement`|ListItem|*|Массив строк навигации|
|[https://schema.org/ListItem](https://schema.org/ListItem)||||
|`item`|URL|*|URL страницы|
|`name`|Text|*|Название строки навигации, которое видит пользователь|
|`position`|Integer|*|Позиция страницы в иерархии сайта начиная с 1|
## Microdata

```html
<ul itemscope itemtype="https://schema.org/BreadcrumbList">
  <!-- Item -->
  <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
    <a itemprop="item" href="https://example.com/">
      <span itemprop="name">Home</span>
    </a>
    <meta itemprop="position" content="1"/>
  </li>
  
  <!-- Item -->
  <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
    <a itemprop="item" href="https://example.com/catalog/">
      <span itemprop="name">Catalog</span>
    </a>
    <meta itemprop="position" content="2"/>
  </li>
  
  <!-- Item -->
  <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
    <a itemprop="item" href="https://example.com/catalog/category/">
      <span itemprop="name">Category</span>
    </a>
    <meta itemprop="position" content="3"/>
  </li>
  
  <!-- Item -->
  <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
    <link itemprop="item" href="https://example.com/catalog/category/item/">
    <span itemprop="name">Item</span>
    <meta itemprop="position" content="4"/>
  </li>
</ul>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "BreadcrumbList",
    "itemListElement": [{
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://example.com/"
    },{
      "@type": "ListItem",
      "position": 2,
      "name": "Catalog",
      "item": "https://example.com/catalog/"
    },{
      "@type": "ListItem",
      "position": 3,
      "name": "Category",
      "item": "https://example.com/catalog/category/"
    },{
      "@type": "ListItem",
      "position": 4,
      "name": "Item",
      "item": "https://example.com/catalog/category/item/"
    }]
  }
</script>
```