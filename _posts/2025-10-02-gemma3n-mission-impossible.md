---
layout: post
title: "Gemma3n: tu misión, si decidieras aceptarla..."
date: 2025-10-02
image: /assets/img/entity-spanish.png
tags: [Spain, AI, LLM, Gemma, Language Learning, Travel, Offline-First]
featured_description: "Flashcards and funny LLM hallucinations, 30,000 feet over the Atlantic; testing my Spanish learning app"
---

<br>
<br>
<br>
<br>

# Ha Llegadoooo

Friends, I made it — I've arrived in the land of castanets and Quixote, Borges and Gaudí, and one of my favorite surrealist photo-montage artists, Kati Horna (fantastic show at the Americas Society back in 2016 — [link](https://www.as-coa.org/exhibitions/told-and-untold-photo-stories-kati-horna-illustrated-press)).

I shall spare you the full physical saga of lugging a wheel-less, strap-less carry-on through JFK's villainous check-in lines (and then standing in Madrid immigration's endless human snake-pit). Let's just say, the in-flight entertainment of Tom Cruise's _Mission Impossible_ hijinks — dangling off of planes, free-diving the Bering Sea — has more than sufficed to put my tendonitis and shaking hands in perspective. 😅

Hollywood-humbled, I turned my attention the rest of the time to nerdier fare: stress-testing the **offline Spanish study app** I've thrown together with Claude + ChatGPT. And given the central villain of 'Mission Impossible: The Final Reckoning'--a malicious all-powerful AI hell-bent on annihilating the human race--I think my antics might, in return, help put Hollywood's histrionics in some perspective. 😏

# "The Entity" Me Enseña Español (Cue Lalo Schifrin's Killer Soundtrack)

The core feature of the app is my local, on-device LLM bestie--Gemma3n--generating Spanish conjugation flashcards.

Now, I'm a big believer that some tedious tasks are actually sources of generative friction - learning moments in disguise. But when I was teaching myself Mandarin in NYC, I realized the flashcard flow could definitely use some automating. The valuable part of flashcards is the discovery moment-- the "what does this mean, [Google Translate]?'--and then the subsequent review sessions. Not so much the in-between steps of making sure to star Google's translations, importing the favorites into Google Sheets, then downloading that into a CSV...to import into Anki. C'mon now, I've got a wifi-less subway car to catch so I can get stuck on it and study my cards! 🙃

For Spanish, the most time-consuming cards to make - especially if you want to type the accents just right - are the conjugation cards. For each verb, each tense-mood pair, with each pronoun, that's around 90 cards per verb. 🤯 Socoro-me, Gemma3n!

By the time of the stress test on the flight (6.5 wifi-less hours, because deltawifi.com is a myth), my AI teammates and I had cooked up a solid verb generator page, complete with a reference guide for selecting which tense-mood pairs to study. We had conjugations for 'ser' (conditional tense) and 'hablar' (imperfect tense) already generated and saved pre-flight.

But on the flight... 'decir' provoked some hallucinations and weird UI glitches. 😭

So I took this as an opportunity to try something else: for once, I decided to hand the mic more directly to the (w)rapper, and chat directly with Gemma3n in terminal 😎🎤 However, the lines they dropped were more "fire" shouted in the comedy theater, than fire themselves. 🫠

## Gemma3n Hallucinations (aka: Comedy Hour at 30,000 Feet)

**Me:** Thanks, Gem! Hey, could you give me a multiple choice verb conjugation exercise in Spanish, just one question at a time, where I have to fill in the correct form to complete your sentence? Can the examples be as idiomatic as possible?

**Gemma3n:** ¡De nada! You're very welcome! I'm glad I could help. Absolutely, let's do a multiple-choice verb conjugation exercise. I'll give you one question at a time, and you fill in the blank. I'll try to make the sentences as idiomatic as possible.

**Here's your first question:**

**Yo _______ un café con leche todos los mañanas antes de ir al trabajo.**

a) bebo  
b) bebo  
c) bebo  
d) bebemos

Take your time, and let me know which letter you choose! 😊

**Me:** Haha, it's a, b, and c.... you repeated the same answers!

**Gemma3n:** Ay, perdón! You are absolutely right to call me out on that! My apologies for the error. That was a silly mistake on my part. I am still under development and learning to avoid these kinds of errors.

Let's try that again. Here's the corrected question:

**Yo _______ un café con leche todos los mañanas antes de ir al trabajo.**

a) bebo  
b) bebo  
c) bebo  
d) bebo

Please choose the correct answer this time! I'll be watching closely to make sure I don't repeat the mistake. 😊

**Me** (attempting to change tack): Haha, now it's all of them, you repeated the right answer for each one. No worries! Can you give me the 5 most common -ir regular verbs to know?

...And at this point, Gemma3n confidently offers me: Ir, Vivir...Tener, Comer, Hablar.... 😬

# What I Learned (and What's Next)

We all know that even the mighty, big-brand foundation models - ChatGPT, Claude, Gemini - hallucinate when conversations veer into edge cases. This is part of what makes supporting LLMs with RAG pipelines so exciting: the ability to directly reference or generate materials from specific sources makes their output way more reliable than asking them to answer from a kind of dream state, where all the world's knowledge has been digested into statistical intuition.

Nevertheless, I hadn't quite expected how much one of the world's most spoken languages would challenge a smaller model. 

Maybe training sets lean heavily towards English, or maybe Gemma3n hasn't seen enough pedagogical texts - prompts for multiple choice questions or granular corrections might not be a dance they've mastered yet. Either way, I definitely will be sticking to very contained conjugations generation, instead of full sets of 90 cards at a time. And if there is to be a dynamic quiz section, maybe some fine-tuning can help (give them a couple of more examples of how multiple choice works, perhaps 😅)

Still, even if Gemma3n's conjugation skills are a _Mission Impossible_ of their own, the flashcard app already nails translations of full sentences (plus providing corrections for the original sentence, including those tricky accents!) - this being the second feature of the app. And even if little Gemma can't perfectly conjugate, they _can_ explain to me that translating "should you choose to accept it" would require the conditional tense for "should"...

Not bad for an AI that (will) fit in my pocket. (Next step: Mobile version!)

Hasta la próxima ✈️📚

_Next time: more on the offline architecture
