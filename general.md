---
title: General
layout: withtable
---


In addition to or instead of the above direct contact with the journal, you may also want to publicly report the issue. The table below lists a few websites that handle these kinds of issues. 


  <!-- manually constructing table -->
  <!-- Website,URL,Description,Contributor,Lastdate-->
<table class="display">
  {% for row in site.data.alternate %}
    {% if forloop.first %}
    <thead>
    <tr>
      {% for cell in row %}
        {% if forloop.last %}
          {% continue %}
        {% else %}
        <th>{{ cell[0] }}</th>
        {% endif %}
      {% endfor %}
    </tr>
    </thead>
    {% endif %}

  <tr>
    <td> {{ row["Website"] }} </td>
    <td> <a href="{{ row["URL"] }}" alt="Link to Website">{{ row["URL"] }}</a></td>
    <td> {{ row["Description"] }}</td>
    <td class="contributor">{{ row["Contributed"] }}<br/>{{ row["Lastdate"] }}</td>
  </tr>
  {% endfor %}
</table>
