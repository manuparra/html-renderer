# Puppeteer scrapping API with Docker

##  Start server using docker
`docker run -d --name renderer -p 8080:3000 manuparra/puppeteer-renderer`

## Test 

*(If service loaded in 8080 port, change {port} by 8080 or whatever you use)*

- Input URL in a web browser:   `http://localhost:{port}/?url=https://www.google.com`
- With `wget` or command line tools:  `wget -O output.html "http://localhost:{port}/?url=https://www.google.com"`

## API for the service:

| Name    | Required | Value               | Description            |Usage                                                         |
|---------|:--------:|:-------------------:|------------------------|--------------------------------------------------------------|
|`url`    | yes      |                     |Target URL              |`http://localhost:{port}/?url=http://www.google.com`         |
|`type`   |          |`pdf` or `screenshot`|Rendering another type. |`http://localhost:{port}/?url=http://www.google.com&type=pdf`|
|(Extra options)|    |                     |Extra options (see [puppeteer API doc](https://github.com/GoogleChrome/puppeteer/blob/v1.1.0/docs/api.md#pagepdfoptions)) |`http://localhost:{port}/?url=http://www.google.com&type=pdf&scale=2`|
