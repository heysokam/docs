# Analysis on Crouchsliding  
_Why this mechanic turned the original Quake 4 into a cpm-style fast paced game,_   
_and how that fits into 3D fpracing physics_  

_This article became a bit longer than expected._
_Go to [Conclusion](https://github.com/heysokam/docs/blob/master/gamedesign/crouchsliding.md#conclusion---tldr) to read just the tl;dr version._  
## Overview
Quake was originally made for multiplayer pvp.  
But the movement code/mechanics have sticked with us throughout the years.  

Quake3 movement was "slow".  
It was argued that it wasn't "pro" and skillful enough. And that they removed all of the charm that QuakeWorld/Quake2 had with their ramp mechanics and AD turning.  

Or at least that's what some Quake fans thought back in the day.   
So they figured they could improve vq3 by adding back those mechanics, that were really good about previous Quake games, but that the developers were not implementing into their new games themselves.   
*(rampjumps, AD-turning, faster overall pace, etc)*   

That is, in my opinion, how the classic CPMA movement ruleset came into existence.   
Literally, a Frankenstein of previous mechanics that WORKED and were really FUN, but were forgotten by the original Quake devs.   
Marked as "unintended bugs" instead of "fun features".    
But properly tweaked and balanced together to make the fun to play movement style that now everybody knows.     
Making the end result not at all a Frankenstein, but a unique and distinct fun to play movement game.  

This argument can be proven very simply by analyzing Quake Champions, and what the Quake devs are now doing with movement in their own game, having learned from their previous mistakes:   
- Classic VQ3 : Visor
- CPMA : Anarky, Sorlag
- Quake 4 : Slash
- New Tech : Nyx  (warsow/titanfall wallkicks, +doublejumps midair)

Thinking about it this way, there is NO DOUBT as to why Rapha is such a GOD with Visor.  
Or how Toxjq can be so impossible to stop with Slash.  

How could they not be!  
They are, quite literally, champions made for their unique strategies, movement and playstyle.  
These guys were top-tier gods when those games were at their peak back in the day, and they are still top-tier gods now with the same movement rulesets in QC.   

_I would argue that Vo0 or Rat would be just as good with Anarky/Sorlag if they weren't so strongly limited by the hardcoded speed cap, but that's a topic for another day._  

## Improvement potential
Quake4 implemented crouchsliding to make duels faster (aka more pro/skilful) than Q3, but not impossibly fast like CPMA was proven to be.   

A 3D fps racing game doesn't have those duel/combat requirements, so there is room for modification and improvement, since the game is fully oriented towards movement and that's all we need to worry about.  

You could have three different types of cornering, with different drawbacks/benefits, and that would make the game more complex/interesting than only having one.   
That's irrelevant for a duel setting (or even redundant, since one of them can be proven superior in combat and outrule them all), but could be an essential thing for a movement oriented game.   

If we assume that "more unique/distinct movement options" equal "better movement game", then I think the addition of a well balanced crouchsliding mechanic can be highly beneficial to a CPM-influenced ruleset.  

## Movement comparison: VanillaQ3 vs CPMA vs Quake4
Watch these duels, and keep these questions in mind:  
- **How does Quake4 compare to Quake3?**   
   _(Acceleration mechanic, optimal gamestyle, positional play vs rushing)_
- **How does CPMA compare to VanillaQ3?**  
  _(slowing down for corners = slower game = positional play is more rewarded._  
   _not stopping at all = impossibly fast pace)_
- **What does CPMA have in common with Quake4?**  
  _(pay attention to stairjumps, rampjumps, cornering/turning, overall speed/pace of the game)_  

vq3: https://www.youtube.com/watch?v=tU6v8C1pw8Y   
cpm: https://www.youtube.com/watch?v=7dMGrop2zeQ   
q4: https://www.youtube.com/watch?v=KHCNWdKtUEc  

Let's focus on their essential movement, which is what's important for us.  
VanillaQ3 is the slowest of the three, clearly. Everybody knows that.   
But... why? Think about it.  

Ask yourself these questions:  
- What makes you faster?
- What slows you down?  
- Who wins in a 100m running sprint race?
- Who wins in a Car Racing competition?
- And, more importantly: Who loses in those?

The simplest answer to all of them is in one word: -Acceleration-   
- No acceleration = No movement  
- Negative acceleration (deceleration) = Slower overall speed/time  
- Higher acceleration = Faster time    

But what exactly influences that acceleration?  
That's one of the cores answers of this article.

_(The Q3 formulas for acceleration are out of scope for this article. Watch: https://www.youtube.com/watch?v=rTsXO6Zicls)_  

### Essential movement factors
In essence, every movement competition (even real life physics) is based around two elements:  
1. Cornering  (aka, shorter distance & how to decelerate less than others)
2. Speed (and with it, acceleration, because more accel = more speed)  

As you can see, both are actually related to acceleration.  
_(either positive or negative, respectively)_  

So, how does each game handle these two factors?   
Considering that the optimal acceleration mechanic is more or less equal in all of them (diagonal strafing with A/D+W), lets look at how their unique cornering mechanics are similar/different to each other:
- **VQ3**:   
  Does not allow for vector redirection. Requires strategic bumping into things to navigate.
  - Only diagonal acceleration.  
  - Strongly limited turn-rate.  
  - Requires stopping down to walkspeed and then circlejumping...  
  - or bumping into walls or diagonal/rounded corners to redirect the speed vector to a better/shorter line.
- **CPM**:  
  Allows the player to redirect their current speed into a different direction, under very specific conditions:  
  - limited corner radius, dependent on Speed
  - limited acceleration
  - AD & W are well balanced against each other and distinct/unique
- **Q4**:  
  Allows the player to redirect their current speed into a different direction, under very specific conditions  
  - requires crouching
  - constant deceleration by friction (speed cost)
  - limited corner radius (same tool that AD uses to balance its power in cpm)

As you can see, both CPM and Q4, in essence, achieve the exact same thing (higher turn rate + vector redirection).  
BUT, what makes them similar is their **cornering style**, and not their acceleration style. That's why I would associate Q4 crouchsliding with AD turning, and not with VQ3. Even if Q4 had the same straight line acceleration style than VQ3.  

Neither CPM nor Q4 give the player an infinite turn-rate, though.   
They have rules for when a higher turnrate can be achieved and how.   
Those situations are difficult to master and mechanically challenging in both games (AD-turning and W-turning for CPM, and Crouchsliding for Q4). And, in my opinion, this is what makes them interesting in their own unique ways.  

Although, if you think about it... they achieve the exact same outcome. Just in different ways.  
So, you could argue that they are not distinct, and one of them should be rejected.  
But this is where I saw something different, and how I think crouchsliding fits 3D fpracing games.  
This is the reason why this text exists.  

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::
***

# Conclusion   (TL;DR)
*This is a short conclusion to this article*   
*If you don't want to read the explanation of how/why this idea started, then just start here.*  
## My Crouchsliding vision
_and analysis of why crouchsliding can fit 3D fpracing games_  
### What is crouchsliding
#### 1. Cornering:
Like it was mentioned, crouchsliding can be seen as "just another turning mechanic, equal to the others and irrelevant".   
And this is true, but only if you think about what it DOES, and not what it COULD do.   
Which is: The potential for using it in corners of different radiuses than what AD or W can possibly achieve in CPM.    

Example:  
- Sharp corner
- 180 degrees
- 64u radius
- 400u maximum width
- approached at +1500ups or more  

That's literally an impossible corner for AD or W without oversteering or bumping into the wall,  losing -at least- 200ups.    
_(see r7_tech for an example of this: https://youtu.be/WOwLF0MFRQ8?t=13)_

But, with the right cvar values for it, it can be made to require skilful control to execute a sharper turn than AD, at the cost of some speed.   

This way, the player would have to make a choice for their route strategy:  
1. Do I want to use AD for this turn?  
  Considering:  
  - Easier to execute (slightly)
  - Allows me to maintain all my speed (or increase it)
  - Increased overall distance/radius.  
  - Is that extra speed worth the increased overall distance?  
2. Or do I use crouchsliding:  
  Considering:  
  - Harder to execute  
  - Gives me the shortest overall distance.
  - Costs me some speed no matter what, but its effect can be minimized with my skilful control.   

This crouchsliding definition might conflict with AD's oversteering to slow down. But it doesn't with the optimal use of AD for full speed turns. And this use of AD for slowing down with oversteering doesn't consider the reduction of player height that occurs during crouchsliding.   

The reduction in player height during crouchsliding is an aspect of the mechanic that will open even more obstacle options for mappers, and some turns very unique to the mechanic (ie. same corner as before, but going under low beam or into a hole in the wall).  

#### 2. Reduced player height:
Lowered player-collision height is only possible to execute in CPM/VQ3 by being submitted to the full effect of ground friction.  
Height-based obstacles are possible, but their cost is extremely high. This cost makes them extremely difficult and punishing to implement in a map.

Crouchsliding allows the mapper to design those same obstacles mentioned, but without punishing the player so strongly.  
It opens the option to design shortcuts/obstacles that cost just a bit of speed, instead of making the player lose it all no matter what they do.    

The skilful aspect of the mechanic also allows for this strategic choice:   
"Do I choose the faster, but harder to execute, path? Or do I take the longer/easier line?"    
Regular crouching would make that choice not possible, because the speed cost is just too high    
_(and it takes no skill to go under a crouching obstacle without sliding, so there is nothing to master/improve about it)_.  

### Crouchsliding in vq3 influenced physics
_Why the added turning rate of CS doesn't belong in vq3 & Tech physics, but the reduced player height might._  
Like it was mentioned before, what makes vq3 and cpm different is not their straight line acceleration mechanics, but their cornering styles.    

Adding the increased turnrate and vector redirection aspects of crouchsliding to VQ3 changes the physics into, essentially, a different version of CPM.
If we want to design a unique VQ3-influenced style, then maintaining that reduced turnrate as much as possible is essential to its design.  

This is why regular crouchsliding doesn't fit `phy_tech`.  
But a different crouchsliding configuration will, because it would allow for the reduced player height aspect of the mechanic, without turning the setting into "just cpm, but without AD".    
A simple `sv_crouchslide_accelerate 0` would achieve this effect perfectly.  
_(removes turning completely during crouchsliding, while keeping its reduced friction and height)_    
It is also simple to explain: "You cannot turn while crouching in phy_tech, but you can crouchslide in both"  

### Crouchsliding in Speed physics.  
Crouchsliding can coexist with AD and W, without neither of them being redundant and irrelevant.    
Making crouchsliding fit in a unique way with CPM-influenced physics is not an issue with the mechanic itself.  
It is just a matter of balancing it properly, so that they don't overlap.  

Starting point:
```
phy_crouchslide_accelerate 80;  
phy_crouchslide_friction 0.7;  
phy_crouchslide_threshold 700;  
```
