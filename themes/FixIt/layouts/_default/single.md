{{- $params := .Scratch.Get "params" -}}
{{- $author := .Site.Params.author | merge (dict "name" "Anonymous" "link" (default "" $params.authorlink)) -}}
{{- if isset $params "author" | and (ne $params.author .Site.Params.author.name) -}}
  {{- $author = dict "name" $params.author | merge $author -}}
  {{- $author = dict "link" (default "" $params.authorlink) | merge $author -}}
{{- end -}}
# {{ .Title }}

{{ if $params.password -}}
  ***{{ T "single.encryptedAbstract" }}***
{{- else -}}
  {{ .RawContent | replaceRE "\n?{{% fixit-encryptor .+ %}}((\n|.)*){{% /fixit-encryptor %}}\n?" "" }}
{{- end }}

---

> {{ T "single.author"}}: {{ with $author.link }}[{{ $author.name }}]({{ . }}){{ else }}{{ $author.name }}{{ end }}  
> URL: {{ .Permalink }}  
{{ if $params.repost.enable | and (hasPrefix $params.repost.url "http") }}> {{ T "single.repost" }} URL: {{ $params.repost.url }}{{ end }}
