# Curl

Pull information from website. 
Can retrieve the html content of a page, or information from a rest api.
Can also post information.

## Basics

curl -[option] [url]
> curl https://google.com

Output in a file:
>curl -o output.html https://google.com

## Pushing data

You can push entry to a rest api with `POST` .

Use `-d` to specify the data (should be the format of the api).
`-h` to specify the format of the data.

> curl -d '{"name":"Bob","age":"23  "}' -H 'Content-Type:application/json' -X POST https://example.com/api/231/create

You can alse `update` or `delete` data.

[source](https://www.youtube.com/watch?v=-nnJ82uc2ic)
