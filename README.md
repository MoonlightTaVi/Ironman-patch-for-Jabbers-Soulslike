# Ironman patch for [Jabbers Soulslike](https://www.moddb.com/mods/stalker-anomaly/addons/jabbers-soulslike-gamemode)
<br>
There are plenty of add-ons for S.T.A.L.K.E.R. Anomaly, which allow you to respawn after your death. Even though **[jabbersdcs](https://www.moddb.com/members/jabbersdcs "jabbersdcs")** has the most immersive version (you don't just randomly respawn: a stalker brings you to a savespot; and you don't just randomly lose your gear: it is _stolen_), his work (as well as the others' ones) lacks one interesting feature...
<br>
Imagine: you've fallen unconcious; you are rescued; but it is pretty realistic, that you are heavily injured, and have to recover your strength. The game's health system doesn't allow any long-term penalties (you simply eat a medkit and go rushing this stash with your items); even if it had, it would feel dumb.
<br>
I have a different approach: I simply re-use the Ironman's mechanics, so that you have a limited amount of respawns. If you've ran out of "spare lives", you need to recover a bit, so that the life-granter will give you another opportunity to die a stupid death.
<br>
Works great with Sleeping Ironman and Immersive Sleeping.
<br>
**CAUTION:** I am **NO** modder at all. I've just edited a couple of lines. This means that this patch *might* not work properly.
<br>
### Known issues:
* Deaths don't count (always at 0)
* Death counter doubles its values
* You keep respawning, even though you shouldn't
<br>
The issues are caused by the conflict at Ironman's and Soulslike's *actor_on_before_death* callback method (I think). The thing is, I can't understand if it's possible to determine the order of callbacks. Most times the bugs don't happen, sometimes they do. I would appreciate your testing!
<br>
For now I think it's stable, but anything can happen. So, a message to **jabbersdcs** (and any modder, who may be interested): you may finish this tweak and upload to moddb FREELY (crediting *MoonlightTaVi* is optional, but nice). If it is proven to be fixed already, just upload. I am NOT uploading this by myself; I am already frustrated for the fact, that the bugs happen RANDOMLY.
<br>
Possible fix: edit the Ironman's *actor_on_before_death* callback, so that it doesn't count deaths in any possible way (be it statistics or meta). *I don't know how to do that*.
<br>
# Changed files
* *souslike_gamemode_injector_mcm.script* (added the ability to turn both Ironman and Soulslike on)
* *soulslike.script* (changed the *actor_on_before_death* block to count deaths instead of Ironman (but it still counts sometimes, I think) and break out of the respawn function if there are no spare lives)
