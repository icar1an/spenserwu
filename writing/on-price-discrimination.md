# on price discrimination and grocery arbitrage

I've always been fascinated by price discrimination because it is the ultimate end game of late stage capitalism x enshittification of nice things for consumers. the idea of being able to charge people exactly what they're willing to pay and extracting maximum profit is just wow. then again for now this is a fantasy and does not work for most consumer goods (good luck charging mark zuckerberg 200k for airpods). should probably decide if I'm going to side with consumers or corpos on this one soon.

got started thinking about this months ago when I spoke to alum @SethSarelson, who sold his digital couponing company for an undisclosed amount of money. funny thing about price discrimination is that if it is presented in the form of a dynamic coupon, people who get different coupons don't feel ripped off even though they are being price discriminated against since they feel like the person who got the better coupon was more skilled (insane ikr).

he told me if you book your flights with terrible computers/cell phones in ZIP codes with lower median income, you can finesse better prices which absolutely blew my mind.

theory: any company like instacart or uber obviously uses what data they have to optimize prices in different regions.

surprisingly when I explored the actual data, I found that wegmans charged the same prices through instacart no matter what region of ithaca I set my residency to (so so expensive to pay for apify in order to discover this, think instacart has a secret markup somewhere but I don't want to violate ToS).

since I had already hard committed to the project at this point I figured it would be interesting to map the price of a basket of consumer goods in the Ithaca region cross zip codes to see if there was any meaningful price difference to exploit (spoilers: no. you would spend more on gas and opportunity cost than trying to geoarb your groceries).

however, this was a ton of fun to pull off and inspired several other projects I am going to work on. orchestrated the whole thing with running multiple agents in parallel thinking about running agent swarms, and also used designprompts.dev to make the website (shoutout @BenKoppe for putting me on game, loving the neo brutalism).
