# Authentication

### API key

To use the API you need an API key. You can get a free one by simply signing up [here](https://artsearch.io/console/).
Once you have your API key, you have to put it in the request URL for every request you make like so   
?api-key=**YOUR-API-KEY**.

!!! note "Attention"

    Only the first query parameter is prefixed with a ? (question mark), all subsequent ones will be prefixed with a & (ampersand). That is how URLs work and nothing related to our API. Here's a full example with two parameters api-key and query: https://api.artsearch.io/artworks?api-key=YOUR-API-KEY&query=paintings.
    Alternatively, you can put the API key in the request header as `x-api-key`.
