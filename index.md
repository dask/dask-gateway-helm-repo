<html>
<body>

<p>See installation instructions at:</p>

<ul>
<li><a href="https://gateway.dask.org/install-kube.html">Dask-Gateway Kubernetes Installation</a></li>
</ul>

<h2>Stable releases</h2>
{% assign dask-gateway = site.data.index.entries.dask-gateway | sort: 'created' | reverse %}
{% assign all_charts = dask-gateway %}
<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in all_charts %}
    {% unless chart.version contains "-" %}
    <tr>
      <td>
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version }}
      </a>
      </td>
      <td>
      <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
    {% endunless %}
  {% endfor %}
</table>

<h2>Development releases</h2>
<table>
  <tr>
    <th>release</th>
    <th>date</th>
  </tr>
  {% for chart in dask-gateway %}
    <tr>
      <td>
      {% unless chart.version contains "-" %}<b>{% endunless %}
      <a href="{{ chart.urls[0] }}">
          {{ chart.name }}-{{ chart.version }}
      </a>
      {% unless chart.version contains "-" %}</b>{% endunless %}
      </td>
      <td>
      <span class='date'>{{ chart.created | date_to_rfc822 }}</span>
      </td>
    </tr>
  {% endfor %}
</table>
</body>
</html>

