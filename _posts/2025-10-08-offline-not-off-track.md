---
layout: post
title: "Offline, But Not Off-Track"
date: 2025-10-08
image: /assets/img/blog_4_cover.png
tags: [Spain, AI, Offline-First, Language Learning, App Development, Solo-Motherhood]
featured_description: "A week in Madrid, diving into offline-first Spanish learning, LLM-powered flashcards, and the messy, magical architecture of a personal tech-meets-language experiment."
---

<br>
<br>
<br>
<br>

**🇪🇸 Madrid: Week One-iversary**

Today marks the end of my first week in Madrid! An auspicious occasion commemorated by my eSim card ghosting me completely just as I was trekking into Centro! 😅 (This space cadette had completely forgotten that she’d only purchased a 7-day plan. My sincerest thanks to SailyBot for escalating my absent-minded panic to a human assistant 👌)

![[blog_4_saily.png]]({{ "/assets/img/blog_4_saily.png" | relative_url }})
*Fig A.* When you're trying to milk 2GB across 30 days, but you actually have 1GB for 7. Result: a mere 30% of my quota used.😅

Like Indiana Jones rolling clear of a rapidly descending hundred-ton wall, two major tasks slid past their last obstacles just in time for this date.

First, I now know which fertility clinic I’ll be starting my single-mom-by-choice (_madre soltera por elección_) journey with—beginning with egg vitrification.  
(More on this in a future post; for now, a round of applause to my friend Vero, the GIF queen, for finding this lil’ animation)
<img src="{{ "/assets/img/blog_4_vero.png" | relative_url }}" alt="Egg vitrification animation" style="max-width: 60%; height: auto; display: block; margin: 0 auto;">

And second… my little Spanish flashcard study app is officially _live_ — fully functional from a locally hosted, offline web platform on my laptop to offline access from my phone. 🤯 The only time these two interfaces need Wi-Fi is to high-five via a Railway-hosted back end and sync their local flashcard databases. 🙌!

Here's how it works (kudos to Claude for this diagram):

![[blog_4_diagram.png]]({{ "/assets/img/blog_4_diagram.png" | relative_url }})

1. We have a command set up in a `.toml` (still not totally sure what that is 😅), so once I navigate in Terminal to the `spanish-cards` folder, I just type `./start.sh` to launch the app from my local server **and**—I think—simultaneously open the port for the Railway back end. (Working this out with my LLM teammates took an _insane_ amount of time; key concepts: CORS and database structure.)
    
2. In the browser, go to `localhost:8080`. There, I can generate verb and sentence flashcards, study, and manage/edit cards. All of that works offline, including saving, but if I want the newly saved cards to be accessible for mobile download--just once, and then offline forevs--I will need Wi-Fi before signing off.
    
3. Then, from my phone, I just go to `amyzhang-commits.github.io/spanish-cards-app`. The first time, I need Wi-Fi to load it—but afterwards, it’s stored in browser cache. Syncing happens occasionally when Wi-Fi returns. (Right now it’s polling automatically to retrieve; I’ll fix that later, since that's less resource efficient.) You can’t have Gemma3n generate cards on mobile, but you can study, edit, and review offline, and those edits sync once you reconnect.
    

So...no more excuses to not buckle down in the biblioteca, right? 🫣

---

### Technical Debt: Payback Time 💸 

Before deep-diving into it all, I *am* intent on taking some time to really understand how this modular marvel even holds together. 😅 Copious work logs (aka conversations with Claude, Claude Code, and ChatGPT) await me. 

For now, here’s the list of the things that I currently understand myself to **not** have understood—_yet._

1) **Cross-Origin Resource Sharing (CORS) + Ports:**  
Why 8080 and 8000 kept arguing, why the front end and back end need different ports, and what the browser’s “bouncer” (CORS) was really trying to tell us. In the end, the fix was comically simple: adding explicit environment variables. I’ll need to dive deeper into Railway’s role here—it feels like a sort of Squarespace for apps rather than landing pages. Honestly, this might become my full-stack crash course.

2) **Relative vs. absolute paths:**  
Why my CSS refused to load on GitHub Pages until I learned that not all roads lead to Rome… if you’ve moved Rome. Revisiting this will be my front-end fundamentals bootcamp.

3) **Database systems:**  
This is the murkiest one. There’s PostgreSQL in Railway, but also a debugging PostgreSQL that Claude came up with to test sync--what became of that? I _think_ most of this app uses IndexedDB for offline storage? And at some point, the Railway database URL came into play—something about public databases causing egress charges. (No clue what that means yet.)  
The bigger realization: I was still thinking in “server-based web app” mode—like a Telegram bot that updates a cloud DB. But an _offline-first_ app flips that: each device holds its own local database, and the cloud is just the sync helper. 

4) **Progressive Web Apps (PWAs) + Browser Cache:**  
How the phone app now lives in browser memory like a ghost app that doesn’t need Wi-Fi. Magical and utterly mysterious to me still. But how do I make this personalizable or shareable for others? Surely not every Spanish learner who wants to try this out needs their own GitHub + Railway setup…

5) **Gemma’s Verb Hallucinations:**  
Ah, dios mio. This one’s part comedy, part crisis, as I shared in the previous post-- an entire language-learning app with Spanish speaking credentials as reliable as Professor Chang from Community. 
![[blog_4_chang.png]]({{ "/assets/img/blog_4_chang.png" | relative_url }})
I mostly understand what’s happening, but what I'd like to retroactively understand is better planning around JSON schema, in this case for flashcards. Object attributes matter more than you’d think for filtering and downstream flexibility. For instance, we 'd originally forgotten to ask Gemma3n to include whether a verb was regular or irregular—essential for filtering. Tiny omission, big use-case blind spot. And because constructing the JSON schema is a large part of Gemma's task in this app, it'll be a good opportunity to see if the current prompts can be improved. 

---

### En conclusión...🪶

In sum, the Spanish studying will happen! On Sunday, I went to a lovely art Meetup and discovered that while I can chat and joke comfortably, I’m still relying on everyone’s goodwill. From that event, I now have an image of a piece by the wildly versatile artist, Alfredo Alcain, depicting me, hanging out on the Spanish B2-level plateau with my LLM squad 😅

![[blog_4_LLMteam.png]]({{ "/assets/img/blog_4_LLMteam.png" | relative_url }})

In the meantime, revisiting all this code will be worth it. This humble, hybrid offline architecture—open source wherever possible—feels like a real template for the kind of tools I want to build (and teach my kids and their friends to build). And I know it's a long shot from an actual federated learning project, but...paso a paso, no es? 

For now, as someone spending _way_ more time on Madrid’s metro than expected (this city is basically Los Angeles with trains), I can tell you that studying my flashcards from my phone from the 6 line to Legazpi, being humbled by the verb _haber_ in present tense, felt like a strangely satisfying way to start Week 2.

As my hermanitx ChatGPT quipped:  
**Offline, but not off-track.**
