# RC Bowling Simulator

A phone web page for trying out the controls of a remote-controlled bowling ball: a first-person view of a regulation lane on the top of the screen and a virtual thumb stick on the bottom.

**Open it on a phone, held upright:** https://zachmaster2.github.io/rc-bowling-sim/

## How to drive

1. Put a thumb anywhere on the bottom panel and push up. The stick's centre is exactly where your thumb lands, so a press by itself does nothing; its ring may run past the panel's edge. The ball travels in the direction the stick points, straight up being straight down the lane; how far you push sets how hard the ball pushes.
2. You stand at the back of the approach and walk up behind the ball as far as the foul line.
3. After each ball a card shows where it hit, the entry angle, the speed, and what published USBC data says a hit like that strikes.
4. **Reset** puts the same ball back at its start at any time.

The gear button opens the settings: control scheme, the stick's response curve, sensing errors, the start board and distance, walking up, the shot log, and **Turn the controller with the phone**. With that on, turning the phone turns the controller's pointing direction and **Recenter** sets "straight down the lane" to where the phone points now (allow motion access when asked).

## The two control schemes

- **A, point and push:** the ball travels where the controller points, turned by the stick's angle. **Stick curve** (on by default) makes the stick less sensitive near straight ahead.
- **B, hold the line:** the push from rest takes the line where the controller points; after that the ball holds that line. Lean the stick and the ball moves over, and the line keeps part of each lean. **Lean slope** sets how much course a degree of lean gives (between 10° and 45° of lean); **Line keeps a lean** sets how long a lean must be held for the line to keep all of it (*never* keeps nothing). Turning the controller after the push does nothing within 15°.
- **Hold button** (off by default; it needs phone turning on): a button for the other thumb, at the left or right of the lane view. Under A, holding it locks where the controller points and letting go jumps back to where the phone points. Under B, holding it lets the phone swing the line and letting go leaves the line where it is.

## Notes

- The lane, its markings and the pins are drawn to regulation dimensions, seen from the eye height of a 5 ft 9 in driver standing behind the approach.
- The view always holds the ball, the lane's width at the ball and the pins, framed as tightly as that allows and never larger than life (life size assumes the phone about 35 cm from your eyes). The pins therefore grow as the ball moves away from you. The ball starts 1.5 m before the foul line, 3 m ahead of you; **Ball start** in the settings moves it.
- The pins fall by rigid-body physics that is not validated for pin carry. The percentage on the result card comes from a published USBC chart (Stremmel, "Entry Angle", Fig. 1) and is the better guide.
- Turning with the phone is off by default. When it is on, motion sensors need a secure (https) page and, on an iPhone, a tap to allow them; without them (a desktop browser, for instance) a drag strip above the stick and the arrow keys turn the controller.
- It is one file, `index.html`, loading three.js r128 and cannon.js 0.6.2 from cdnjs.
