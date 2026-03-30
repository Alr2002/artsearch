# Random Artwork

Get one random artwork from our vast collection. The API returns comprehensive details including the title, high-quality image URL, creation date range, and a rich description providing historical and artistic context.

## API call

Method - **GET**
```
https://api.artsearch.io/artworks/random?api-key={API_key}
```

## Required parameters

|Parameter|Required/Optional| Example | Description|
-----------|:-------:|:--:|:---------|
|[`api-key`][1] | required | abcd1234 | Your API key.  |

[1]: https://     "type: string"

## Example of API request 

Method - **GET**

```
https://api.artsearch.io/artworks/random?&api-key=API_key
```

### Test parameters for the query

|Parameter|Value|Description|
-----------|:-------:|-----------|
**`api-key`**| API_key | Your API key


!!! example "Examples of API requests for various languages"
    === "**cURL**"

        ```
        curl --location --globoff '{{baseUrl}}/artworks/random?api-key=<API key>' \
        --header 'Accept: application/json'
        ```

    === "**Python - http.Client**"

        ```py
        import http.client

        conn = http.client.HTTPSConnection("api.artsearch.io")
        payload = ''
        headers = {
        'Accept': 'application/json'
        }
        conn.request("GET", "/artworks/random?&api-key=<API key>", payload, headers)
        res = conn.getresponse()
        data = res.read()
        print(data.decode("utf-8"))
        ```

    === "**JavaScript-jQuery**"

        ```javascript
        var settings = {
        "url": "https://api.artsearch.io/artworks/random?api-key=<API Key>",
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

        url = URI("https://api.artsearch.io/artworks/random?api-key=<API Key>")

        https = Net::HTTP.new(url.host, url.port)
        https.use_ssl = true

        request = Net::HTTP::Get.new(url)
        request["Accept"] = "application/json"

        response = https.request(request)
        puts response.read_body
        ```

    === "**C#-HttpClient**"

        ```c#
        var client = new HttpClient();
        var request = new HttpRequestMessage(HttpMethod.Get, "https://api.artsearch.io/artworks/random?api-key=<API Key>)
        request.Headers.Add("Accept", "application/json");
        var response = await client.SendAsync(request);
        response.EnsureSuccessStatusCode();
        Console.WriteLine(await response.Content.ReadAsStringAsync());
        ```

## Example of API response

??? note "JSON"

    ``` json linenums="1"
    {
    "id": 25623857,
    "title": "Knightly Sword",
    "image": "https://img.artsearch.io/artworks/knightly_sword_unknown23_1450.jpg",
    "start_date": 1401,
    "end_date": 1450,
    "description": "The image depicts a knightly sword, a prominent weapon crafted between 1401 and 1450, showcasing the key characteristics of medieval armament. This sword features a long, tapered blade, designed for both cutting and thrusting, a hallmark of the period's martial needs. The blade is wide at the hilt and narrows sharply towards the tip, indicating a focus on agility and precision in combat. \n\nThe hilt is adorned with a distinctive crossguard that provides both defense and grip stability, crucial in the heat of battle. The grip is wrapped in dark leather, likely to ensure a strong hold, while the pommel, often an intricate element in knightly swords, features decorative detailing that may signify the sword's origin or the status of its owner. \n\nHistorically, this sword reflects the transition in European warfare and chivalric culture during the late Middle Ages, where such weaponry symbolized not only martial prowess but also nobility and honor in combat. It stands as a testament to the craftsmanship of the era, merging functionality with artistry, and provides insights into the socio-political dynamics of knighthood and warfare of the time."
    }
    ```

### Fields in API response     

|Parameter|Description|
|:-----------|:-----------|
**`id`** | The id of the artwork. |
**`title`** | The title of the artwork. |
**`image`** | Link to view an image of the artwork.  |
**`start_date`** | The start date.  |
**`end_date`** | The completion date.   |
**`description`** | Description of  the artwork.  |

## Response Headers

- **Content-Type**: application/json
- **X-API-Quota-Request**: The number of points used by the request
- **X-API-Quota-Used**: The number of points used in total today
- **X-API-Quota-Left**: The number of points left today (depends on your plan)

## Quotas
Calling this endpoint costs **1 request**