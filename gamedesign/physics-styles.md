## 3D First-person Racing Physics Styles:
_Definition, ideas, examples and reasoning behind each of them_

1. Classic Defrag
- 1:1 classic VQ3 and CPM defrag gameplay
- Rulesets are kept intact, and tweaked to be as close as possible to the origina
- Has two leaderboards:
  1. CPM
  2. VQ3

2. Speed Physics
- Based around time-to-complete gameplay.
- Same gamemode as classic defrag, but with custom physics / weapons / powerups / etc
- Uses differential strafing as a core
- Classic gameplay feel, but with added complexity and mechanics

3. Tech Physics
- Oriented towards difficulty-to-complete gameplay.
- Allows/encourages time-to-complete, but to a lesser degree than the Speed Mode.
- Uses differential strafing as a core
- Explained more in depth in [this section]()

### Naming
#### Classic:
- Signals the player, already by its name, that the original defrag mechanics are supposed to be there and preserved as "classic" and intact as possible.

#### Speed:
- Contrasted with classic: Signals the player that a different ruleset from "classic defrag" is to be expected.
- Contrasted with tech: Signals the player that the gameplay is focused around going fast and beating a timer.

#### Tech:
- Contrasted with Speed: Signals the player that the gameplay is focused around technical movement and precision.


## Speed
Features:
- Differential strafing
- No snapzones
- No W-turning
- Crouch-sliding for sharp turns (no slide acceleration. ?maybe?)

- Q2+CPM ramps mix:
  - Sliding up the ramp if no input.
  - Jumping while in the ramp triggers the same loss of speed that cpm does.
  - Double jumping from a ramp has the same 400ms timer as a double jump

- Additive jumps
- sokam-Autojumps (no-boost if auto, but boost if no-auto)

## Tech
_Definition, Ruleset, Concepts and Reference Examples_

VQ3 & Q2 inspired trickjump / tech physics
- Same root physics as q2 / q3
- With added technical mechanics
  - Gives mappers tools to design around difficulty-of-completion value, and not only time-to-complete in isolation.  
_Time-to-complete should be important too, just not the only goal._  

This ruleset creates a mapstyle that is already played in games like Defrag, Quake2, Enemy Territory, Reflex, Diabotical (video examples at the end).  
It aims to join the best pieces and core elements of those games together into one unique game.  

Speed physics are more cpm oriented (i.e. better turning and/or higher speed in general).  
But Tech physics, instead, aim to keep the vq3 and q2 feel, but introduce new tech.  

### Features:  
- Differential Strafing:  
	- Based around vq3 vector control, mixed with cpm ad turning  
	- No w-turning  
	- Reduced AD turn rate.  
	- Increased AD acceleration. Inferior to regular strafing, but stronger than cpm accel.  

- vq3 ground acceleration values (for circlejumping)  
- cpm sliding power values  

- No snapzones  
	- Removal of W-turning makes snapzone-acceleration almost impossible to control / optimize.  
	- Acceleration feels random/unstable without a way to control it.  
	- Skillful strafing is more related to optimization of differential strafing angles.  

- Autojump:  
	- Leaving jump pressed makes you -10% slower (maximum -10%, or else it becomes extremely punishing for new players)  
	- You can still autojump most of the easy/medium maps  
	- Additive jumps can be autojumped, but you reach -10% less height (?maybe -20%?) (?maybe auto-no-boost instead?)  
	- (Difficulty in this should be left for mappers to design, as to not hinder new players that need to rely on   autojump in their early learning stages, because they are overwhelmed by the overall difficulty of the game)  

- General Triggers:  
	- Overbounce  
	- Slide  
	- Surf (slide for ramps??)  
	- Teleport  

- CPM specifics:  
	- Teleport Jumps  
	- Stairs jumps  
	- Headbump double jumps  

- Q2+CPM ramps mix:  
	- Sliding up the ramp if no input.  
	- Jumping while in a ramp triggers the same loss of speed that cpm does, but gives the extra height from the cpm double jump.  
	- Double jumping from a ramp has the same 400ms timer as a cpm double jump  
	- _(the goal of these is to join q2 and cpm ramp physics together)_  

- Downramps: Regular vq3/q2/cpm behavior. Give horizontal speed boost.  
- Surf ramps: Keep vq3 behavior. Add optional surf_surf surfaceflag.  

- Reducing player size mid air:  
	- Allows for fitting through areas/gaps that you would not be able to clear (modified tech from ETjump)  
	- Crouching:  
		- Raises your legs, reducing your hitbox size  
		- Doesn't change the highest level of your hitbox. No difference for ceiling avoidance. (-50% total player height maybe?)  
		- Allows for higher & longer reach of jumps (how much?)  
	- Proning:  
		- Switches your width with your height
		  - Reduces vertical player hitbox size, but increases the horizontal size  
		  - Lowers your hitbox (head), but doesn't change lower hitbox collision point (feet). (aka. doesn't help with higher jump reach)  
		  - For clearing narrow (height) gaps and avoiding hitting the ceiling  

- Ladders  
- Water movement  
	(both from q2)  

- Additive jumps:  
  - Q2 based. The more vertical speed you have, the higher the next jump is. (each jump adds X v.ups to your v.speed? revise q2 code)  
	- _includes ladder+water jumps by making each one's vertical speed the base for the additive jump calculation_ 

- Stances (names/fantasy should be revised):  
	- Based on q2 fps manipulation  
	- Needs a clear HUD indicator of which one is active  
	- Each stance gives you a boost/increase in one type of movement, but reduces the others.  
	  - Balancing:  
		  - +10% / -10% / -5%  
			  - higher numbers = too important / mandatory / punishing  
			  - If higher numbers: Lower skilled players will be too punished/gimped for not being able to manage everything properly  
			  - If lower numbers: Higher skilled players will still be rewarded for their skill by being able to clear the highest difficulty challenges designed by good mappers that can design around the mechanic.  
	- Types:  
		- Balanced/Neutral: Suboptimal in everything (lets say -+0% to all), but allows you to not worry about optimization (overwhelming area/zone or just new to the game)  
		- Sliding stance: Augments sliding power (including both ramps and slide triggers). Reduces Height and Control power  
		- Height stance: Augments vertical speed acceleration. Reduces Speed and Control power.  
			- (including additive jumps and cpm-based ramp jumps. shouldn't affect catapult/push triggers)  
		- Speed stance: Augments/optimizes horizontal acceleration. Reduces Height and Sliding power  
		- Control stance: (greatly?) Reduced acceleration in all directions (included sliding, additive jumps, etc). Augments air/ground control power.  
			- Goal: Fine control, torture-esque maps, avoiding obstacles (improved breaking+handling), tiny platforms.  

- Maps for tech mode:  
	- Technical jumps that require more precision and control than just miliseconds optimization.  
	- Should still be able/encouraged to fight for a better time. Mix of both.  
	- Examples:  
		- https://www.youtube.com/watch?v=dDHPiNrsy5c  
		- https://www.youtube.com/watch?v=9lOlPq_Ys3U  
		- https://www.youtube.com/watch?v=zZNuooB_S_8  
		- https://www.youtube.com/watch?v=q9txEQqDViQ  
		- Technical strafing, but not 100% trickjumping (tech). Although technical, should be considered speed defrag maps.  
			- https://www.youtube.com/watch?v=_6syNv5xfxo  
			- https://www.youtube.com/watch?v=rmOz4U_I17E  


- What should the base mode here have  
- Documentation around the tech  
- Examples  
- A mode is pretty self contained with its identity and features.  

Cvars config:
```md
////////  
//// vq3 good parts  
////////  
sv_strafestyle 3		// (default 0) enables strafing differently depending on the wishdir angle to the velocity.  
// Strafing with halfbeat is a really nice feeling you can normally only have in vq3.  
// Mixing AD turning with Halfbeat is really unique, and I think it should be the core of the new physics settings, which cannot be enjoyed in any other game   
//  
sv_accelerate 10				// (default 10) the amount of ground acceleration
// Having the slower start of vq3 is one of the ways the physics could be controlled, which also helps maintaining the vq3 core feel of the game.  
// Another value to be considered for ground accel might be 0.85 or 0.9 (0.75 seems too slow). This would make vq3 circlejump heavy maps ported from defrag much more difficult to clear. Might not be a good thing, just to compensate for differential. But should be reconsidered to balance slide surfaces speed increases in relation to overall acceleration speeds. Slide power might be able to be balanced programatically in other ways (i.e. unique sliding cvars)  

////////  
//// cpm good parts  
////////  
// W turning:  
// Makes the game more accessible to new players. But it also dumbs down the skill requirement of some maps.  
// Does not work well with differential-vq3-style, because it removes the need to control your directional vector at all, removing a core vq3 element/mechanic with it.  
//  
// AD turning  
// Half the amount of control of CPM, but double the acceleration.  
// Keeps the vq3 gameplay feel from being erased from the game just because of adding AD turning.  
// Higher acceleration helps with not feeling punished for having to AD-turn a lot in turn heavy maps.  
// But the acceleration is still lower than regular/halfbeat straight strafing.  
// So you still need to optimize your directional vector and route to get a better time.  
sv_aircontrol_enable 0				// (default 1) enables aircontrol. activated when wishdir is less than the minimum q3 strafe angle.  
sv_maxairstrafespeed 60				// (default 30) max speed when strafing with A/D (CPM only  
sv_airstrafeaccelerate 3			// (default 6.7) acceleration when strafing with A/D (CPM only)  


////////  
//// Common to both  
////////  
//// Snap Zones  
sv_snapvelocity 0				// enables rounding velocity to ints every frame (default 1 from defrag)  
// Maybe yes with snaphud. Needs testing both to compare.  
//  
//// Autojump  
sv_autojump 1					// enables auto-jumping (default defrag 0)  
sv_scalecmd_fix 1				// fixes slowdown on jump input if enabled (default defrag 0)  
//////// Autojump, plus removing slowdown on jump (currently -50%, not configurable, so it is disabled for now)  
////////  
////////  
//////// ToDo: Additive jumps cvars 
```
