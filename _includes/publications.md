<h2 id="publications" style="margin: 2px 0px -15px;">Publications (Selected)</h2>

<div class="publications" markdown="0">
<ol class="pub-list" style="list-style:none;padding:0;margin-top:1.2rem;counter-reset:pub-counter;">

{% for pub in site.data.publications.main %}

<li style="counter-increment:pub-counter;margin-bottom:1rem;padding-left:2.4rem;position:relative;line-height:1.5;">
  <span style="position:absolute;left:0;top:0;font-weight:600;color:#043361;" class="pub-num">[{{ forloop.index }}]</span>
  <div class="pub-title" style="font-weight:600;font-size:0.97rem;">
    {% if pub.url and pub.url != "" %}
    <a href="{{ pub.url }}" target="_blank" rel="noopener" style="color:#043361;text-decoration:none;">{{ pub.title }}</a>
    {% else %}
    <span title="Accepted but not yet published" style="color:#043361;text-decoration:none;">{{ pub.title }}</span>
    {% endif %}
  </div>
  <div class="pub-authors" style="font-size:0.88rem;color:#555;margin-top:2px;">{{ pub.authors }}</div>
  <div class="pub-venue" style="font-size:0.85rem;color:#777;margin-top:1px;">
    <em>{{ pub.venue }}</em>&ensp;
    <span style="font-weight:600;color:#043361;">{{ pub.venue_short }}</span>
    {% if pub.venue_rank %}
    <span style="display:inline-block;background:#043361;color:#fff;font-size:0.7rem;font-weight:700;padding:1px 5px;border-radius:3px;vertical-align:middle;margin-left:4px;">{{ pub.venue_rank }}</span>
    {% endif %}
  </div>
  {% if pub.notes %}
  <div class="pub-notes" style="font-size:0.82rem;color:#e74d3c;margin-top:2px;"><strong><i>{{ pub.notes }}</i></strong></div>
  {% endif %}
</li>

{% endfor %}

</ol>
</div>

<!-- Dark mode tweaks -->
<style>
@media (prefers-color-scheme: dark) {
  .pub-num { color: #3eb7f0 !important; }
  .pub-title a { color: #3eb7f0 !important; }
  .pub-title a:hover { text-decoration: underline !important; }
  .pub-title span[title] { color: #3eb7f0 !important; border-bottom-color: #3eb7f0 !important; }
  .pub-authors { color: #bbb !important; }
  .pub-venue { color: #999 !important; }
  .pub-venue span[style*="background:#043361"] { background: #3eb7f0 !important; color: #111 !important; }
}
</style>
