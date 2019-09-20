# Puppeteer scrapping API with Docker

This repository allows you to launch a docker service that serves as a proxy to obtain websites or webpages simulating Chrome/Chromium as an agent. The result is generated in an image, PDF or HTML according to the API parameters provided.

##  Start server using docker
`docker run -d --name renderer -p 8080:3000 manuparra/puppeteer-renderer`

## Test - Extract HTML processed code for a website:

*(If service loaded in 8080 port, change {port} by 8080 or whatever you use)*

- Input URL in a web browser:   `http://localhost:{port}/?url=https://www.google.com`
- With `wget` or command line tools:  `wget -O output.html "http://localhost:{port}/?url=https://www.google.com"`

## Test - Print PDF of the website/webpage:

*(If service loaded in 8080 port, change {port} by 8080 or whatever you use)*

- Input URL in a web browser:   `http://localhost:{port}/?url=https://www.google.com&type=pdf`
- With `wget` or command line tools:  `wget -O output.pdf "http://localhost:{port}/?url=https://www.google.com&type=pdf"`

## URL params encoded

If the URL contains special characters or in this case if the URL contains a URL with a website queryset, it is necessary to send the encoded URL:

- for the URL: https://www.cv-library.co.uk/search-jobs?geo=Milton+Keynes&distance=50 the API call will be:

  - With `wget` or command line tools:  `wget -O output.pdf "http://localhost:{port}/?url=https%3A%2F%2Fwww.cv-library.co.uk%2Fsearch-jobs%3Fgeo%3DMilton%2BKeynes%26distance%3D50"`



## API for the service:

| Name    | Required | Value               | Description            |Usage                                                         |
|---------|:--------:|:-------------------:|------------------------|--------------------------------------------------------------|
|`url`    | yes      |                     |Target URL              |`http://localhost:{port}/?url=http://www.google.com`         |
|`type`   |          |`pdf` or `screenshot`|Rendering another type. |`http://localhost:{port}/?url=http://www.google.com&type=pdf`|
|(Extra options)|    |                     |Extra options (see [puppeteer API doc](https://github.com/GoogleChrome/puppeteer/blob/v1.1.0/docs/api.md#pagepdfoptions)) |`http://localhost:{port}/?url=http://www.google.com&type=pdf&scale=2`|
