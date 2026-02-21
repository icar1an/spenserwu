# on AI slop and incentive design

I have an obsessive hatred for AI generated content on YouTube. It's incredibly disrespectful to the platform that I basically grew up on, watching genuine passionate creators pour out their hearts into making content and getting less views than an AI generated disney princess channel disgusted me. But what was I going to do about it? Any classification model would be hopeless against the constant iterations and improvements in AI content generation. What works perfectly today could become obsolete tomorrow. You wwould be in a constant arms race against AI creators who have automated content farms and posting schedules. Even getting more human creators to post wouldn't work, because creativity isn't something you can schedule ahead of time and wield on demand. 

But it would be so lame of me to sit around and do absolutely nothing. The first order of business for solving this problem is to acquire data. I pulled multiple all nighters to label YouTube channels manually, both AI and human content. Managed to accumulate an initial dataset of around 2000 channels this way, which is what the original product was trained upon. You can extract channel characteristics using the YouTube API, and from there I fit poisson distributions over posting behavior and that was where I had my first sage revelation: in a large amount of instances there is a statistically measurable difference in the posting behavior of human and AI creators! 

It wasn't perfect because there were many edge cases. For example, there's a YouTube channel I follow called The Perfume Guy who makes videos about fragrances, and that guy has a posting schedule which is scheduled down to the minute. If you're classifying people purely based off of variance and their posting behavior, you would classify this guy as a bot, because even though he is a human he posts like a bot, but he is a person. You'd have many of these edge cases, but consistently you would notice that AI-generated channels have very high posting throughput, so they'll post 20-30 minutes of finished content a day. For a human creator, unless you're doing a podcast on the daily, it's very difficult to shoot 20-30 minutes of finished content today; you would definitely burn out.

A great example of this would be Elliott Choy. That guy had an insane posting variability. He would disappear for weeks at a time, release an hour-long video, come back maybe like another 15-minute video. In general, lack of posting consistency was a great indicator for humans, but that works primarily for blogs or where people are making organic content. What about scheduled things? What if creators are working for an organization like Khan Academy, where they're posting courses or things on a scheduled basis? How do we avoid misclassification? 

The second key sage realization from modeling the AI vs human creators with Poisson processes was realizing that the reasoning and explanation for why people post a certain way is entirely based off of their incentive structure. Once again, game theory coming in with a massive clutch right here, because you realize that if you are an AI content channel, you do not know how to make content, because you outsourced all your creativity to a bot.

Therefore, your strategy for maximizing revenue on YouTube is to post as much content on YouTube as possible. Since you don't think about creation, you are going to spend all your time:
- optimizing for SEO
- optimizing your posting schedule (like when people are most going to be online)
- optimizing every single little instance in your video
Essentially anything but actual creativity.
Whereas if you are a human, you can't really match that. If you are smart, you are going to spend all your time thinking about how can you make appealing content, how can I make the best possible content that I can make, and that's something that takes a lot of effort and time to refine.

You cannot be posting 20-30 minutes of finished content a day. If you think you can, maybe you could if you had a production team, but most solo creators or anybody under a certain subscriber count does not have that much money, so you wouldn't see behavior like that.

This was really difficult to try and capture with pure XGBoost based models so this is where Caroline was incredibly helpful. Massive massive thank you to Caroline.

She labeled thousands of channels with me, definitely more than me towards the end. This is why I was able to train an XGBoost model that was able to immediately filter out around 70% of the AI channels right out of the database on our train test split. This is incredible because at this point I wasn't using Poisson processes anymore. We were just running pure XGBoost on the data returned by the YouTube API in order to classify these channels.

The final step in making this extension completely foolproof was trying to figure out a way to prevent AI channels from mislabeling themselves as non-AI because obviously they'd be incentivized to do this.

I thought if we scaled our Chrome extension hypothetically up to a million users or maybe like 10 million (this is a complete fantasy at this point), in the event that it does scale up to that point and all the users are sharing a collective blacklist (because one of the first things that I thought up was a shared blacklist, almost like on Sponsor Block), if one user submits a modification to a video, the entire user base benefits. Obviously there's a freeloader problem from this but it's an incredibly effective model for being able to carve out a portion of the internet where the content is just not AI-generated. I wanted to create a little garden within YouTube, so to say, to absolutely filter out all AI content.

Naturally, if you try and create this garden, an AI channel is going to try and infiltrate it because if they can infiltrate the garden, then they could be hypothetically showing their content to people who other channels wouldn't be able to, and they'd be able to maximize their revenue that way. The easiest way to filter them out was actually just through a weighted voting/consensus mechanism. I'll explain this a bit more.

Essentially, when users first see a video, it has no votes. The first few votes are obviously going to be way more important than the ones that come after it, so they have a higher weight. Once we have enough votes for a channel, we are able to establish some sort of consensus on whether this is AI or is human. Anybody who goes against consensus and classifies it the opposite way is going to be punished for that; their votes matter less. If they do this enough times, then I wrote an algorithm that just completely shadows them off the extension so they can't touch it at all.

You'd think that, obviously, there are going to be channels who try and sabotage the extension, and then there are going to be people who try and help but they're not that great at classifying AI versus non-AI. Those people probably should not be voting as well. Because you cannot take away somebody's right to vote with the extension, the easiest way to do this is to observe if they break consensus or not. 

That was really the final piece of the puzzle. After that it was really just a complete product grind and sprint. Eventually I made posts about this with Caroline on LinkedIn. We got this on the Cornell eShip listserv. It was honestly quite a fun ride; I learned a ton once again. Shout out Caroline for really basically doing all of GTM labeling, tons of data, and also making content.

It was a great great time. This was one of the first projects that I did which I was really proud of and it was able to inspire me to pursue more aggressive and ambitious projects. Right now they have already been finished, but when I first made this extension there were still unhad ideas in my head.


