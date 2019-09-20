# Puppeteer scrapping API with Docker

##  Start server using docker
`docker run -d --name renderer -p 8080:3000 manuparra/puppeteer-renderer`

## Test 
- Input url  `http://localhost:{port}/?url=https://www.google.com`
- With wget:  `wget -O output.html "http://localhost:{port}/?url=https://www.google.com"`

## API for the service:

| Name    | Required | Value               | Description            |Usage                                                         |
|---------|:--------:|:-------------------:|------------------------|--------------------------------------------------------------|
|`url`    | yes      |                     |Target URL              |`http://puppeteer-renderer?url=http://www.google.com`         |
|`type`   |          |`pdf` or `screenshot`|Rendering another type. |`http://puppeteer-renderer?url=http://www.google.com&type=pdf`|
|(Extra options)|    |                     |Extra options (see [puppeteer API doc](https://github.com/GoogleChrome/puppeteer/blob/v1.1.0/docs/api.md#pagepdfoptions)) |`http://puppeteer-renderer?url=http://www.google.com&type=pdf&scale=2`|
