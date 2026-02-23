# on price discrimination and grocery arbitrage

I've always been fascinated by price discrimination because it is the ultimate endgame of late-stage capitalism meets enshittification of nice things for consumers. The idea of being able to charge people exactly what they're willing to pay and extracting maximum profit is just — wow. Then again, for now this is mostly a fantasy and doesn't work for most consumer goods. Good luck charging Mark Zuckerberg $200k for AirPods. I should probably decide if I'm going to side with consumers or corporations on this one soon.

I got started thinking about this months ago when I spoke to alum @SethSarelson, who sold his digital couponing company for an undisclosed amount of money. Funny thing about price discrimination is that if it's presented in the form of a dynamic coupon, people who get different coupons don't feel ripped off — even though they are being price discriminated against — since they feel like the person who got the better coupon was simply more skilled. Insane, I know.

He told me that if you book your flights from terrible computers or old phones in ZIP codes with lower median income, you can finesse better prices. That absolutely blew my mind.

Theory: any company like Instacart or Uber obviously uses whatever data they have to optimize prices across different regions.

Surprisingly, when I explored the actual data, I found that Wegmans charged the same prices through Instacart no matter what region of Ithaca I set my residency to. It was painfully expensive to pay for Apify in order to discover this. I think Instacart has a secret markup somewhere, but I don't want to violate their ToS.

Since I had already hard committed to the project at this point, I figured it would be interesting to map the price of a basket of consumer goods in the Ithaca region across ZIP codes to see if there was any meaningful price difference to exploit. Spoiler: no. You would spend more on gas and opportunity cost than you'd ever save trying to geo-arbitrage your groceries.

However, this was a ton of fun to pull off and inspired several other projects I'm going to work on. I orchestrated the whole thing by running multiple agents in parallel — got me thinking about agent swarms — and also used designprompts.dev to make the website. Shoutout to @BenKoppe for putting me on, loving the neo-brutalism.
