# curl Cheatsheet

Quick commands for HTTP requests, APIs, downloads, and debugging.

## GET

```sh
curl https://example.com
```

Follow redirects:

```sh
curl -L https://example.com
```

## Headers

Show response headers:

```sh
curl -i https://example.com
```

Headers only:

```sh
curl -I https://example.com
```

Send a header:

```sh
curl -H "Authorization: Bearer TOKEN" https://api.example.com
```

## POST

```sh
curl -X POST https://example.com
```

Send JSON:

```sh
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{"name":"nihit"}' \
  https://api.example.com
```

## Download

```sh
curl -O https://example.com/file.zip
```

Choose filename:

```sh
curl -o archive.zip https://example.com/file.zip
```

## Save Response

```sh
curl https://example.com -o response.html
```

## Upload File

```sh
curl -F "file=@example.txt" https://example.com/upload
```

## Authentication

```sh
curl -u username:password https://example.com
```

## Verbose

```sh
curl -v https://example.com
```

## Silent

```sh
curl -s https://example.com
```

Useful in scripts:

```sh
curl -fsSL https://example.com
```

Be careful when piping downloaded scripts directly into a shell. Inspect unfamiliar scripts first.
