# Stardate-Hugo

Returns date in Star Trek's Star Date format, for Hugo-powered sites.

This repo provides a Hugo [partial](https://gohugo.io/templates/partials/) file for calculating stardate.

This script doesn't account hour, minute and seconds, just considers day / month and year.

## Some Example Dates

|Earth Date (YYYY-MM-DD)|Star Date|
|---|---|
|1966-09-08*|-356394.52|
|2024-05-14|-298631.14|
|2323-01-01|0|

*First air date of Star Trek TOS.

## Usage

1. Standalone Usage, you should pass an object with Go's Time format. For example when you define a Date variable in your markdown file's frontmatter like `Date: 2024-05-14
` you'll have a Go-Time format.

```go
{{- partial "stardate.html" (dict "date" .Date) -}}
```

2. You can get the stardate as a parameter, and use in your template;

```go
{{- $stardate := partial "stardate.html" (dict "date" .Date) -}}
```

3. Here's an example of using it in a theme;

```go
{{- $stardate := partial "stardate.html" (dict "date" .Date) -}}

{{- $scratch.Add "meta" (printf "<span>Stardate: %s</span>" $stardate) }}
```


## Credits

This project is re-written from the project [nmalinowski/stardate-go](https://github.com/nmalinowski/stardate-go)

