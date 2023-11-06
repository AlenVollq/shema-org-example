# Recipe

Чтобы ваши рецепты было проще найти, предоставьте сведения об отзывах, времени приготовления и калорийности.

- [schema.org](https://schema.org/Recipe)
- [google](https://developers.google.com/search/docs/appearance/structured-data/recipe)
- [yandex](https://yandex.ru/support/webmaster/supported-schemas/recipe.html)

|itemprop| type                    | required | description                                                                                                                                               |
| -- |-------------------------|----|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|[ttps://schema.org/Recipe](ttps://schema.org/Recipe)|                         |    |                                                                                                                                                           |
|`name`| Text                    | *  | Название блюда                                                                                                                                            |
|`image`| URL или ImageObject     | *  | Изображение готового блюда                                                                                                                                |
|`author`| Person или Organization |    | Автор рецепта (имя человека или название организации)                                                                                                     |
|`datePublished`| Date                    |    | Дата публикации рецепта в формате ISO 8601                                                                                                                |
|`description`| Text                    |    | Краткое описание блюда                                                                                                                                    |
|`prepTime`| Duration                |    | Общее время подготовки и приготовления блюда, указанное в формате ISO 8601. Всегда используйте это свойство вместе с элементом cookTime.                  |
|`cookTime`| Duration                |    | Время, которое требуется на приготовление блюда. Значение следует вводить в формате ISO 8601. Всегда используйте это свойство вместе с элементом prepTime. |
|`totalTime`| Duration                |    | Общее время приготовления блюда в формате ISO 8601. Используйте свойство totalTime или же комбинацию cookTime и prepTime.                                 |
|`recipeYield`| Text или Integer        |    | Количество итогового продукта. Количество порций                                                                                                          |
|`recipeCategory`| Text                    |    | Вид блюда                                                                                                                                                 |
|`recipeCuisine`| Text                    |    | К какой кухне мира относится рецепт                                                                                                                       |
|`nutrition.calories`| Energy                  |    | Количество калорий в каждой порции блюда                                                                                                                  |
|`recipeIngredient`| Text                    |    | Ингредиенты, используемые в рецепте                                                                                                                       |
|`recipeInstructions`| HowToStep               |    | Этапы приготовления блюда                                                                                                                                 |
|`aggregateRating`| AggregateRating         |    | Аннотация к средней оценке по отзывам                                                                                                                     |
|`video`| VideoObject             |    | Видео, иллюстрирующее этапы приготовления блюда                                                                                                           |
|[https://schema.org/HowToStep](https://schema.org/HowToStep)|                         |    |                                                                                                                                                           |
|`text`| Text                    | *  | Полный текст шага инструкции                                                                                                                              |
|`name`| Text                    |    | От одного до нескольких слов, кратко описывающих шаг                                                                                                      |
|`url`| URL                     |    | URL прямой ссылки на шаг                                                                                                                                  |
|`image`| ImageObject или URL     |    | Иллюстрация к шагу инструкции                                                                                                                             |
|[https://schema.org/VideoObject](https://schema.org/VideoObject)|                         |    |                                                                                                                                                           |
|`contentUrl`| URL                     | *  | URL файла видео                                                                                                                                           |
|`name`| Text                    |    | Наименование видео                                                                                                                                        |
|`uploadDate`| Date или DateTime|    | Дата когда видео было загружено                                                                                                                           |
|`duration`| Duration|    | Продолжительность видео в формате даты ISO 8601                                                                                                           |
|`description`| Text                    |    | Описание видео                                                                                                                                            |
|`url`| URL                    |    | Ссылка на видео                                                                                                                                           |
|`thumbnail`| ImageObject                    |    | Миниатюра изображения или видео                                                                                                                           |
|`thumbnailUrl`| URL                    |    | Миниатюрное изображение, относящееся к видео                                                                                                              |
|`isFamilyFriendly`| Boolean                    |    | Указывает, подходит ли этот контент для семейного просмотра                                                                                                                                        |

## Microdata

```html
<section itemscope itemtype="https://schema.org/Recipe">
  <h1 itemprop="name">Cake</h1>
  <img itemprop="image" src="https://example.ru/image/cake/image.jpg" alt="Image alt">
  <div itemprop="author" itemscope itemtype="https://schema.org/Person">
    <p itemprop="name">John Doe</p>
  </div>
  <span itemprop="datePublished">2020-11-06</span>
  <p itemprop="description">Cake description</p>
  <meta itemprop="prepTime" content="PT20M">
  <meta itemprop="cookTime" content="PT30M">
  <meta itemprop="totalTime" content="PT50M">
  <meta itemprop="recipeYield" content="10">
  <p itemprop="recipeCategory">Dessert</p>
  <p itemprop="recipeCuisine">American</p>
  <div itemprop="nutrition" itemscope itemtype="https://schema.org/NutritionInformation">
    <p itemprop="calories">270 calories</p>
  </div>
  <ul>
    <li itemprop="recipeIngredient">2 cups of flour</li>
    <li itemprop="recipeIngredient">3/4 cup white sugar</li>
    <li itemprop="recipeIngredient">2 teaspoons baking powder</li>
    <li itemprop="recipeIngredient">1/2 teaspoon salt</li>
    <li itemprop="recipeIngredient">1/2 cup butter</li>
    <li itemprop="recipeIngredient">2 eggs</li>
    <li itemprop="recipeIngredient">3/4 cup milk</li>
  </ul>
  <ul>
    <li itemprop="recipeInstructions" itemscope itemtype="https://schema.org/HowToStep">
      <span itemprop="name">Preheat</span>
      <span itemprop="text">Preheat the oven to 350 degrees F. Grease and flour a 9x9 inch pan.</span>
      <link itemprop="url" href="https://example.ru/cake#step1">
      <img itemprop="image" src=https://example.ru/image/cake/image1.jpg" alt="Image alt"/>
    </li>
    <li itemprop="recipeInstructions" itemscope itemtype="https://schema.org/HowToStep">
      <span itemprop="name">Mix dry ingredients</span>
      <span itemprop="text">In a large bowl, combine flour, sugar, baking powder, and salt.</span>
      <link itemprop="url" href="https://example.ru/cake#step2">
      <img itemprop="image" src=https://example.ru/image/cake/image2.jpg" alt="Image alt"/>
    </li>
    <li itemprop="recipeInstructions" itemscope itemtype="https://schema.org/HowToStep">
      <span itemprop="name">Bake</span>
      <span itemprop="text">Bake for 30 to 35 minutes, or until firm.</span>
      <link itemprop="url" href="https://example.ru/cake#step3">
      <img itemprop="image" src=https://example.ru/image/cake/image3.jpg" alt="Image alt"/>
    </li>
    <li itemprop="recipeInstructions" itemscope itemtype="https://schema.org/HowToStep">
      <span itemprop="name">Enjoy</span>
      <span itemprop="text">Allow to cool and enjoy.</span>
      <link itemprop="url" href="https://example.ru/cake#step4">
      <img itemprop="image" src=https://example.ru/image/cake/image4.jpg" alt="Image alt"/>
    </li>
  </ul>
  <div itemprop="aggregateRating" itemscope itemtype="https://schema.org/AggregateRating">
    <span itemprop="ratingValue">5</span>
    <span itemprop="ratingCount">18</span>
  </div>
  <div itemscope itemprop="video" itemtype="https://schema.org/VideoObject">
    <link itemprop="contentUrl" href="https://example.ru/video.mp4" />
    <p itemprop="name">How to make a Cake</p>
    <meta itemprop="uploadDate" content="2020-11-06T08:00:00+08:00" />
    <meta itemprop="duration" content="PT1M33S" />
    <p itemprop="description">This is how you make a Cake.</p>
    <link itemprop="url" href="https://example.ru/cake/" />
    <link itemprop="thumbnail" href="https://example.ru/image/cake/video.jpg" />
    <link itemprop="thumbnailUrl" href="https://example.ru/image/cake/video.jpg" />
    <meta itemprop="isFamilyFriendly" content="true">
  </div>
</section>
```

## JSON-LD
```javascript
<script type="application/ld+json">
  {
    "@context": "https://schema.org/",
    "@type": "Recipe",
    "name": "Cake",
    "image": "https://example.ru/image/cake/image.jpg",
    "author": {
      "@type": "Person",
      "name": "John Doe"
    },
    "datePublished": "2020-11-06",
    "description": "Cake description",
    "prepTime": "PT20M",
    "cookTime": "PT30M",
    "totalTime": "PT50M",
    "recipeYield": "10",
    "recipeCategory": "Dessert",
    "recipeCuisine": "American",
    "nutrition": {
      "@type": "NutritionInformation",
      "calories": "270 calories"
    },
    "recipeIngredient": [
      "2 cups of flour",
      "3/4 cup white sugar",
      "2 teaspoons baking powder",
      "1/2 teaspoon salt",
      "1/2 cup butter",
      "2 eggs",
      "3/4 cup milk"
    ],
    "recipeInstructions": [
      {
        "@type": "HowToStep",
        "name": "Preheat",
        "text": "Preheat the oven to 350 degrees F. Grease and flour a 9x9 inch pan.",
        "url": "https://example.ru/cake#step1",
        "image": "https://example.ru/image/cake/image1.jpg"
      },
      {
        "@type": "HowToStep",
        "name": "Mix dry ingredients",
        "text": "In a large bowl, combine flour, sugar, baking powder, and salt.",
        "url": "https://example.ru/cake#step2",
        "image": "https://example.ru/image/cake/image2.jpg"
      },
      {
        "@type": "HowToStep",
        "name": "Bake",
        "text": "Bake for 30 to 35 minutes, or until firm.",
        "url": "https://example.ru/cake#step3",
        "image": "https://example.ru/image/cake/image3.jpg"
      },
      {
        "@type": "HowToStep",
        "name": "Enjoy",
        "text": "Allow to cool and enjoy.",
        "url": "https://example.ru/cake#step4",
        "image": "https://example.ru/image/cake/image4.jpg"
      }
    ],
    "aggregateRating": {
      "@type": "AggregateRating",
      "ratingValue": "5",
      "ratingCount": "18"
    },
    "video": {
      "@type": "VideoObject",
      "name": "How to make a Cake",
      "uploadDate": "2020-11-06T08:00:00+08:00",
      "duration": "PT1M33S",
      "description": "This is how you make a Cake.",
      "url": "https://example.ru/cake/",
      "contentUrl": "https://example.ru/video.mp4",
      "thumbnail": "https://example.ru/image/cake/video.jpg",
      "thumbnailUrl": "https://example.ru/image/cake/video.jpg",
      "isFamilyFriendly": "true"
    }
  }
</script>
```