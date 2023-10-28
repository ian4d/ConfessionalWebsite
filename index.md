---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

{%- assign mp3s = site.static_files | where: "mp3", true -%}
{%- assign mp3Count = mp3s | size -%}

<div class="intro">
    You've always wanted to say it out loud but never had the courage. 
    Confess here, anonymously and without fear of judgement. 
    Call toll-free at <a href="tel:1-844-531-1664">1-844-531-1664</a> and let it all out. 
    New confessions are published daily.
</div>

<div class="entry-container">
<div class="entry-header gothic">Bear Witness!</div>
{% for mp3 in mp3s %}
    <div class="entry">
        <figure class="audio-figure">
            <audio controls src="{{ mp3.path }}" class="audio-player">
                <a href="{{ mp3.path }}">Download audio</a>  
            </audio>
        </figure>
    </div>
{% endfor %}
</div>
