# Search Artworks

Search and filter artworks by query, creation time, material, technique, and origin. The natural language search uses semantic AI to understand the context of your query, so you can search for artworks by their style, subject, or even emotions they evoke. The API returns a list of artworks matching the given criteria.

## API call

Method - **GET**
```
https://api.artsearch.io/artworks?query=medieval+knights&earliest-start-date=1750&latest-start-date=1755&earliest-end-date=1751&latest-end-date=1760&min-ratio=0.8&max-ratio=1.5&type=painting&material=ivory&technique=etching&origin=Italy&offset=0&number=3&api-key={API_key}
```

## Required parameters

|Parameter|Required/Optional| Example | Description|
-----------|:-------:|:--:|:---------|
|[`query`][1] | optional | landscape paintings | The search query. | 
|[`earliest-start-date`][2] | optional | 1750 | The artwork must have been created after this date. |
|[`latest-start-date`][2] | optional | 1755 | The artwork must have been created before this date. |
|[`earliest-end-date`][2] | optional | 1751 | For artworks with a period of creation, the completion date must be after this date. |
|[`latest-end-date`][2] | optional | 1760 | For artworks with a period of creation, the completion date must be before this date. |
|[`min-ratio`][2] | optional | 0.8 | The minimum aspect ratio (width/height) the artwork image must have. |
|[`max-ratio`][2] | optional | 1.5 | The maximum aspect ratio (width/height) the artwork image must have. |
|[`type`][1] | optional | painting | The artwork type. Possible values are tapestry, collotype, collage, printmaking, cutting, digital_art, sculpture, metalwork, fragment, token, embroidery, painting, jewellery, print, ornament, photograph, statuette, furniture, needlework, drawing, miniature, tile, stereograph, calligraphy. |
|[`material`][1] | optional | ivory  | The art material used. Possible values are ferrous_lactate, ink, textile, metal, bronze, canvas, stone, reduced_iron, horn, stoneware, in_shell_walnuts, chalk, velvet, silver, charcoal, gold_leaf, candied_walnuts, porcelain, walnut_halves, jade, cotton, paint, ferrous_fumarate, graphite, cobalt, sandstone, plastic, walnut_pieces, clay, walnuts, cupric_sulfate, ivory, ferric_orthophosphate, earthenware, tin, pen, linen, mahogany, electrolytic_iron, silk, crayon, black_walnuts, brush, beech_wood, terracotta, glass, lead, brass, oil_paint, pencil, leather, gold, marble, watercolor, diamond, iron, ferrous_sulfate, walnut_halves_and_pieces, gouache, wool, ceramic, parchment, cork, limestone, copper_gluconate, paper, pastel, copper, cardboard, plant_material, oak, wood. |
|[`technique`][1] | optional | etching | The art technique used. Possible values are engraving, grinding, embroidering, etching, vitrification, gilding, lithography, knitting, cyanotype, silkscreen, woodcut, printing, drypoint, photolithography, weaving, sawing, casting, glassblowing, block_printing, photographing, forging. |
|[`origin`][1] | optional | Italy | The country or region of origin for the artwork. |
|[`offset`][2] | optional | 0  | The number of artworks to skip in range [0,1000].  |
|[`number`][2] | optional | 10 | The number of artworks to return in range [1,10].  |
|[`api-key`][1] | required | abcd1234 | Your API key.  |

[1]: https://     "type: string"
[2]: https://     "type: number"


## Example of API request 

Method - **GET**

```
https://api.artsearch.io/artworks?query=vermeer%2Cmilkmaid&earliest-start-date=1660&latest-start-date=1661&type=painting&api-key=API_key
```

### Test parameters for the query

|Parameter|Value|Description|
-----------|:-------:|-----------|
**`query`** | vermeer, milkmaid | The search query |
**`earliest-start-date`** | 1660 | The artwork must have been created after this date. |
**`latest-start-date`** | 1661 | The artwork must have been created before this date. |
**`type`** | painting | The artwork type. |
**`api-key`**| API_key | Your API key

 


!!! example "Examples of API requests for various languages"
    === "**cURL**"

        ```
        curl --location 'https://api.artsearch.io/artworks?query=vermeer%2Cmilkmaid&earliest-start-date=1660&latest-start-date=1661&type=painting&api-key=API_key' \
        --header 'Accept: application/json'
        ```

    === "**Python - Http Client**"

        ```py
        import http.client
        conn = http.client.HTTPSConnection("api.artsearch.io")
        payload = ''
        headers = {
        'Accept': 'application/json'
        }
        conn.request("GET", "/artworks?query=vermeer,milkmaid&earliest-start-date=1660&latest-start-date=1661&type=painting&api-key=API_key", payload, headers)
        res = conn.getresponse()
        data = res.read()
        print(data.decode("utf-8"))
        ```

    === "**JavaScript-JQuery**"

        ```javascript
        var settings = {
        "url": "https://api.artsearch.io/artworks?query=vermeer,milkmaid&earliest-start-date=1660&latest-start-date=1661&type=painting&api-key=API_key",
        "method": "GET",
        "timeout": 0,
        "headers": {
        "Accept": "application/json"
        },
        };

        $.ajax(settings).done(function (response) {
        console.log(response);
        });
        ```

    === "**Ruby - NET::HTTP**"

        ```ruby
        require "uri"
        require "net/http"

        url = URI("https://api.artsearch.io/artworks?query=vermeer,milkmaid&earliest-start-date=1660&latest-start-date=1661&type=painting&api-key=API_key")

        https = Net::HTTP.new(url.host, url.port)
        https.use_ssl = true
        request = Net::HTTP::Get.new(url)
        request["Accept"] = "application/json"
        response = https.request(request)
        puts response.read_body
        ```

## Example of API response

??? note "JSON"

    ``` json linenums="1"
    {
    "available": 2,
    "number": 10,
    "offset": 0,
    "artworks": [
        {
            "id": 25896332,
            "title": "The Milkmaid",
            "image": "https://img.artsearch.io/artworks/the_milkmaid_johannes_vermeer_1660.jpg"
        },
        {
            "id": 25322630,
            "title": "A Mother giving her Child the Breast",
            "image": "https://img.artsearch.io/artworks/a_mother_giving_her_child_the_breast_domenicus_van_tol_1676.jpg"
        }
    ]
    }
    ```

### Fields in API response

|Parameter|Description|
|:-----------|:-----------|
**`available`** | The number of artworks matching the search query.  |
**`number`** | The number of artworks to return in range. |
**`offset`** | The number of artworks to skip in range.  |
**`artworks`** |    |
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`artworks.id`** | The Id of the artwork.   |
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`artworks.title`** | The title of the artwork.   |
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**`artworks.image`** | Link to view an image of the artwork.   |

## Response Headers

- **Content-Type**: application/json
- **X-API-Quota-Request**: The number of points used by the request
- **X-API-Quota-Used**: The number of points used in total today
- **X-API-Quota-Left**: The number of points left today (depends on your plan)

## Quotas
Calling this endpoint costs **1 request**

