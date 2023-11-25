---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

{%- assign mp3s = site.static_files | where: "mp3", true -%}
{%- assign mp3Count = mp3s | size -%}

<div class="intro">
    <p>
    You've always wanted to say it out loud but never had the courage. 
    Confess here, anonymously and without fear of judgement.
    </p>
    <p>
    Call toll-free at <a href="tel:1-844-531-1664">1-844-531-1664</a> and let it all out. 
    New confessions are published daily.
    </p>
</div>

<div class="entry-container">
<div class="entry-header gothic">Bear Witness!</div>

{% for audio in site.data.audio %}
    {% assign audioKey = audio[0] %}
    {% assign audioData = audio[1] %}
    {% assign mediaPath = "/audio/mp3/"  | append: audioData.filename %}
    {% assign fileExists = site.static_files | where: "path", mediaPath | first %}
    {% if fileExists %}
        <div class="entry">
            <figure class="audio-figure">
                <audio controls src="{{ mediaPath }}" class="audio-player">
                    <a href="{{ mediaPath }}">Download audio</a>  
                </audio>
            </figure>
            <hr />
            <span class="recordingDate">{{ audioData.dateCreated | date: "%D" }}</span>
            <span class="reportLink"><a href="mailto:ianl4d+confessor@gmail.com?subject=Report on {{ audioKey }}">Report this confession</a></span>
        </div>
    {% endif %}
{% endfor %}
</div>

