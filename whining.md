let's try to be big boys about this. i'll document whatever i'm doing.

# the challenge

make a chatbot for GIS in 1 day. today is 18th july and i started at 1:45 PM. ground rules: i'm not allowed to use any chatbot API (openai and stuff). the metric is that the bot should be able to answer these questions to some degree of correctness:

    1. Can you show me the latest satellite imagery of New York City?
    2. What is the land use distribution in Los Angeles for 2023?
    3. How has the deforestation rate changed in the Amazon rainforest over the last decade?
    4. Can you provide the population density map of Delhi?
    5. What are the main agricultural zones in California?
    6. Show me the changes in urban development in Tokyo from 2000 to 2020.
    7. Can you find flood-prone areas in Florida?
    8. What is the elevation profile of the Rocky Mountains?
    9. Provide a heat map of traffic congestion in London.
    10. Can you identify areas suitable for solar panel installations in Arizona?

ight lessgoooooo

# step 1: data
need daaaaataaa. two types of data: textual data (research papers and shit), and non-textual data (maps and stuff)

i'm going for land use data for non-textual. 

ight found the perfecc dataset, slight issue - it's 60 GB for each year for all the data. 
esri data from the sentinel-2 satellite land cover data at a 10 meter resolution. 
absolute dream shit, but my wee laptop and my stingy ass can't have it. hmmmmmmm. workaround, lesssee. one possibility is i can just download a region, which will (hopefully) be smol, and change the questions to limit myself to that region. can do. ight fine :( but i'll complain the whole time.

reset the questions. limited the dataset to north india, hindi belt - rajasthan, punjab, delhi, haryana, uttar pradesh, bihar, and limited it to 2020. new questions: 

    1. Can you show me the latest satellite imagery of Delhi?
    2. What is the land use distribution in Jaipur for 2020?
    3. How has the deforestation rate changed in the forests of Uttar Pradesh over the last decade?
    4. Can you provide the population density map of Patna?
    5. What are the main agricultural zones in Punjab?
    6. Show me the changes in urban development in Chandigarh from 2000 to 2020.
    7. Can you find flood-prone areas in Bihar?
    8. What is the elevation profile of the Aravalli Range?
    9. Provide a heat map of traffic congestion in Lucknow.
    10. Can you identify areas suitable for solar panel installations in Haryana?

feel like kind of a poop rn, but c'est la vie. 

ight so i have these weird ass picture thingies. never used this format, dunno what these are tbh. 
3 pictures, around 250 mb each. insane shit. they're lagging and misbehaving and i wanna throw a tantrum rn. this is not the stage i expected to have problems at wtf. why is it not transferring the pictures??

ok, using my advanced software engineering skills and unequalled computing prowess, i managed to transfer 3 picture files from desktop to this folder (the computer restarted 3 times in the process). now, onto figuring out what to actually do with these .tif files. 

before we get into that tho, let's get some textual data. now because of the limits applied from the land use data, we'll have to be smart about this. need texts about north india from 2020. probably won't get clean data off kaggle or something. might have to explore like, govt agencies and shit.

tbh i can probably do get by with what i have, idk. one possible strategy atp is to just train with the land use data, cuz the primary purpose of this exercise is just to understand how this shit works. we can add text data later, it's not like nlp is an issue.

another alternative is to find some textual data for some location, then download the land use data from there, and rewrite the questions to fit that. that's actually the better alternative. i deserve cookies sometimes :D

ight-o im going with new york. t'is 4:02 PM and i've achieved... one github repo, lunch and a 15 min nap :|
ok whatever, now i delete these 600 MB of .tif files. fun. i hates them. replaced with 2021 2022 2023 data of new york. tbh new york's a tiny part of it, it's a huge area, whatever it covered new york that's all that matters ig. gonna need new questions now. 

question set #4389021832019 here goes:

    1. Can you show me the latest satellite imagery of New York City from 2021?
    2. What is the land use distribution in Manhattan for 2022?
    3. How has the green space area in Central Park changed from 2021 to 2023?
    4. Can you provide the population density map of Brooklyn for 2023?
    5. What were the main traffic congestion areas in New York City in 2022?
    6. Show me the changes in urban development in Queens from 2021 to 2023.
    7. Can you find flood-prone areas in New York City from the 2022 data?
    8. What is the elevation profile of Staten Island?
    9. Provide a heat map of air pollution levels in the Bronx for 2021.
    10. Can you identify areas suitable for new park developments in New York City based on 2023 data?

sooooooooooooo sleepy. we march on. textual data let's go.

new problem: too much data. what do i need. wtf is my life i'm so confused.
here's what i'm thinking: 

    1. satellite images
    2. city maps
    3. population maps
    4. traffic maps (if that's a thing)
    5. elevation? idk if that's a separate thing but i desire it.
    6. heat map (again idk what that is)

THESE ARE map datas :( 

screw this it's a waste of time. nothing works. i'm just gonna move onto the next step now, i'll add more data later if i need it.

# step 2: preprocessing
