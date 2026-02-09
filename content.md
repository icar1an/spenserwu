**proof of agency**

[arbicart](https://arbicart.spenserwu.com) — geoarb your groceries (hypothetically)
- I've always been fascinated by price discrimination because it is the ultimate end game of late stage capitalism x enshittification of nice things for consumers. the idea of being able to charge people exactly what they're willing to pay and extracting maximum profit is just wow. then again if you dig up one of my old twitter posts you will realize that is a fantasy and does not work for most consumer goods (good luck charging mark zuckerberg 200k for airpods)
- really got started thinking about this months ago when I spoke to alum @SethSarelson, who sold his digital couponing company for an undisclosed amount of money. funny thing about price discrimination is that if it is presented in the form of a dynamic coupon, people who get different coupons don't feel ripped off even though they are being price discriminated against since they feel like the person who got the better coupon was more skilled (insane ikr)
- he told me if you book your flights with terrible computers/cell phones in ZIP codes with lower median income, you can finesse better prices which absolutely blew my mind
- this ties into another one of my theses, which is that any company like instacart that coordinates transportation of physical goods from retail to consumer or companies like uber that do ride hailing would obviously use what data they have to optimize prices in different regions
- surprisingly when I explored the actual data, I found that wegmans charged the same prices through instacart no matter what region of ithaca I set my residency to (so so expensive to pay for apify in order to discover this)
- since I had already hard committed to the project at this point I figured it would be interesting to map the price of a basket of consumer goods in the Ithaca region cross zip codes to see if there was any meaningful price difference to exploit (spoilers: no. you would spend more on gas and opportunity cost than trying to geoarb your groceries)
- however, this was a ton of fun to pull off and inspired several other projects I am going to work on. orchestrated the whole thing with running multiple agents in parallel thinking about running swarms, and also used designprompts.dev to make the website (shoutout @BenKoppe for putting me on game, loving the neo brutalism)

[head.surf](https://head.surf) — scroll reels/tiktoks/shorts handlessly, surf any webapp 🏄‍♂️🏄‍♂️🏄‍♂️
- the story behind this is insane. originally was working with @BenKoppe on adtech, but we got distracted by instagram reels during a roadblock. suddenly came up with a thesis: in the age where anyone can build anything, distribution is king. unless you have money to burn on marketing or are an influencer already/know ones willing to work for free in a relevant niche, you have to build products to enable repeatable content with virality potential. once you cultivate an audience, you ship your actual product
- he agreed, and we spent a while thinking about what we could build which would look the most goofy on reels, to which I suggested someone playing the chrome dino game with their face. only thought of this because of this guy named @aaronka4n on reels who used CV to make scripts that fetched images/quizzes. if that's possible then there is no reason why you shouldn't be able to play the chrome game with your head. stuff like the arcteryx detector is a waste of DDR5 ram
- quickly built a working prototype of the chrome dino game in 30 minutes, then immediately started working on making it work for subway surfers. we got it so good in one night that we went around campus doing user testing on random people at 1am. reception was crazy, it was my first time making a product that people actually WANTED. so addicting
- ended up skipping class the next day to rapidly improve head mode with auto tracking + perfecting the sensitivity thresholds. this is also when I had the sage realization that if it works for subway surfers, you can scroll REELS with it too
- it was also really easy to test this product and perfect it by using it, since the way you that is by watching short form content/playing internet games to fine tune the settings
- Ben got it into an auto updating dmg, we speedran the website and also started building gesturebinds + hand control modes using fingertip tracking. cue more UI/UX improvements through pure feeling and intuition for what a product like this should be like
- built wink controls, auditory feedback (so so satisfying), and also ended up consolidating some of the detected modes
- the beauty of headsurf is that it's so stupid the product literally markets itself. you can film infinite UGC by using it to scroll brainrot or play games in lectures, or even scroll multiple reels at once which is simply disgusting
- in the process of rapidly building out the product, a new thesis came to mind. keyboards are reductivistic and need to be made obsolete. technology should not constrain our instincts, and instead be built around them. the keyboard has been around for less than 150 years, compared to gestures which we have been doing for over 10,000. you should be able to control any content on screens through pure head/hand movement without additional haptic hardware. 
- now turning this into a gesture based way for people to interact with AI coding IDEs, if you're not coding with surf in 2026 ur ngmi 

[mode](https://chromewebstore.google.com/detail/mode-fashion-discovery-re/bbgigkgmodajaobdfalekpaolpolebnm) — if you follow me you'll know my eLab project was for fashiontech, but appdev on that front was a real pain and taking too long so I ended up shipping this to validate if the market wanted a product like this
- the CTR on this is insane currently ranging from 2-6%, I'm guessing this is because when people use it (they don't know how to dress like a certain outfit/aesthetic) they have an incredibly malleable window in their head for product placements 
- it originally had terrible CTR but then I changed the highest price by default to 150 and sorted all fetched items from low to high, this came from the sage realization that someone with serious money would hire a stylist instead of downloading a chrome extension
- new thesis: unless you have insane distribution/credibility in the industry, DO NOT try to build fashiontech. nobody needs the 2892 wardrobe/OOTD app or "tinder for clothes", just spend more money on clothes and learn how to get clothes from ebay/grailed/depop/vinted/vestaire collective/the realreal. you cannot shortcut the taste acquisition process, downloading apps to become more fashionable is like reading the sparknotes for tolstoy and expecting to be on par with someone who read the actual book. it's ridiculous, naive, and incredibly low signal


[clarity](https://chromewebstore.google.com/detail/clarity-hide-ai-videos-on/gjngfjkebjejpaagdlbkdibdameiolfk) — open source anti-ai slop chrome extension built with @CarolineZhu, [whitepaper](Clarity Whitepaper.pdf) available now
- made this because I hated the amount of AI content I was getting recommended on YouTube, pulled multiple all nighters to jumpstart the dataset and get it to a point where I could train some models for classification
- the breakthrough was realizing that an AI content creator has a completely different incentive system than a human creator, they make money from output not quality and therefore exhibit completely different posting behaviors
- this isn't something they can hide so a simple XGBoost model can filter out around 70% of AI channels right off the bat based on publicly avaliable data like comments, likes, views fetched from the YouTube API
- however AI slop channels would have the incentive to lie about their content type. this led me to spend a few days thinking of a mechanism that rewards honest users and punishes people who try to sabotage the classification system
- after much self learning in game theory I realized that you do this with a simple group consensus mechanism and shadowban people who go against what the community thinks. someone who has good intentions but horrible accuracy at identifying AI content is as harmful as an active saboteur

[ferrofluid](ferrofluid-fixed.html) — an audio-reactive 3D ferrofluid MP3 player
- made during a day I was insanely obsessed with ferrofluids, unfortunately I am not a MechE and building a ferrofluid speaker irl would be too hard so I made this instead

[veil](https://chromewebstore.google.com/detail/veil/lneibmllflnollbfbmdomcdibmnboamg?authuser=0&hl=en) — removing thumbnails and profile icons from youtube and replacing them with text
- this was the first chrome extension I ever made, you learn very quickly that in order for anyone to be interested or want to download chrome extensions you need to make the title stupidly blunt. made this after I labelled too many channels for clarity and got sick of staring at ugly thumbnails
- hilarious how this actually reduced my youtube screentime greatly, good luck clickbaiting me now mr beast

[jensenindex](https://jensenindex.onrender.com/) — a bloomberg terminal clone, but with leather jackets and NVDA ticker data
- watched too many NVDA keynotes and bought a leather jacket, needed to quantify the relationship
- another project heavily inspired by Riley Walz/MSCHF. you learn at first by copying the greats until you acquire your own sense

[heartpv](https://heartpv.spenserwu.com) — how many more times will my heart beat, and what is each beat worth?
- this was the first project I ever made completely solo. honestly looking back it's pretty terrible, but I still posted it to have skin in the game. mainly inspired by my take on Riley Walz, a little too morbid looking back but come on are yoru first projects ever supposed to be good?


---

**proof of articulation**

[daymare](#daymare) (oct 2021 pre GPT)

---

**proof of taste**

*skincare*
round lab birch sunscreen, adapalene, PKY calming cream/balm, FANCL cleansing oil

- this was a long journey. for skincare my general advice is to start from first principles YEAH I SAID IT AGAIN WHAT ARE YOU GONNA DO ABOUT IT?? my skin is oily/rosacea prone and through much experimentation I found the best approach focuses on restoration and not suppressing symptoms. madecassoside + ceramides are king, the only brand that mixes them well with minimal irritation and fragrances is PKY. sunscreens round lab works pretty well, torriden is fine as well. about to try the haruharu black rice one perhaps it will be good? double cleaning is also super important, the muji oil is actually better than the manyo imo since it doesn't hurt if you get it in your eyes. FANCL is even better tho. to get rid of acne just use adapalene for a while, actually magic. 

*fragrance*
current: edit(h) earl grey/diptyque philosykos
previous: d'annam white rice, one day taipei

- originally got into fragrances for a very shallow reason, but ended up falling in love with them once I realized how what is literally scented water can completely change your mood. started with blue masculine mens fragrances, then went through a white musk/floral phase, green herbal/botanical, now exploring masculine scents again but with a more nuanced and fresh perspective. really crazy how the same outfit can be radically different based on what fragrance you pair with it, trying to pare my collection down to 4 max ideally just one. 

*designers (aesthetically)*
christophe lemaire, hengdi wang, jil sander, hedi slimane, ricardo tisci

- if you like Uniqlo, you need to know that Christophe Lemaire is the person behind the entire Uniqlo U line. Lemaire is literally Uniqlo U but designer level in quality, fabrics, cut and color. 
- Hengdi Wang is the only person who scratches my Dune itch, his clothes are actually surreal. if liquid chrome aespa is y3k, hengdi wang is y4k when we've built programmable clothing and become an interplanetary species
- Jil Sander is simply clean. wow. if only the blazers didn't cost 5k a piece.
- Hedi Slimane and Ricardo Tisci are the ones who inspired by affinity for all black clothing, and also made me pay what I previously thought was an obscene amount of money for clothes. if you respect art, try to get designer. you don't need it new, thrift most of this stuff anyways because they don't work for the same houses anymore and it's just not the same. 

---

**proof of influence**

[why not you — togi](https://www.youtube.com/watch?v=HsT_uVz2q38&t=3203s)
- credit this one with pulling me out of a huge mental rut

[russ hanneman pitch — silicon valley](https://www.youtube.com/watch?v=C0nIWMKfzGY)
- even though he was talking to richard this was sage advice

---

[email](mailto:spenser.f.wu@gmail.com) · [x](https://x.com/kytherax) · [instagram](https://www.instagram.com/spensewu/) · [github](https://github.com/icar1an) · [steal my clothes](https://www.grailed.com/icarian)
