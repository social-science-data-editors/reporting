---
title: Reporting failures to reproduce or incomplete replication packages
layout: withtable
---

This page will attempt to link to reporting mechanisms when readers of articles detect issues with replication packages. 

## Journal-specific reporting mechanisms

We suggest to first contact the journal itself to report any issues. Many issues can be resolved with the assistance of the editor-in-chief or the data editor of the journal. We provide a (possibly incomplete) list of such reporting mechanisms. Some are specifically oriented towards replication packages, others may be a general feedback form.

<!-- Form to redirect to various journals -->
<!-- constructed from data in reporting.csv -->


<form class="journalselector">
  <label for="journalSelector">Select a journal:</label>
  <select id="journalSelector" onchange="redirectToJournal()">
    <option value="none">--Select a journal--</option>
   
  {% for row in site.data.reporting %}
    {% if forloop.first %}
    <!-- values read from config -->
    {% endif %}
   <option value="{{ row["URL"] }}">{{ row["Name"] }}</option>
  {% endfor %}
  </select>
</form>


Also check the answers to the [survey conducted by the Institute for Replication](https://i4replication.org/publishing.html) about whether journals publish comments and replications. 

## General mechanisms

In addition to or instead of the above direct contact with the journal, you may also want to publicly report the issue. The table below lists a few websites that handle these kinds of issues. To suggest additional ones, please open an issue in the [underlying Github repository]({{ site.repository }}).


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

  <!-- manually constructing table -->
  <!-- Website,URL,Description,Contributor,Lastdate-->
  <tr>
    <td> {{ row["Website"] }} </td>
    <td> <a href="{{ row["URL"] }}" alt="Link to Website">{{ row["URL"] }}</a></td>
    <td> {{ row["Description"] }}</td>
    <td class="contributor">{{ row["Contributed"] }}<br/>{{ row["Lastdate"] }}</td>
  </tr>
  {% endfor %}
</table>

## License

All information provided on this page and in the corresponding [Github repository]({{ site.gitub }}) is available under a ![CC-BY-NC](assets/cc-by-nc.png) [CC-BY-NC license](https://creativecommons.org/licenses/by-nc/4.0/).


<script>
  function redirectToJournal() {
    var journal = document.getElementById("journalSelector").value;
    if (journal !== "none") {
      window.location = journal;
    }
  }
</script>
