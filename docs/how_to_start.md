# How to start

## Prerequisites

To start working with the Art Search API, register and log in to [your account](https://artsearch.io/console/). Then select your subscription plan and receive your API key.


## Authentication

Art Search API uses API key authentication. You can get a free one by simply [signing up here.](https://artsearch.io/console/).  
Once you have your API key, you have to put it in the request URL for every request you make like so `api-key`=**YOUR-API-KEY**.  
Alternatively, you can put the API key in the request header as `x-api-key`. 

## How to make an API call

1.	Pick a function (endpoint) such as [Search Artworks](https://artsearch.io/docs/search-artworks-api/) and then copy and paste the demo code in your development environment.
2.	Optional: Download an [SDK](https://artsearch.io/sdks/) for your language to use the API seamlessly.
3.	Optional: Play with all APIs by using the [Postman Collection](https://www.postman.com/spoonacular-api/workspace/art-search-api/collection/7431899-342abc51-7005-43a3-b88d-7499c69da460?action=share&creator=7431899).


## Base URL

`https://api.artsearch.io`

## Endpoints

### [Search Artworks](search_artworks.md)

`/artworks`

Search and filter artworks by query, creation time, material, technique, and origin. The natural language search uses semantic AI to understand the context of your query, so you can search for artworks by their style, subject, or even emotions they evoke. The API returns a list of artworks matching the given criteria.

### [Retrieve Artwork by Id](retrieve_artwork_by_id.md)

`/artworks/{id}`

Get one artwork by its id. The API returns the title, image URL, start and end date, and a description of the artwork.

### [Random Artwork](random_artwork.md)

`/artworks/random`

Get one random artwork from our vast collection. The API returns comprehensive details including the title, high-quality image URL, creation date range, and a rich description providing historical and artistic context.