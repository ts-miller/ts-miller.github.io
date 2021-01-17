---
layout: post
title:      "Props & State - Oh What A Tangled Web We Weave"
date:       2021-01-17 19:49:51 +0000
permalink:  props_and_state_-_oh_what_a_tangled_web_we_weave
---


I'm not typically one for poetry, but sometimes iconic truisms such as the one in this blog post's title, fit life (and coding) so well. While learning React.js I found myself in the similar position that I had found myself in throughout this cohort. I started out at the bottom of the mountain looking up and feeling like I could summit in no longer than a few days. However, even the largest mountains can often feel small and safe from a distance. As I progressed in my project, it became apparent that what I thought was a small hill was actually a 14,000ft mountain. The primary bugagoos in the journey, I soon came to realize, are props and state.

Props and state are the two main players of the game that is React. State is contained in components or abstracted to a state manager like Redux. It changes throughout the component lifecycle and primarily determines the data being displayed to the user. Props (short for properties) are accessible to components and allow us to transsfer this data (or functions) to other components.

So imagine I have a component that outputs a list of all of my users. Each user build using a User component. Rather than each User component holding state itself (what a crazy mess that would be) the container holds all of the user data in it's state then sends each component only the info it needs as a Prop. While it's easy to follow this example, most web sites you build in the real world are not going to be this simple.

I greatly appreciate React because it displays helpful messages if you stray away from convention. What it does not do however, is tell you when to hold state in a component and when to pass it as a prop in the parent component. This becomes a problem when you have 3 or 4 (generations?) of components.


App ==> ClientsPage ==> ClientsContainer ==> ClientRow


Above is the flow for part of my portfolio project. Ultimately each ClientRow component needed to know the correct client data. Logically, it makes sense to connect my ClientsContainer to my Redux store and call it a day but my clients page also needed to make a call to the store for Appointments. So I could move it up a level to my ClientsPage and pass my clients as a prop to the ClientContainer and then pass it again to my Client row. This just for one small piece of a typical app and the larger it becomes the most concerned you need to become with unnecessary rerenders and performance issues.

Right or wrong what made sense for me and made my code vastly more readable was to use state a bit more liberally rather than sending a mess of props through my chain of components. This is what worked well for me in the project but I plan to change my tune as I learn. Perhaps when I begin building larger apps in my career, I discover issues that I could not imagine today. That is the beauty of learning and I'm along for the journey to the top of the mountain no matter how long it takes.
