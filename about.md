---
layout: page
title: Me in a Nutshell
---

<style>
.button--nav {
  color: #202A4F;
}
.footer {
  background-color:#202A4F;
}
.footer a {
  color: white;
}
.footer small {
  color: white;
}
a {
  color:#202A4F;
}
.bio-container {
  display: flex;
  flex-flow: row wrap;
}
.bio {
  text-align: left;
}
.text {
  padding-right: 2%;
  width: 100%;
  float: right;
}
.image {
  width: 42%;
  margin-right:2%;
}
</style>

{% if jekyll.environment == 'production' %}
{% include analytics.html %}
{% endif %}

<div class='bio-container'>
  <span class='bio text'>
    <img src='/assets/me_irl.jpg' class='image' align='left' HSPACE="50px"/>
    <p style='margin-bottom:0; text-align: justify; text-justify: inter-word;'>
    &nbsp;&nbsp;&nbsp;&nbsp;Hey! I am Egemen Sert, an Electrical and Electronics Engineering senior at METU.
    My skills are focused on Machine Intelligence and Data Science. I am interested in
    transforming unstructured data into structured format, analyzing
    structured data to extract information, and controlling systems with either
    traditional approaches or Reinforcement Learning. Projects are focused on analyzing
    human systems. Take a look at my analysis on Turkish <a href='/politics/turkey/2019/08/26/characterizing-political-participation/'>Political Variety</a>. <br/><br/>
    &nbsp;&nbsp;Aside from research, I love exploring the world by traveling,
    learning the languages and observing the cultures. We interact with so many cultures in myriad ways. Check out this <a href='https://qz.com/1176962/map-how-the-word-tea-spread-over-land-and-sea-to-conquer-the-world/'>Quartz post</a>.
    <img src='/assets/beento.png' class='image' align='right' width="350" style='margin-left: 10px'/>
    </p>
    <p style='text-align: justify; text-justify: inter-word;'>
    &nbsp;&nbsp;&nbsp;&nbsp;In a nutshell, I love meddling with data to extract insights and explore the world. Shared a choropleth map of the places I've been to, colored in navy blue. If you have any projects regarding data of the countries (especially in gray), please reach me at egemen[dot]sert[at]metu[dot]edu[dot]tr. Also, <a href='https://scholar.google.com.tr/citations?user=18w61Q8AAAAJ&hl=tr&oi=ao'>here</a> is my Google Scholar page and below is my short resume:
    </p>
     <img src='/assets/infogram_2.png'/>

  </span>
</div>
