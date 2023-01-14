---
title: Journals
---

We suggest to first contact the journal itself to report any issues. Many issues can be resolved with the assistance of the editor-in-chief or the data editor of the journal. We provide a (possibly incomplete) list of such reporting mechanisms. Some are specifically oriented towards replication packages, others may be a general feedback form.

<!-- Form to redirect to various journals -->
<!-- constructed from data in reporting.csv -->


<form class="journalselectorform">
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


<script>
  function redirectToJournal() {
    var journal = document.getElementById("journalSelector").value;
    if (journal != "none") {
      window.location = journal;
    }
  }
</script>
