# on AI slop and incentive design

I have an obsessive hatred for AI-generated content on YouTube. It's incredibly disrespectful to the platform that I basically grew up on. Watching genuine, passionate creators pour their hearts into making content and get fewer views than an AI-generated Disney princess channel disgusted me. But what was I going to do about it? Any classification model would be hopeless against the constant iterations and improvements in AI content generation. What works perfectly today could become obsolete tomorrow. You'd be in a constant arms race against AI creators who have automated content farms and posting schedules. Even getting more human creators to post wouldn't work, because creativity isn't something you can schedule ahead of time and wield on demand.

But it would be so lame of me to sit around and do absolutely nothing. The first order of business was to acquire data. I pulled multiple all-nighters to label YouTube channels manually, both AI and human content. Managed to accumulate an initial dataset of around 2,000 channels this way, which is what the original product was trained on. You can extract channel characteristics using the YouTube API, and from there I fit Poisson distributions over posting behavior. That was where I had my first revelation: in a large number of instances, there is a statistically measurable difference in the posting behavior of human and AI creators.

It wasn't perfect because there were many edge cases. For example, there's a YouTube channel I follow called The Perfume Guy who makes videos about fragrances, and that guy has a posting schedule down to the minute. If you're classifying people purely based on variance in their posting behavior, you'd classify him as a bot, because even though he's a human, he posts like one. You'd have many of these edge cases, but consistently you'd notice that AI-generated channels have very high posting throughput. They'll post 20–30 minutes of finished content a day. For a human creator, unless you're doing a daily podcast, it's very difficult to produce 20–30 minutes of finished content every day without burning out.

A great example of the opposite is Elliott Choy. That guy had insane posting variability. He would disappear for weeks at a time, release an hour-long video, come back with maybe a 15-minute video. In general, lack of posting consistency was a great indicator for humans, but that works primarily for vlogs or where people are making organic content. What about scheduled things? What if creators are working for an organization like Khan Academy, where they're posting courses on a set schedule? How do we avoid misclassification?

The second key realization from modeling AI vs. human creators with Poisson processes was that the reasoning for why people post a certain way is entirely based on their incentive structure. Once again, game theory coming in clutch, because you realize that if you are an AI content channel, you do not actually know how to make content. You outsourced all your creativity to a bot.

Therefore, your strategy for maximizing revenue on YouTube is to post as much as possible. Since you don't think about creation, you're going to spend all your time:
- optimizing for SEO
- optimizing your posting schedule (like when people are most likely to be online)
- optimizing every single little variable in your video
Essentially anything but actual creativity.
Whereas if you are a human, you can't really match that. If you're smart, you're going to spend all your time thinking about how to make the best possible content you can, and that takes a lot of effort and time to refine.

You simply cannot be posting 20–30 minutes of finished content a day. Maybe you could if you had a production team, but most solo creators or anybody under a certain subscriber count does not have that kind of money, so you wouldn't see behavior like that.

This was really difficult to capture with pure XGBoost-based models, and this is where Caroline was incredibly helpful. Massive, massive thank you to Caroline.

She labeled thousands of channels with me, definitely more than me towards the end. Because of that, I was able to train an XGBoost model that immediately filtered out around 70% of AI channels on our train-test split. This is incredible because at this point I wasn't even using Poisson processes anymore. We were just running pure XGBoost on the data returned by the YouTube API to classify these channels.

The final step in making this extension foolproof was figuring out a way to prevent AI channels from mislabeling themselves as non-AI, because obviously they'd be incentivized to do that.

I thought about what happens if we hypothetically scaled our Chrome extension up to a million users, or maybe 10 million (complete fantasy at this point). If it does scale up to that point and all the users are sharing a collective blacklist (one of the first things I thought up was a shared blacklist, almost like SponsorBlock), then if one user submits a modification to a video, the entire user base benefits. Obviously there's a freeloader problem, but it's an incredibly effective model for carving out a portion of the internet where the content is just not AI-generated. I wanted to create a little garden within YouTube to absolutely filter out all AI content.

Naturally, if you try to create this garden, AI channels are going to try and infiltrate it, because if they can get in, they're showing their content to people that other channels wouldn't be able to reach, and they can maximize their revenue that way. The easiest way to filter them out was actually through a weighted voting and consensus mechanism. I'll explain this a bit more.

When users first see a video, it has no votes. The first few votes are going to be way more important than the ones that come after, so they carry a higher weight. Once we have enough votes for a channel, we're able to establish consensus on whether it's AI or human. Anybody who goes against consensus and classifies it the opposite way gets punished for that; their votes start to matter less. If they do this enough times, I wrote an algorithm that just completely shadows them off the extension so they can't touch it at all.

You'd think there are obviously going to be channels that try to sabotage the extension, and then there are going to be people who try to help but aren't great at classifying AI versus non-AI. Those people probably shouldn't be voting either. Because you can't take away someone's right to vote on the extension, the easiest way to handle this is to observe whether they break consensus or not.

That was really the final piece of the puzzle. After that, it was a complete product grind and sprint. Eventually I made posts about this with Caroline on LinkedIn. We got it on the Cornell eShip listserv. It was honestly quite a fun ride; I learned a ton once again. Shout out to Caroline for basically doing all the GTM labeling, tons of data work, and content creation.

It was a great time. This was one of the first projects I did that I was really proud of, and it inspired me to pursue more aggressive and ambitious projects. They've since been finished, but when I first made this extension, there were still ideas in my head that hadn't happened yet.
