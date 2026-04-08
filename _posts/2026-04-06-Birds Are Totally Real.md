---
layout: post
title: "Birds are Totally Real"
date: 2026-04-06
tags: [general, open science]
---

There are lots of forms of familial rebellion by members of a younger generation against their elders. Some dye their hair a devious color; some engage in risky behavior; and some go to art school. I rebelled by resisting birding. 

Birding is a multi-generational hobby that started with my grandfather, Dick Dionne, a couple of decades ago. You should check out his [incredible bird photographs here](https://pbase.com/redionne). When the family gets together, birding is often the activity. And that used to bug me. If you're not into birds, then birding is a slow, uneventful walk in the woods. There were many uneventful walks in the woods over the years - some that displaced other birdless plans that would have been more eventful. For years, I was disinterested and resisted the model behaviors of my kin: getting binoculars, upsizing camera lenses, and signing up for [eBird](https://www.ebird.org).

Then, in 2021, I turned 40. I have no idea what induced the change, but I found myself suddenly very interested in birds. I signed up for an [account on eBird](https://ebird.org/profile/Mjk2ODMxNQ/world). I asked my mother for a pair of binoculars for my birthday. I started reading books about birds (two of my faves include [The Evolution of Beauty by Richard Prum](https://en.wikipedia.org/wiki/The_Evolution_of_Beauty) and [Birding to Change the World by Trish O'Kane](https://www.aba.org/activism-and-hope-through-birds/)). I even started painting birds. Very recently, I spent a sum of money I probably should save for the mortgage on an upgraded lens - I think that's a birder's final form: carrying a cannon-sized canon (though, to be fair, mine's a Fuji). 
<img width="902" height="740" alt="A Baltimore Oriole painted by me in 2025" src="https://github.com/user-attachments/assets/748ff7ce-ee4c-4988-8797-f555e7b1823a" />
*Figure: a watercolor painting of a Baltimore oriole I painted in 2025.*

# The White House, Birding, and Open Science
2021 was also the year I agreed to join the Biden-Harris Administration to lead open science policy development at the White House Office of Science and Technology Policy. There is a harmony between open science and birding. I've already mentioned eBird twice above. eBird is a flagship online  platform for documenting birding observations and is provided by the [Cornell Lab of Ornithology](https://www.birds.cornell.edu/home/). It has become a global model for open science by building research infrastructures that make high‑quality biodiversity data freely accessible and is one of the world’s most successful examples of community science. eBird has enabled millions of participants to contribute standardized bird observations that are [openly shared for research](https://support.ebird.org/en/support/solutions/articles/48000838205/), conservation planning, and long‑term monitoring. Cornell’s approach demonstrates how open data and public participation can work together to produce scientific resources that are both deeply collaborative and broadly reusable. Because I worked to advance policies to make science more open and equitable, an app like eBird would have been appealing as a case-example even if I wasn't also deeply interested in birds. Of course, I submitted occasional birding lists to eBird from inside the White House campus. Here is a list of the species (common names) I encountered there:

 - American Black Duck
 - Blue Jay
 - Canada Goose
 - European Starling
 - Gray Catbird
 - House Sparrow
 - Mallard
 - Mourning Dove
 - Northern Cardinal
 - Northern Mockingbird
 - Peregrine Falcon
 - Red-shouldered Hawk
 - Red-tailed Hawk
 - Rock Pigeon (Feral Pigeon)
 - Song Sparrow
 - Tree Swallow

You'll note the absence of two birds associated with the White House: I never saw a Bald Eagle even flying over the complex and, while I did see six turkeys there for several pardoning ceremonies, they were captive and eBird doesn't accept those observations. 

There were quite a few fellow bird enthusiasts at the White House. During my subsequent tenure at the White House Office of Management Budget, I started an employee resource/interest group that I called the "Office of Migratory Birdbrains". The mostly intranet-based group was a loose collection of a few serious birders (one of my fellow OIRAns kept binoculars in his office) and many more typical bird fans that wouldn't be able to distinguish a sparrow from a female red-winged blackbird (I often can't). Former Director for Access Management at the National Security council, Michael David Thomas, became a bit of a birding celebrity in the Executive Office of the President for his diligence in documenting the mallard families in the courtyard of the New Executive Office Building (NEOB). For many years each spring, lineages of the ducks would set up seasonal residence to nest and raise their brood in the NEOB courtyard. I assume they kept coming back to take advantage of the shade, the fountain, the duck food put out by the General Services Administration, and probably the peace of mind provided by the security of the Secret Service. Michael, would often be stationed by the fountain early in the morning taking beautiful photographs of the ducklings. He circulated these on a distribution list (the Duckling Distro) which we birdbrains also celebrated and reshared. You can view a collection of Michael's [wonderful photos online here](https://www.icloud.com/sharedalbum/#B2J5FrPQ6qx5wH).

![DSCF4643](https://github.com/user-attachments/assets/d2c30aa0-4503-4dd4-a245-df8ea7b7ec14)
*Figure: a cute mallard duckling grooming its belly as photographed by Michael David Thomas in 2024 at the NEOB (shared with permission).*

# My 500th Birding List
This is the first April in four years that I have not gotten a chance to await the arrival of the ducklings in the NEOB. On the plus side, though, with my resignation from the White House last July, I've had a lot more opportunity to go birding and to contribute birding lists to eBird as a citizen scientist. Just this past week, I posted my 500th birding list. eBird not only provides the anonymized full observation dataset, the platform also allows contributors to download their own subset of that data. To mark the milestone of 500 submissions, I did some [analysis using R of my own data](https://github.com/cmarcum/talks-and-posts/tree/main/2026-04-06-Birds%20Are%20Totally%20Real) and I am happy to share the results here as a set of figures.

While I take pains to count every individual bird (in February, I counted every single one of 358 black-bellied whistling ducks at [Ollie's Pond in Charlotte, County Florida](https://ebird.org/checklist/S298932326)) there are a lot of guestimates and rounding errors in my data. So, these figures should be interpreted with that in mind. 

<img width="1126" height="672" alt="A lollipop plot showing the top-ten most frequently encountered and most abundant birds. The plot uses orange and blue feathers of lengths proportional to the values of each species, respectively, to illustrate the data." src="https://github.com/user-attachments/assets/f0db9909-741e-44cc-b3de-0f8d2f73e94e" />
*Figure: a lollipop barchart showing the top-ten most frequently encountered and most abundant birds. The plot uses orange and blue feathers with lengths proportional to the values of each set of the data, respectively.*

The first plot shows both the top-ten most frequently encountered (as a percent of my 500 lists) species as well as the top-ten species in terms of how many individuals I recorded seeing (abundance, per list). Not surprisingly, the two have considerable overlap. I see at least one Northern Cardinal (the most [stateliest bird](https://iere.org/what-is-the-most-common-state-bird/#:~:text=The%20Northern%20Cardinal%20is%20the%20most%20common%20state,made%20it%20a%20beloved%20symbol%20of%20several%20regions.)) nearly every-other-time I record a birding list on average. I'm a little bit surprised that Fish Crows didn't make either top-ten list - while I know I see a lot of American Crows, I feel like I hear the the higher-pitched caws of the Fish Crows much more often that these data show.  The other surprise here is that I record observing a red-bellied woodpecker about 25% of the time but I haven't counted many individuals (per list).  

<img width="592" height="799" alt="a photograph of a large flock of sandhill cranes taken by me in 2012 at Whitewater Draw, Cochise County, Arizona. The photo was shot on my phone through a viewing scope" src="https://github.com/user-attachments/assets/acb3bf2b-8e06-4342-ae22-a4aea0795bbb" />
*Figure: a photograph of a large flock of sandhill cranes taken by me in 2012 at Whitewater Draw, Cochise County, Arizona. The photo was shot on my phone through a viewing scope.*

Seeing these data also made me realize that there is some missingness that would have made it into the abundance graph had I not been so resistent to birding when I was younger: I have a photograph of at least 300 Sandhill Cranes from a trip I took with my Grandfather back in 2012 to Whitewater Draw in Arizona - maybe I should add that as a historical list.

<img width="1126" height="672" alt="a cumulative line plot showing the growth of the number of lifers I have encountered in the first 500 bird lists I've submitted to eBird" src="https://github.com/user-attachments/assets/22a620fb-8ee7-4eb4-bf6c-e7239da49c5e" />
*Figure: a cumulative line plot showing the growth of the number of lifers I have encountered in the first 500 bird lists I've submitted to eBird.*

The cumulative growth in the number of my "lifers" over time is plotted in the second graph. A lifer is a bird species that someone observes for the very first time in their life, an especially exciting milestone for birders. On eBird lifers are maintained on life lists. Life lists are a bit weird - I have recorded observations of 350 lifers but eBird only counts 345 of those. Five of my lifers are either hybrids or exotics that have not been recognized by Cornell for a given location. Pretty much everything pre-2021 on this graph is a "historical list" or a list my mother or grandfather shared with me to add to my own (one of the social features of eBird). 

<div class="map-container" style="margin: 20px 0;">
  <iframe 
    src="{{ '/assets/leaflets/bird_map.html' | relative_url }}" 
    width="100%" 
    height="600px" 
    style="border: none; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);" 
    title="Interactive Birding Map">
  </iframe>
</div>

*Note: Larger circles indicate locations where I have submitted more than 10 checklists.*

Finally, one of the greatest things I've learned about birding is that I can take it with me, for free, anywhere in the world. Here's an interactive map of all the places I've been privileged to record observations while visiting over the last few years. When I look at this map I think about all the places I've been *before* I was birding - The Bahamas, Puerto Rico, Spain, and Texas among others. These are places I have to revisit as a birder now. Birding gets me outside and makes exciting what would otherwise be an uneventful walk in the woods. 
