# BigCommerce StoreInsight API Dcoumentation

The **BigCommerce StoreInsight API** empowers developers with access to comprehensive metrics and insights related to BigCommerce stores. This API allows users to retrieve valuable data on store performance, traffic, customer behavior, and product metrics, supporting data-driven decision-making and strategic planning for online retail operations.

With straightforward access to product catalogs, analytics, inventory counts, store details, and more, the **BigCommerce StoreInsight API** makes it easy to gather and analyze essential store data. The API provides structured JSON responses, facilitating seamless integration into platforms and workflows for improved automation and insight generation.

# Key Features:
- Access to detailed store info & analytics.
- Insights into customer interactions and purchase patterns.
- Performance metrics for products and categories.
- Traffic analysis to understand visitor behavior.

# Authentication
The URL you need to use is the following: `https://bigcommerce-storeinsight-api.p.rapidapi.com/`
The API requires the headers listed below:

 - **`x-rapidapi-host`**: `bigcommerce-storeinsight-api.p.rapidapi.com`
 - **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/bigcommerce-storeinsight-api/pricing).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

# Endpoints
The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

#### 1. **`GET /store/search`**
-   **Description**: This endpoint allows searching stores based on provided query parameters such as `query`, `page`, and `perPage`. It retrieves results from a CSV file and returns them as JSON.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `query`  | string   | `-` | Specifies the search term   | Yes       |
| `page`  | string   | `1` | Specifies the page number for paginated results  | No       |
| `perPage`  | string   | `10` | Specifies the number of results per page. Maximum value allowed is 35   | No       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/search?query=fit&perPage=2', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "totalResults": 228,
  "totalPages": 114,
  "currentPage": 1,
  "perPage": 2,
  "data": [
    {
      "Domain name": "anghu.cn",
      "Company name": "Anghu",
      "Category": "",
      "Language": "en",
      "Popularity": "1",
      "Twitter": "anghufitness",
      "Facebook": "anghufitness",
      "Available Emails ": "1"
    },
    {
      "Domain name": "fitnessreality.com",
      "Company name": "Fitness Reality",
      "Category": "Sport",
      "Language": "en",
      "Popularity": "1",
      "Twitter": "fitnessrealityx",
      "Facebook": "fitnessreality4u",
      "Available Emails ": "0"
    }
  ]
}
```

#### 2. **`GET /store/random`**
-   **Description**: This endpoint retrieves a random selection of stores with pagination options, allowing users to specify the number of results per page and the page number.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `page`  | string   | `1`| Specifies the page number for paginated results  | No       |
| `perPage`  | string   | `10`| Specifies the number of results per page. The maximum value allowed is 35  | No       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/random?perPage=2', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "totalPages": 21288,
  "currentPage": 1,
  "perPage": 2,
  "data": [
    {
      "Domain name": "velighting.com",
      "Company name": "",
      "Category": "",
      "Language": "",
      "Popularity": "",
      "Twitter": "",
      "Facebook": "",
      "Available Emails ": ""
    },
    {
      "Domain name": "robot-zero.com",
      "Company name": "",
      "Category": "",
      "Language": "",
      "Popularity": "",
      "Twitter": "",
      "Facebook": "",
      "Available Emails ": ""
    }
  ]
}
```

#### 3. **`GET /store/all`**
-   **Description**: This endpoint retrieves a paginated list of all stores, allowing users to specify the number of results per page and the page number.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `page`  | string   | `1`| Specifies the page number for paginated results  | No       |
| `perPage`  | string   | `10`| Specifies the number of results per page. The maximum value allowed is 35  | No       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/all?perPage=2', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "totalPages": 21288,
  "currentPage": 1,
  "perPage": 2,
  "data": [
    {
      "Domain name": "suspensionshop.com",
      "Company name": "Suspension Shop",
      "Category": "Automotive",
      "Language": "en",
      "Popularity": "1",
      "Twitter": "",
      "Facebook": "suspensionshopaz",
      "Available Emails ": "1"
    },
    {
      "Domain name": "shoppopsonic.com",
      "Company name": "Pop Sonic",
      "Category": "Manufacturing",
      "Language": "en",
      "Popularity": "1",
      "Twitter": "shoppopsonic",
      "Facebook": "shoppopsonic",
      "Available Emails ": "3"
    }
  ]
}
```

#### 4. **`GET /product/description`**
-   **Description**: This endpoint retrieves the description of a product based on its URL. It also utilizes caching to improve performance by storing and retrieving data for previously requested product URLs.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `productUrl`  | string   | `-` | The URL of the product whose description is to be fetched  | Yes       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/product/description?productUrl=https%3A%2F%2Fyummycupcakes.com%2Fclassic-cupcakes-6-box%2F', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "data": {
    "productId": "142",
    "title": "CLASSIC CUPCAKES - 6 BOX",
    "mainImage": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/415/Cupcakes_6_R2__57429.1591753152.jpg?c=2",
    "images": [
      {
        "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/415/Cupcakes_6_R2__57429.1591753152.jpg?c=2",
        "alt": "CLASSIC CUPCAKES - 6 BOX"
      },
      {
        "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/616/Classic_6_Box_copy__99326.1677977252.jpg?c=2",
        "alt": "CLASSIC CUPCAKES - 6 BOX"
      }
    ],
    "description": "CUSTOM CUPCAKE 6 PACK\nIt is always fun to create your very own, custom designed collection! Build your 6 pack from a list of traditional and unique artisanal flavor combinations from our menu. You can choose 6 different flavors or all of one flavor. . . that's the beauty. It will become your custom collection so it is sure to be a hit!\nWe do not ship these cupcakes.  For a delicious treat you can ship, please order the Cupcake in a Jar.",
    "reviewsCount": "(No reviews yet)",
    "prices": {
      "sku": null,
      "upc": null,
      "mpn": null,
      "gtin": null,
      "weight": null,
      "base": true,
      "image": null,
      "price": {
        "with_tax": {
          "formatted": "$25.50",
          "value": 25.5,
          "currency": "USD"
        },
        "tax_label": "Tax"
      },
      "out_of_stock_behavior": "hide_option",
      "out_of_stock_message": "Out of stock",
      "available_modifier_values": [
        4125,
        4158,
        3927,
        3928,
        4159,
        4076,
        4026,
        3889,
        4077,
        4078,
        2294,
        4050,
        ...
      ],
      "in_stock_attributes": [
        4125,
        4158,
        3927,
        3928,
        4159,
        4076,
        4026,
        3889,
        4077,
        4078,
        2294,
        4050,
        3468,
        ...
      ],
      "stock": null,
      "instock": true,
      "stock_message": null,
      "purchasable": true,
      "purchasing_message": null
    },
    "attributes": [
      {
        "label": "Flavor 1",
        "options": [
          {
            "value": "4125",
            "text": "Black Forrest (until Nov 3)"
          },
          {
            "value": "4158",
            "text": "Blackout (until Nov 3)"
          },
          {
            "value": "3927",
            "text": "Brown Sugar Cinnamon (until Dec 1)"
          },
          ...
        ]
      },
      {
        "label": "Flavor 2",
        "options": [
          {
            "value": "4125",
            "text": "Black Forrest (until Nov 3)"
          },
          {
            "value": "4158",
            "text": "Blackout (until Nov 3)"
          },
          ...
        ]
      },
      ...
    ],
    "variantsProducts": [
      {
        "name": "CLASSIC CUPCAKES - 4 BOX",
        "price": "$17.00",
        "url": "https://yummycupcakes.com/classic-cupcakes-4-box/",
        "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
      },
      {
        "name": "BIRTHDAY CUPCAKES - 6 BOX",
        "price": "$28.50",
        "url": "https://yummycupcakes.com/birthday-cupcakes-6-box/",
        "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
      },
      ...
    ]
  }
}
```

##### **Caching:**
- The endpoint checks if the product description is already cached using a key based on the product URL. If found, it returns the cached data, otherwise, it fetches the description from an external source.

#### 5. **`GET /store/products`**
-   **Description**: This endpoint retrieves a paginated list of all products from a specified store URL. It supports caching for improved performance, allowing for faster retrieval of previously requested data.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `storeUrl`  | string   | `-`| The URL of the store from which to fetch the products  | No       |
| `page`  | string   | `1`| Specifies the page number for paginated results  | No       |
| `perPage`  | string   | `10`| Specifies the number of results per page. The maximum value allowed is 15  | No       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/products?storeUrl=https%3A%2F%2Fyummycupcakes.com%2F', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "data": {
    "products": [
      {
        "productId": "234",
        "title": "Edible Biscoff Cookie Dough",
        "mainImage": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/234/690/Cookie_Dough_2__87116.1730053234.jpg?c=2",
        "images": [
          {
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/234/690/Cookie_Dough_2__87116.1730053234.jpg?c=2",
            "alt": "Edible Biscoff Cookie Dough"
          }
        ],
        "description": "EDIBLE COOKIE DOUGH IS SUCH A GREAT TREAT!!!\nScoops of fresh made edible Biscoff cookie dough...with lots of Biscoff cookie pieces!  It's ready to eat.  Served in a colorful paper cup with lid and spoon so you are ready to eat and love it.  You can put in the frig so you can enjoy all week...or...come into the Bakeshop and get another cup.\nTry the Chocolate Chip cookie dough too!\nGreat dessert break for afternoon meetings, fun to serve at parties, look great on your dessert table, or a treat just for you!\n \nFor large quantity orders, you can also call us directly at 818.558.1080.",
        "reviewsCount": "(No reviews yet)",
        "prices": {
          "sku": null,
          "upc": null,
          "mpn": null,
          "gtin": null,
          "weight": null,
          "base": true,
          "image": null,
          "price": {
            "with_tax": {
              "formatted": "$5.75",
              "value": 5.75,
              "currency": "USD"
            },
            "tax_label": "Tax"
          },
          "out_of_stock_behavior": "hide_option",
          "out_of_stock_message": "Out of stock",
          "available_modifier_values": [],
          "in_stock_attributes": [],
          "stock": null,
          "instock": true,
          "stock_message": null,
          "purchasable": true,
          "purchasing_message": null
        },
        "attributes": [
          {
            "label": "Pick Up Date [Tue-Sat] (24 hours in advance):",
            "options": [
              {
                "value": "1",
                "text": "\n                Jan\n            "
              },
              {
                "value": "2",
                "text": "\n                Feb\n            "
              },
              {
                "value": "3",
                "text": "\n                Mar\n            "
              },
              ...
            ]
          }
        ],
        "variantsProducts": [
          {
            "name": "Edible Choc Chip Cookie Dough",
            "price": "$5.75",
            "url": "https://yummycupcakes.com/edible-choc-chip-cookie-dough/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "Sugar Cookie",
            "price": "$3.00",
            "url": "https://yummycupcakes.com/sugar-cookie/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "Choc Chip/Oat/Sea Salt Cookie",
            "price": "$3.00",
            "url": "https://yummycupcakes.com/choc-chip-oat-sea-salt-cookie/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          }
        ]
      },
      {
        "productId": "142",
        "title": "CLASSIC CUPCAKES - 6 BOX",
        "mainImage": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/415/Cupcakes_6_R2__57429.1591753152.jpg?c=2",
        "images": [
          {
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/415/Cupcakes_6_R2__57429.1591753152.jpg?c=2",
            "alt": "CLASSIC CUPCAKES - 6 BOX"
          },
          {
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/616/Classic_6_Box_copy__99326.1677977252.jpg?c=2",
            "alt": "CLASSIC CUPCAKES - 6 BOX"
          }
        ],
        "description": "CUSTOM CUPCAKE 6 PACK\nIt is always fun to create your very own, custom designed collection! Build your 6 pack from a list of traditional and unique artisanal flavor combinations from our menu. You can choose 6 different flavors or all of one flavor. . . that's the beauty. It will become your custom collection so it is sure to be a hit!\nWe do not ship these cupcakes.  For a delicious treat you can ship, please order the Cupcake in a Jar.",
        "reviewsCount": "(No reviews yet)",
        "prices": {
          "sku": null,
          "upc": null,
          "mpn": null,
          "gtin": null,
          "weight": null,
          "base": true,
          "image": null,
          "price": {
            "with_tax": {
              "formatted": "$25.50",
              "value": 25.5,
              "currency": "USD"
            },
            "tax_label": "Tax"
          },
          "out_of_stock_behavior": "hide_option",
          "out_of_stock_message": "Out of stock",
          "available_modifier_values": [
            4125,
            4158,
            3927,
            3928,
            4159,
            ...
          ],
          "in_stock_attributes": [
            4125,
            4158,
            3927,
            3928,
            4159,
            ...
          ],
          "stock": null,
          "instock": true,
          "stock_message": null,
          "purchasable": true,
          "purchasing_message": null
        },
        "attributes": [
          {
            "label": "Flavor 1",
            "options": [
              {
                "value": "4125",
                "text": "Black Forrest (until Nov 3)"
              },
              {
                "value": "4158",
                "text": "Blackout (until Nov 3)"
              },
              ...
            ]
          },
          {
            "label": "Flavor 2",
            "options": [
              {
                "value": "4125",
                "text": "Black Forrest (until Nov 3)"
              },
              {
                "value": "4158",
                "text": "Blackout (until Nov 3)"
              },
              ...
            ]
          },
          ...
        ],
        "variantsProducts": [
          {
            "name": "CLASSIC CUPCAKES - 4 BOX",
            "price": "$17.00",
            "url": "https://yummycupcakes.com/classic-cupcakes-4-box/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "BIRTHDAY CUPCAKES - 6 BOX",
            "price": "$28.50",
            "url": "https://yummycupcakes.com/birthday-cupcakes-6-box/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "CHEF'S CHOICE CUPCAKES - 6 BOX",
            "price": "$25.50",
            "url": "https://yummycupcakes.com/chefs-choice-cupcakes-6-box/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "SPECIALTY BIRTHDAY CUPCAKES - 6 BOX",
            "price": "$30.00",
            "url": "https://yummycupcakes.com/specialty-birthday-cupcakes-6-box/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "CLASSIC CUPCAKE IN A JAR 4 BOX - PICK UP",
            "price": "$39.39",
            "url": "https://yummycupcakes.com/classic-cupcake-in-a-jar-4-box-pick-up/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "CLASSIC CUPCAKES - DOZEN",
            "price": "$49.00",
            "url": "https://yummycupcakes.com/classic-cupcakes-dozen/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "INDIVIDUAL CLASSIC CUPCAKE",
            "price": "$4.75",
            "url": "https://yummycupcakes.com/individual-classic-cupcake/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "SPECIALTY ASSTD CUPCAKE 6 BOX (Vegan, GL, GLV)",
            "price": "$27.00",
            "url": "https://yummycupcakes.com/specialty-asstd-cupcake-6-box-vegan-gl-glv/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "6 Months of Cupcakes!",
            "price": "$260.00",
            "url": "https://yummycupcakes.com/6-months-of-cupcakes/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          }
        ]
      }
    ],
    "currentPage": 1,
    "totalPages": 21,
    "totalItems": 41,
    "itemsPerPage": 2
  }
}
```

##### **Caching:**
- The endpoint checks for cached data using a key based on the store URL, page number, and results per page. If cached data is available, it returns that data instead of querying again.

#### 6. **`GET /store/info`**
-   **Description**: This endpoint retrieves detailed information about a specified store based on its URL. It employs caching to enhance performance by storing and reusing data from previous requests.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `storeUrl`  | string   | `-` | The URL of the store whose information is to be fetched | Yes       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/info?storeUrl=https%3A%2F%2Fyummycupcakes.com%2F', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "data": {
    "title": "Gourmet Cupcakes, Cupcake in a Jar - Yummy Cupcakes, Treats, Desserts",
    "site_name": "",
    "logo": "https://cdn11.bigcommerce.com/s-37dff/product_images/favicon.png",
    "description": "Since 2004, over 400 recipes of gourmet cupcakes and delicious cupcake specialty treats like our famous Cupcake-in-the-Jar created by Celebrity Chef Tiffini.",
    "platform": "bigcommerce.stencil",
    "creationDate": "2004",
    "totalProducts": 41,
    "image": "",
    "url": "https://www.yummycupcakes.com/",
    "socialMedia": [],
    "emails": [],
    "addresses": [],
    "phoneNumbers": []
  }
}
```

#### **Caching:**
- The endpoint checks if the store information is already cached using a key based on the store URL. If cached data is found, it returns that data instead of making a new request.

#### 7. **`GET /store/products/search`**
-   **Description**: This endpoint allows users to search for products within a specified store URL, providing pagination options for managing the number of results displayed per page. It also utilizes caching to enhance performance by storing previously fetched search results.

-   **Parameters**:

| Parameter | Type   | Default   | Description                                                | Required |
|-----------|--------|-----------|------------------------------------------------------------|----------|
| `storeUrl`| string | `-`      | The URL of the store to search for products                | Yes      |
| `query`   | string | `-`       | The search term to filter products                         | Yes      |
| `page`    | string | `1`       | Specifies the page number for paginated results            | No       |
| `perPage` | string | `10`      | Specifies the number of results per page (max value: 15)   | No       |


Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/products?storeUrl=https%3A%2F%2Fyummycupcakes.com%2F&query=cup', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "data": {
    "products": [
      {
        "productId": "234",
        "title": "Edible Biscoff Cookie Dough",
        "mainImage": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/234/690/Cookie_Dough_2__87116.1730053234.jpg?c=2",
        "images": [
          {
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/234/690/Cookie_Dough_2__87116.1730053234.jpg?c=2",
            "alt": "Edible Biscoff Cookie Dough"
          }
        ],
        "description": "EDIBLE COOKIE DOUGH IS SUCH A GREAT TREAT!!!\nScoops of fresh made edible Biscoff cookie dough...with lots of Biscoff cookie pieces!  It's ready to eat.  Served in a colorful paper cup with lid and spoon so you are ready to eat and love it.  You can put in the frig so you can enjoy all week...or...come into the Bakeshop and get another cup.\nTry the Chocolate Chip cookie dough too!\nGreat dessert break for afternoon meetings, fun to serve at parties, look great on your dessert table, or a treat just for you!\n \nFor large quantity orders, you can also call us directly at 818.558.1080.",
        "reviewsCount": "(No reviews yet)",
        "prices": {
          "sku": null,
          "upc": null,
          "mpn": null,
          "gtin": null,
          "weight": null,
          "base": true,
          "image": null,
          "price": {
            "with_tax": {
              "formatted": "$5.75",
              "value": 5.75,
              "currency": "USD"
            },
            "tax_label": "Tax"
          },
          "out_of_stock_behavior": "hide_option",
          "out_of_stock_message": "Out of stock",
          "available_modifier_values": [],
          "in_stock_attributes": [],
          "stock": null,
          "instock": true,
          "stock_message": null,
          "purchasable": true,
          "purchasing_message": null
        },
        "attributes": [
          {
            "label": "Pick Up Date [Tue-Sat] (24 hours in advance):",
            "options": [
              {
                "value": "1",
                "text": "\n                Jan\n            "
              },
              {
                "value": "2",
                "text": "\n                Feb\n            "
              },
              ...
            ]
          },
          {
            "label": "",
            "options": [
              {
                "value": "1",
                "text": "\n                1\n            "
              },
              {
                "value": "2",
                "text": "\n                2\n            "
              },
              {
                "value": "3",
                "text": "\n                3\n            "
              },
              ...
            ]
          },
          ...
        ],
        "variantsProducts": [
          {
            "name": "Edible Choc Chip Cookie Dough",
            "price": "$5.75",
            "url": "https://yummycupcakes.com/edible-choc-chip-cookie-dough/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "Sugar Cookie",
            "price": "$3.00",
            "url": "https://yummycupcakes.com/sugar-cookie/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "Choc Chip/Oat/Sea Salt Cookie",
            "price": "$3.00",
            "url": "https://yummycupcakes.com/choc-chip-oat-sea-salt-cookie/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          }
        ]
      },
      {
        "productId": "142",
        "title": "CLASSIC CUPCAKES - 6 BOX",
        "mainImage": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/415/Cupcakes_6_R2__57429.1591753152.jpg?c=2",
        "images": [
          {
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/415/Cupcakes_6_R2__57429.1591753152.jpg?c=2",
            "alt": "CLASSIC CUPCAKES - 6 BOX"
          },
          {
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/images/stencil/500x659/products/142/616/Classic_6_Box_copy__99326.1677977252.jpg?c=2",
            "alt": "CLASSIC CUPCAKES - 6 BOX"
          }
        ],
        "description": "CUSTOM CUPCAKE 6 PACK\nIt is always fun to create your very own, custom designed collection! Build your 6 pack from a list of traditional and unique artisanal flavor combinations from our menu. You can choose 6 different flavors or all of one flavor. . . that's the beauty. It will become your custom collection so it is sure to be a hit!\nWe do not ship these cupcakes.  For a delicious treat you can ship, please order the Cupcake in a Jar.",
        "reviewsCount": "(No reviews yet)",
        "prices": {
          "sku": null,
          "upc": null,
          "mpn": null,
          "gtin": null,
          "weight": null,
          "base": true,
          "image": null,
          "price": {
            "with_tax": {
              "formatted": "$25.50",
              "value": 25.5,
              "currency": "USD"
            },
            "tax_label": "Tax"
          },
          "out_of_stock_behavior": "hide_option",
          "out_of_stock_message": "Out of stock",
          "available_modifier_values": [
            4125,
            4158,
            3927,
            3928,
            4159,
            ...
          ],
          "stock": null,
          "instock": true,
          "stock_message": null,
          "purchasable": true,
          "purchasing_message": null
        },
        "attributes": [
          {
            "label": "Flavor 1",
            "options": [
              {
                "value": "4125",
                "text": "Black Forrest (until Nov 3)"
              },
              {
                "value": "4158",
                "text": "Blackout (until Nov 3)"
              },
              ...
            ]
          },
          ...
        ],
        "variantsProducts": [
          {
            "name": "CLASSIC CUPCAKES - 4 BOX",
            "price": "$17.00",
            "url": "https://yummycupcakes.com/classic-cupcakes-4-box/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "BIRTHDAY CUPCAKES - 6 BOX",
            "price": "$28.50",
            "url": "https://yummycupcakes.com/birthday-cupcakes-6-box/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "CHEF'S CHOICE CUPCAKES - 6 BOX",
            "price": "$25.50",
            "url": "https://yummycupcakes.com/chefs-choice-cupcakes-6-box/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "SPECIALTY BIRTHDAY CUPCAKES - 6 BOX",
            "price": "$30.00",
            "url": "https://yummycupcakes.com/specialty-birthday-cupcakes-6-box/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "CLASSIC CUPCAKE IN A JAR 4 BOX - PICK UP",
            "price": "$39.39",
            "url": "https://yummycupcakes.com/classic-cupcake-in-a-jar-4-box-pick-up/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "CLASSIC CUPCAKES - DOZEN",
            "price": "$49.00",
            "url": "https://yummycupcakes.com/classic-cupcakes-dozen/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "INDIVIDUAL CLASSIC CUPCAKE",
            "price": "$4.75",
            "url": "https://yummycupcakes.com/individual-classic-cupcake/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "SPECIALTY ASSTD CUPCAKE 6 BOX (Vegan, GL, GLV)",
            "price": "$27.00",
            "url": "https://yummycupcakes.com/specialty-asstd-cupcake-6-box-vegan-gl-glv/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          },
          {
            "name": "6 Months of Cupcakes!",
            "price": "$260.00",
            "url": "https://yummycupcakes.com/6-months-of-cupcakes/",
            "imageUrl": "https://cdn11.bigcommerce.com/s-37dff/stencil/6ea6b450-3a7c-0136-ad01-0242ac11001d/e/ba84b080-294b-013d-36ce-4e5b9fd5bd3a/img/loading.svg"
          }
        ]
      }
    ],
    "currentPage": 1,
    "totalPages": 21,
    "totalItems": 41,
    "itemsPerPage": 2
  }
}
```

#### **Caching:**
- The endpoint checks if the search results are already cached using a key based on the store URL, search query, page number, and results per page. If cached data is available, it returns that data instead of querying again.

#### 8. **`GET /store/contacts`**
-   **Description**: This endpoint retrieves personal contact information for a specified store based on its URL. It employs caching to improve performance by storing previously fetched contact details.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `storeUrl`  | string   | `-` | The URL of the store whose contact information is to be fetched | Yes       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/contacts?storeUrl=https%3A%2F%2Fyummycupcakes.com%2F', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "available_contacts": {
    "emails": [
      "t.soforenko@yummycupcakes.com",
      "victoria@yummycupcakes.com",
      "specialevents@yummycupcakes.com",
      "fanclub@yummycupcakes.com",
      "jobs@yummycupcakes.com",
      "marketing@yummycupcakes.com",
      "franchising@yummycupcakes.com",
      "bakingclasses@yummycupcakes.com",
      "feedback@yummycupcakes.com",
      "enjoy@yummycupcakes.com"
    ],
    "phones": [],
    "twitter": [
      "https://twitter.com/yummycupcakesla"
    ],
    "linkedIn": [
      "https://linkedin.com/company/yummy-cupcakes"
    ],
    "instagram": [
      "https://instagram.com/yummycupcakesla"
    ]
  }
}
```

##### **Caching:**
- The endpoint checks if the contact information is already cached using a key based on the store URL. If cached data is available, it returns that data instead of making a new request.

#### 9. **`GET /store/analytics`**
-   **Description**: This endpoint retrieves analytics data for a specified store based on its URL. It uses caching to enhance performance by storing previously fetched analytics data.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `storeUrl`  | string   | `-` | The URL of the store for which analytics data is to be fetched  | Yes       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/analytics?storeUrl=https%3A%2F%2Fyummycupcakes.com%2F', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "data": {
    "Version": 1,
    "SiteName": "yummycupcakes.com",
    "Description": "since 2004, over 400 recipes of gourmet cupcakes and delicious cupcake specialty treats like our famous cupcake-in-the-jar created by celebrity chef tiffini.",
    "TopCountryShares": [
      {
        "country": "United States of America",
        "countryCode": "US",
        "countryFlag": "https://purecatamphetamine.github.io/country-flag-icons/3x2/US.svg",
        "Value": 1.0000000000000002,
        "valueinPercentage": "100.00"
      }
    ],
    "Title": "gourmet cupcakes, cupcake in a jar - yummy cupcakes, treats, desserts",
    "Engagments": {
      "BounceRate": "0.3515636421952115",
      "Month": "9",
      "Year": "2024",
      "PagePerVisit": "3.411560032213198",
      "Visits": "774",
      "TimeOnSite": "129.32432045601655"
    },
    "EstimatedMonthlyVisits": {
      "2024-07-01": 8031,
      "2024-08-01": 1407,
      "2024-09-01": 774
    },
    "GlobalRank": {
      "Rank": 12029956
    },
    "CountryRank": {
      "Country": 840,
      "CountryCode": "US",
      "Rank": 3686317
    },
    "CategoryRank": {
      "Rank": "11733",
      "Category": "Food_and_Drink/Groceries"
    },
    "GlobalCategoryRank": null,
    "IsSmall": false,
    "Policy": 0,
    "TrafficSources": {
      "Social": 0.125597600307174,
      "Paid Referrals": 0.005913324339335878,
      "Mail": 0.00042349847277636755,
      "Referrals": 0.05542721509674998,
      "Search": 0.30757101390538155,
      "Direct": 0.5050673478785823
    },
    "Category": "food_and_drink/groceries",
    "LargeScreenshot": "https://site-images.similarcdn.com/image?url=yummycupcakes.com&t=1&s=1&h=28e1e78291bb2540d3a62cda45b8cbe152395ddee6236c3ceb653dff50bb09f0",
    "IsDataFromGa": false,
    "Countries": [
      {
        "Code": "AF",
        "UrlCode": "afghanistan",
        "Name": "Afghanistan"
      },
      {
        "Code": "AX",
        "UrlCode": "land-islands",
        "Name": "Åland Islands"
      },
      {
        "Code": "AL",
        "UrlCode": "albania",
        "Name": "Albania"
      },
      ...
    ],
    "Competitors": {
      "TopSimilarityCompetitors": []
    },
    "Notification": {
      "Content": null
    },
    "TopKeywords": [],
    "SnapshotDate": "2024-09-01T00:00:00+00:00"
  }
}
```

##### **Caching:**
- The endpoint checks if the analytics data is already cached using a key based on the store URL. If cached data is available, it returns that data instead of making a new request.


#### 10. **`GET /store/analyticsv2`**
-   **Description**: This endpoint retrieves enhanced analytics data for a specified store based on its URL. It employs caching to improve performance by storing previously fetched analytics data.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `storeUrl`  | string   | `-` | The URL of the store for which analytics data is to be fetched  | Yes       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/analyticsv2?storeUrl=https%3A%2F%2Fyummycupcakes.com%2F', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "data": {
    "domainName": "yummycupcakes",
    "image": "https://site-images.similarcdn.com/image?url=yummycupcakes.com&t=0&s=1&h=28e1e78291bb2540d3a62cda45b8cbe152395ddee6236c3ceb653dff50bb09f0",
    "icon": "https://site-images.similarcdn.com/image?url=yummycupcakes.com&t=2&s=1&h=28e1e78291bb2540d3a62cda45b8cbe152395ddee6236c3ceb653dff50bb09f0",
    "imageLarge": "https://site-images.similarcdn.com/image?url=yummycupcakes.com&t=1&s=1&h=28e1e78291bb2540d3a62cda45b8cbe152395ddee6236c3ceb653dff50bb09f0",
    "title": "gourmet cupcakes, cupcake in a jar - yummy cupcakes, treats, desserts",
    "domain": "yummycupcakes",
    "isSubDomain": false,
    "yearFounded": "2004",
    "employeeRange": "10 - 50",
    "engagementOverview": null,
    "trafficRanks": {},
    "topCountries": [
      {
        "country": "United States of America",
        "countryCode": "US",
        "countryFlag": "https://purecatamphetamine.github.io/country-flag-icons/3x2/US.svg",
        "Value": 1.0000000000000002,
        "valueinPercentage": "100.00"
      }
    ],
    "genderDistribution": {},
    "audienceInterest": {},
    "competitors": [
      {
        "Category": "Food_and_Drink~Groceries",
        "Affinity": 1,
        "Domain": "sweetesbakeshop.com",
        "Rank": 656948,
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=sweetesbakeshop.com&t=2&s=0&h=7665b7e25c408f0fbda7de0b2aea57dd5abb512a137fa8fb0c261fb02fc783d8"
      },
      {
        "Category": "Food_and_Drink~Groceries",
        "Affinity": 0.836736032278002,
        "Domain": "pacificcookie.com",
        "Rank": 3065480,
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=pacificcookie.com&t=2&s=0&h=103bcdba7ea6678e3c95d250f8aa66775dbda53631734fcd3cfaeef815087697"
      },
      {
        "Category": "Food_and_Drink~Groceries",
        "Affinity": 0.8129286283766082,
        "Domain": "bakednyc.com",
        "Rank": 4034351,
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=bakednyc.com&t=2&s=0&h=25ce56c6ca87088d443a5dd53752dacec20a4a2c7e2c4d2be4711b167fdf02e1"
      },
      {
        "Category": "Food_and_Drink~Groceries",
        "Affinity": 0.7457109930166904,
        "Domain": "famouscookies.com",
        "Rank": 2613827,
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=famouscookies.com&t=2&s=0&h=0d904f83ea0a60d2a03ab56529a474a852771111a57f4bd0fa0b6ad8bcb3b021"
      },
      {
        "Category": "Food_and_Drink~Restaurants_and_Delivery",
        "Affinity": 0.5924755339406735,
        "Domain": "sprinkles.com",
        "Rank": 297940,
        "HasAdsense": true,
        "Favicon": "https://site-images.similarcdn.com/image?url=sprinkles.com&t=2&s=0&h=73804257e4f86d7bc9bea61b9e9c7611598b37243fcf7684537908d3c31854be"
      },
      {
        "Category": "Food_and_Drink~Groceries",
        "Affinity": 0.5720517016203526,
        "Domain": "sweetlorens.com",
        "Rank": 778277,
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=sweetlorens.com&t=2&s=0&h=faa0fd1ff7b9c3abd3a3dc1a6e39b798c2502b299ea575c0d428b7a1f38b42a3"
      },
      {
        "Category": "Food_and_Drink~Restaurants_and_Delivery",
        "Affinity": 0.5512822640938946,
        "Domain": "sweetcupcakes.com",
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=sweetcupcakes.com&t=2&s=0&h=4e81ef6ab5b7d9b110fc5f35784e1e7351fa0c5b05d52ce35567632000e8c4cc"
      },
      {
        "Category": "Food_and_Drink~Food_and_Drink",
        "Affinity": 0.5512822640938946,
        "Domain": "dangerouspies.com",
        "Rank": 5174926,
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=dangerouspies.com&t=2&s=0&h=2ac5bf931113bf87e58b6621809183c347259d23fc67779815a836ecfd0dec22"
      },
      {
        "Category": "Food_and_Drink~Restaurants_and_Delivery",
        "Affinity": 0.5382204343904222,
        "Domain": "vanillabakeshop.com",
        "Rank": 10217884,
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=vanillabakeshop.com&t=2&s=0&h=06954d5abfe8c63b52246981a1e24a44fea0afad8884e6eb88fb23f0472fe004"
      },
      {
        "Category": "Food_and_Drink~Restaurants_and_Delivery",
        "Affinity": 0.5371078551657489,
        "Domain": "bakehouse46.com",
        "Rank": 2163300,
        "HasAdsense": false,
        "Favicon": "https://site-images.similarcdn.com/image?url=bakehouse46.com&t=2&s=0&h=d2caf9e39850f796cba54eeb57d06e320ca627cf12e06954922720b86430c900"
      }
    ],
    "organicCompetitors": [],
    "socialMediaTraffic": [],
    "topLinkDestination": [],
    "topAdNetwork": [],
    "topAdsDestination": [],
    "topReferingIndustry": [],
    "topReferrer": [],
    "topkeywordWorldWide": [],
    "paidSearch": []
  }
}
```
##### **Caching:**
The endpoint checks if the analytics data is already cached using a key based on the store URL. If cached data is available, it returns that data instead of making a new request.

#### 11. **`GET /store/competitors`**
-   **Description**: This endpoint retrieves competitor data for a specified store using SemRush. It allows users to set a limit on the number of competitors returned and employs caching to enhance performance by storing previously fetched data.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `storeUrl`  | string   | `-` | The URL of the store for which analytics data is to be fetched  | Yes       |
| `limit`  | string   | `10` | Specifies the maximum number of competitors to return  | No       |
	

Example request:
```javascript
fetch('https://bigcommerce-storeinsight-api.p.rapidapi.com/store/competitors?storeUrl=https%3A%2F%2Fyummycupcakes.com%2F&limit=2', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'bigcommerce-storeinsight-api.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```
Example response:
```json
{
  "data": [
    {
      "domainName": "sweetesbakeshop",
      "image": "https://site-images.similarcdn.com/image?url=sweetesbakeshop.com&t=0&s=1&h=7665b7e25c408f0fbda7de0b2aea57dd5abb512a137fa8fb0c261fb02fc783d8",
      "icon": "https://site-images.similarcdn.com/image?url=sweetesbakeshop.com&t=2&s=1&h=7665b7e25c408f0fbda7de0b2aea57dd5abb512a137fa8fb0c261fb02fc783d8",
      "imageLarge": "https://site-images.similarcdn.com/image?url=sweetesbakeshop.com&t=1&s=1&h=7665b7e25c408f0fbda7de0b2aea57dd5abb512a137fa8fb0c261fb02fc783d8",
      "title": "sweet e's bake shop | logo cookies and celebration cakes",
      "domain": "sweetesbakeshop",
      "isSubDomain": false,
      "yearFounded": "2009",
      "employeeRange": "10 - 50",
      "monthlyVisits": 37093.175233167734,
      "rankings": {
        "globalRanking": 656948,
        "highestTrafficCountryRanking": 142473,
        "categoryRanking": 3283
      },
      "category": "Food_and_Drink/Groceries",
      "url": "https://sweetesbakeshop.com"
    },
    {
      "domainName": "pacificcookie",
      "image": "https://site-images.similarcdn.com/image?url=pacificcookie.com&t=0&s=1&h=103bcdba7ea6678e3c95d250f8aa66775dbda53631734fcd3cfaeef815087697",
      "icon": "https://site-images.similarcdn.com/image?url=pacificcookie.com&t=2&s=1&h=103bcdba7ea6678e3c95d250f8aa66775dbda53631734fcd3cfaeef815087697",
      "imageLarge": "https://site-images.similarcdn.com/image?url=pacificcookie.com&t=1&s=1&h=103bcdba7ea6678e3c95d250f8aa66775dbda53631734fcd3cfaeef815087697",
      "title": "pacific cookie company | buy fresh gourmet cookies online, cookie gifts, and monthly cookie subscriptions",
      "domain": "pacificcookie",
      "isSubDomain": false,
      "yearFounded": "1980",
      "employeeRange": "10 - 50",
      "monthlyVisits": 5043.717266554649,
      "rankings": {
        "globalRanking": 3065480,
        "highestTrafficCountryRanking": 726492,
        "categoryRanking": 15742
      },
      "category": "Food_and_Drink/Groceries",
      "url": "https://pacificcookie.com"
    }
  ]
}
```

##### **Caching:**
- The endpoint checks if the competitors' data is already cached using a key based on the store URL and limit. If cached data is available, it returns that data instead of making a new request.

## Commonly Asked Questions

1. **What data can I access using the StoreInsight API?**  
   You can access a range of metrics including sales data, customer behavior analytics, product performance, and traffic insights for your BigCommerce store.

2. **How do I authenticate with the StoreInsight API?**  
   Authentication is done using the RapidAPI platform. You will need to obtain an access token using your client credentials.

3. **What endpoints are available in the StoreInsight API?**  
   The API provides various endpoints for retrieving analytics data, including endpoints for sales metrics, customer insights, product performance, and more.

4. **Is there a limit on the number of requests I can make to the API?**  
   Yes, the API has rate limits to ensure fair usage and performance. Be sure to check the API documentation for specific rate limit details.

5. **Can I integrate the StoreInsight API with other analytics tools?**  
   Absolutely! You can integrate data retrieved from the StoreInsight API with other analytics platforms and tools for more comprehensive data analysis.


## Error Handling
The  API returns standard HTTP status codes to indicate the success or failure of API requests. Below are common errors and suggestions for handling them.

|Status Code|Message|Description|Suggested Handling|
|--|--|--|--|
| **400** | Bad Request | The request was malformed or missing required parameters (e.g., `domain` parameter not provided). | Verify that all required parameters are included and correctly formatted. |
| **401** | Unauthorized | Invalid or missing API key in the request headers. | Check that a valid API key is included in `x-rapidapi-key`. |
| **403** | Forbidden | Access to the requested resource is denied, possibly due to rate limits or restricted access. | Review rate limits and ensure API permissions. Retry after a delay if rate limit exceeded. |
| **404** | Not Found | The requested domain information could not be found (e.g., domain does not exist). | Check the spelling or availability of the domain. |
| **429** | Too Many Requests | The API rate limit has been exceeded. | Implement rate-limiting logic and retry after the specified rate limit reset time. |
| **500** | Internal Server Error | A server error occurred while processing the request. | Retry the request after a few seconds. If the error persists, contact API support. |
| **503** | Service Unavailable | The API service is temporarily unavailable (e.g., due to maintenance). | Retry the request later or check the API status page for maintenance alerts. |
