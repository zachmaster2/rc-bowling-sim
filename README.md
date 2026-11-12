# RC Bowling Simulator

A phone web page for trying out the controls of a remote-controlled bowling ball: a first-person view of a regulation lane on the top of the screen and a virtual thumb stick on the bottom.

**Open it on a phone, held upright:** https://zachmaster2.github.io/rc-bowling-sim/

## How to drive

1. Hold the phone like a controller, its top edge pointing down the lane.
2. Tap **Recenter** and allow motion access when asked. That sets "straight down the lane" to where the phone points now.
3. Put a thumb anywhere on the bottom panel and push up. The ball travels where the phone points, plus the angle of the stick; how far you push sets how hard the ball pushes.
4. Turn the phone to steer. After each ball a card shows where it hit, the entry angle, the speed, and what published USBC data says a hit like that strikes.

The gear button opens the settings: control scheme, the stick's response curve, sensing errors, the view (whole lane or zoom), the start board, and the shot log.

## Notes

- The lane, its markings and the pins are drawn to regulation dimensions, seen from the eye height of a 5 ft 9 in driver standing behind the approach.
- The pins fall by rigid-body physics that is not validated for pin carry. The percentage on the result card comes from a published USBC chart (Stremmel, "Entry Angle", Fig. 1) and is the better guide.
- Motion sensors need a secure (https) page and, on an iPhone, a tap to allow them. Without them (a desktop browser, for instance) a drag strip above the stick and the arrow keys turn the controller.
- It is one file, `index.html`, loading three.js r128 and cannon.js 0.6.2 from cdnjs.
