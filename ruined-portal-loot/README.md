# FSG - Filtered Seed Glitchless
v 1.2 Tweaked lava pools and added RUINED PORTAL LOOT quality filters (typically 3 iron and a flint and steel but would accept other things like 7 iron or loot 3 swords or 6 obi)

In 1.1 added lava pools to village seeds and fixed a mistake causing half of the shipwreck portals to be buried.

MAJOR CHANGES: v 1.0 changed the verification token to be the only thing needed to validate your seed.  This means streamers don't need to show the code running and tournaments can be FSG and each runner's time can be counted to the leaderboards.  Just run your seed within 30 seconds of generating it here.  Also made major speed improvements, filter for non-ocean ruined portals even in shipwreck seeds.  The code has been refactored to be easier to understand for those looking to learn from it. You can use the spawn specific links below which are also upgraded.

This version of FSG doesn't go through millions of seeds just thousands. Y'all are creative at overworlds and entering the nether.  This filter only specifies two things: a great nether (close pos/pos bastion and close fortress in neg/pos or pos/neg) and great blind travel (300 blocks from 150/-150 or -150/150 if you leave from the fortress).  This might be the best way to practice rather than lean on my janky overworlds, do what you always do, but I'll handle the nether RNG.  Enjoy.

In v 0.6. the shipwreck spawns now have at least one magma ravine somewhere in the (-100,-100) to (200,200) square.  Ravines are somewhat tricky in the way minecraft handles them, so they aren't always blatantly obvious but in practice it should give you a nether entry in most cases.  The code will decide shipwreck or village with 50/50 probability.  If you want a specific start every time I have 3 specific FSG filters out there:
  1) https://repl.it/@AndyNovo/filteredvillage for only village spawns
  2) https://repl.it/@AndyNovo/filteredshipwreck for only shipwreck spawns
  3) https://repl.it/@AndyNovo/filteredseed-jungle for jungle temple spawns 

All 3 still get a ruined portal, nether stuff, and good blind travel of course.

In v 0.5 blind travel filters were added and one nether structure removed.  Bastion in pos/pos, fortress either pos/neg or neg/pos and stronghold within 300 blocks of either 1200,-1200 or -1200,1200 (matching the fortress).  Don't expect fantastic overworlds, blacksmiths are hard, loot tables are hard. 

In v 0.4.2 a memory leak was fixed so the code should run faster and crash less

New in v 0.4.1 the bastion in pos/pos is now guaranteed (never basalt)

New in v 0.4: for village spawns the ruined_portals are always above ground, just outside of the village (no further than coords 144, 144), and most importantly the portals always have at least 11 lava. There is a bastion in pos/pos (unless cancelled by basalt) and 1 fortress either pos/neg or neg/pos.

This is a new category for speedrunners designed to capture the feel of RSG with seeds that are of a certain guaranteed quality without the pre-planned feel of SSG.

In essence twitch streamers doing FSG can be more entertaining by finishing more seeds.

Just hit the RUN button to get a never before run seed with good speedrun traits.

The key to this as a category is that the seeds are chosen using a cryptographically secure random number generator and tested after the fact for a few key traits.

So when submitting a run please film the code running that generates your seed and start the world right after.

The current "good seed" traits:
  A village or shipwreck in the pos/pos quadrant of the overworld between 0 and 80 in both X and Z
  A ruined_portal near (0 to 144 but not in the village)
  Your spawn between -48 and 144 in both coordinates
  In the nether there is a structure close to 0,0 in three quadrants (+/+, -/+, +/-) these are all designed to be within 128 of 0,0 in each coordinate although in the negative dimensions they can't be produced with values between -64 and 0.

There will always be 1 or more bastions (pos/pos guaranteed) and exactly 1 fortress generated within 128 blocks of 0,0.

No restrictions are made on the stronghold in anyway.

If you're interested in helping this category grow you can help in several ways:
  Make and record runs and post them in the pb-brag channel, we can keep track of unofficial WRs for this category.
  If you're a seed finder help improve the algorithm, attributes, and the balance between unpredictable and of sufficient quality.
  Help us specify the standards for the category to be serious enough.

This project was made with love by the University of Delaware Cybersecurity Scholars.

Special thanks to lots of people in this great speedrunning community, from mods and verifiers, to runners streaming and giving feedback, to tourney hosts promoting the category, to the coders and geeks helping me get my code right, to the hypermodernists giving insights into shaving minutes, to the new runners giving me encouragement because it helps them!

gcc csprng.c -I./include -L./libs -lgcrypt -lgpg-error -L. -lcubiomes -lm -lpthread -Wl,-rpath=./libs/ -lminecraft_nether_gen_rs -o seed