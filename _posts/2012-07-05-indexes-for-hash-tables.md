---
category: learn
layout: learn
title: Indexes for hash tables
prev_section: default-values-for-dictionaries
next_section: attributes
---

The asterisk `*` syntax is short-hand for a specific use in another of L20n's features: indexes (discussing the asterisk here doesn't make a lot of sense because it's not revisited in the example).

When the entity's value is a dictionary, an index (`["short"]` below) can be added to it to indicate which key of the dictionary should be returned.

<div class="editor sourceEditor height15"
  id="sourceEditor1"
  data-source="sourceEditor1"
  data-output="output1"
>&lt;name["short"] {
  short: "Twitter",
  long: "Twitter Mobile Client"
}&gt;
&lt;about "About {% raw %}{{ name }}{% endraw %}"&gt;
&lt;licensing "{% raw %}{{ name.long }}{% endraw %} is both free and open-source."&gt;
</div>
<dl id="output1">
</dl>

You can get much more creative in indexes and put expressions in them, too (see <a href="{% post_url 2012-07-10-expressions %}">Chapter 10</a>).

If you nest dictionaries, you can define multivalued indexes.

<div class="editor sourceEditor height15"
  id="sourceEditor2"
  data-source="sourceEditor2"
  data-output="output2"
>&lt;name["short", "nominative"] {
  short: {
    nominative: "Loki",
    genitive: "Loki's"
  },
  long: "Loki Mobile Client"
}&gt;
&lt;about "About {% raw %}{{ name.short.nominative }}{% endraw %}"&gt;
&lt;license "{% raw %}{{ name.long }}{% endraw %} is open-source."&gt;
</div>
<dl id="output2">
</dl>