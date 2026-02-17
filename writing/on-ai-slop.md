# on AI slop and incentive design

I hated the amount of AI content I was getting recommended on YouTube, pulled multiple all nighters to jumpstart the dataset and get it to a point where I could train some models for classification.

the breakthrough was realizing that an AI content creator has a completely different incentive system than a human creator, they make money from output not quality and therefore exhibit completely different posting behaviors.

this isn't something they can hide so a simple XGBoost model can filter out around 70% of AI channels right off the bat based on publicly available data like comments, likes, views fetched from the YouTube API.

however AI slop channels would have the incentive to lie about their content type. this led me to spend a few days thinking of a mechanism that rewards honest users and punishes people who try to sabotage the classification system.

after much self learning in game theory I realized that you do this with a simple group consensus mechanism and shadowban people who go against what the community thinks. someone who has good intentions but horrible accuracy at identifying AI content is as harmful as an active saboteur.

shoutout @CarolineZhu for grinding out GTM, labelling hella data, and also making content.
