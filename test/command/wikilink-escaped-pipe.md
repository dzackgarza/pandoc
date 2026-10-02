A backslash before the pipe of a wikilink in a pipe table cell escapes the
pipe from the cell and belongs to neither the target nor the title.

```
% pandoc -f markdown+wikilinks_title_after_pipe -t html
| a | b |
|---|---|
| [[target\|label]] | x |
^D
<table>
<thead>
<tr>
<th>a</th>
<th>b</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="target" class="wikilink">label</a></td>
<td>x</td>
</tr>
</tbody>
</table>
```

```
% pandoc -f markdown+wikilinks_title_before_pipe -t html
[[label\|target]]
^D
<p><a href="target" class="wikilink">label</a></p>
```
