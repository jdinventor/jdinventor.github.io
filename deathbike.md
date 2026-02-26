---
layout: page
title: "Deathbike: Cheap Performance eBike"
permalink: /deathbike/
---

![picture](/images/eBike.jpg)

The Deathbike project is exactly what it sounds like: my attempt at being as safe as possible on two wheels! This beauty consists of:
- A $20 mountain bike off FB Marketplace. Yes, it doesn't even have disc brakes
- Generic eBay 1.5kW motor/controller kit (controller was later upgraded to a VESC)
- 2x 48V 307Wh battery packs & 13s dumb BMS from my favorite budget vendor, [Battery Hookup](https://batteryhookup.com/)
- Custom 3D-printed battery box using my base-model Ender 3 
- Generic eBay 48V charger (I never charged this unattended and checked battery voltage manually to confirm end of charging)

Well, did I achieve my goal? Sorta. All-in, I think I'm $650-$700 into the build, and the bike certainly was fast. It could do wheelies if I threw my weight back, and the top speed was ~35mph (which is no slouch by any means). And that was all without the VESC controller, which would actually allow me to uncork things. However, after switching to the VESC controller, I ended up shearing the axle shaft due to a tuning mistake. While I knew the change I made was dumb, it took me a while to figure out what exactly I did wrong.

In short, I was trying to tune out a crunching feeling the motor was making during the transition from sensored to sensorless operation. In my infinite wisdom, I decided to lower the transition threshold, then test it out by cranking the throttle. I made it about 5 feet before I heard a loud snapping sound and turned back to see the rear wheel completely lilted. 

After doing some reading, I figured out that because I dropped the sensorless transition lower, there probably wasn't enough BEMF from the motor for the controller to accurately compute position. So it probably lost sync and threw current in randomly, causing the axle to snap. It is likely also related to current regulation issues with the PID loops, which if I datalogged phase currents, might've provided some insight.

So what's next for the bike? Well, right now it's in pieces. But my plans for it are:
- Add a temp sensor and ferrofluid to my new motor so I can crank up phase currents until things just start to cook
- Add the second battery pack for more range and reduced voltage sag under load
- Add a bluetooth module to the VESC so I can datalog on my phone 

We'll see if I ever get around to any of that lol