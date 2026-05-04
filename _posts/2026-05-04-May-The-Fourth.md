---
layout: post
title: "May the Fourth Be With Your Data"
date: 2026-05-04
tags: [open science, open data]
---

Obi-Wan Kenobi famously described the Force as "an energy field created by all living things... it binds the galaxy together." In the modern scientific and civic enterprises - especially those driven by AI -  open data serves much the same purpose. When datasets are liberated from siloed archives and made freely accessible to the public, they create a shared infrastructure of knowledge. The force of open data binds our research, policymaking, journalism, and business communities together, enabling transparency, accelerating innovation, and allowing anyone equitable access to interrogate, validate, learn from, and build upon the work of others. 

Of course, like the Force in the Star Wars universe, there is a light-side and a dark-side to open data. The light side is represented by the benefits of increased transparency, replicability, accessibility, and equity that open data provide to society as a non-excludable public good. The dark side is represented by the use of open data for malfeasance - such as when bad-faith actors inappropriately use open data to identify individuals, threaten national security, and jeopardize data sovereignty in certain cultural contexts. When the principles of the collection and use of open data are stripped of ethical safeguards, it can be twisted into a tool for surveillance and manipulation rather than empowerment and innovation. So, let's continue to advocate for open data to remain on the light side of the force. 

# Star Wars Day 

To celebrate Star Wars Day this year, I wanted to showcase an example of what happens when data is shared openly, freely, and creatively (even many years after the fact). I also wanted to link my past work as social network analyst to my current work in information policy advocating for open data. Below is an interactive network projection mapping on-screen social interactions among Star Wars characters across all the episodes. This builds upon the work started by [Evelina Gabasova](https://evelinag.com/) on her [blog back in 2015](https://evelinag.com/blog/2015/12-15-star-wars-social-network/). The open data driving this visualization was meticulously compiled by Eve and made available via [her github repository here](https://github.com/evelinag/StarWars-social-network). I'm sure there are other Star Wars network analyses out there somewhere in a galaxy far far away - Eve's is the one I'm just most familiar with.  

<div class="map-container" style="margin: 20px 0;">
  <iframe 
    src="{{ '/assets/leaflets/starwars.html' | relative_url }}" 
    width="100%" 
    height="600px" 
    style="border: none; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);" 
    title="Star Wars Character On-Screen Interaction Network">
  </iframe>
</div>

## The Data and Methodology
This network visualization represents character interactions across the Star Wars films. In this network, each node (circle or other shape) represents a character (you can click on them to see who-is-who). The edges (the lines connecting them) represent onscreen interactions. Specifically, an interaction is defined as two characters speaking within the same scene. The thicker the edge, the more frequently those characters shared dialogue. 

I used a standard a Fruchterman-Reingold layout algorithm for this display. For those that care about these things, the layout simulates physical repulsion between nodes and attraction along edges. High-degree characters (those with the most connections, like R2-D2, Luke Skywalker, and C-3PO) naturally gravitate toward the center of their respective clusters, acting as the gravitational anchors of the story. For visual clarity, characters with an interaction degree greater than 50 are highlighted with user icons, while the size of each node scales dynamically with their overall interaction volume. Why 50? Well, I chose that arbitrarily so, why not? Importantly in this network, Darth Vader and Anakin Skywalker are treated as separate characters - again, that was an arbitrary decision I made. Also, I removed isolates by default because they can typically clog up the vis (in this case, I think there was only one "FIVE GOLD" but better safe than sorry). 

If you are unhappy with this decision, feel free [to adapt my code](https://github.com/cmarcum/talks-and-posts/blob/main/2026-05-04-May-The-Fourth/starwars-network.R) and make your own vis.
