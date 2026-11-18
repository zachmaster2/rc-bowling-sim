# RC Bowling Simulator

A phone web page for trying out the controls of a remote-controlled bowling ball: a first-person view of a regulation lane on the top of the screen and a virtual thumb stick on the bottom.

**Open it on a phone, held upright:** https://zachmaster2.github.io/rc-bowling-sim/

## How to drive

1. **Two sticks** (hold the phone in both hands). Put your left thumb anywhere on the left of the bottom panel and push up: that is the main stick. Its centre is exactly where your thumb lands, so a press by itself does nothing; its ring may run past the panel's edge. The ring stays where your thumb landed for as long as you hold it, however far your thumb goes: past the ring's edge the knob stops on the ring and the stick reads the direction from the ring's centre to your thumb (so to turn the ball round, bring your thumb back past the centre). The ball travels in the direction the stick points, straight up being straight down the lane, and how far you push sets how hard the ball pushes. The main stick is one for one: the trigger, below, is what holds a line. Your right thumb, anywhere on the right of the panel, works the **precision stick**: a second stick of the same size, of which only left–right is read. Push it left or right for small aims (up to 5° by default); let go and the aim springs back to straight. While that thumb is down, the main stick is held as it is: see the trigger, below.
2. You stand at the back of the approach and walk up behind the ball as far as the foul line. **Walk up with the ball** has two ways: **+ zoom** (the default) also closes the view in on the ball and the pins as the ball goes; **Walk only** keeps the view's zoom and tilt from the start, so walking up shows as walking.
3. After each ball a card shows where it hit, the entry angle, the speed, and what published USBC data says a hit like that strikes.
4. **Reset** puts the same ball back at its start at any time.

The gear button opens the settings: the precision stick, sensing errors, the start board and distance, walking up, the shot log, and **Turn the controller with the phone**. With that on, turning the phone turns the controller's pointing direction and **Recenter** sets "straight down the lane" to where the phone points now (allow motion access when asked).

## Two sticks, the trigger and LOCK

- **Precision range** sets how far full left or right on the precision stick moves the aim (±5° by default).
- **The trigger** holds the main stick as it is. While the main stick is pushing, squeeze the trigger and keep it squeezed: the stick's angle and strength are held, and you can take your thumb off it (or move it by accident) without the ball noticing. Everything else still works: the precision stick makes its small aims, turning the controller still steers, and STOP still brakes while it is pressed - let STOP go and the held push is back, so short presses of STOP trim the speed. Let the trigger go and the main stick has the ball again (with no thumb on it, the push ends). Squeezed with nothing being pushed, it holds nothing. Reset and a new ball end it. **On a phone the trigger is your right thumb: while it is down on the precision stick, the main stick is held** - push with the left thumb, put the right thumb down, lift the left, aim with the right, and lift the right to let go. The held stick stays drawn in amber where it was taken. On a game controller it is the left trigger (and the right trigger is STOP).
- **LOCK** (between the sticks) appears whenever the pointing direction can turn: with **Turn the controller with the phone** on, or with the RC Bowling controller connected. Press it and the pointing direction is frozen where it was: turning no longer steers, only the sticks do. Press it again to steer by pointing again. Every new ball, and Reset, starts unlocked, so the first push always goes where you point. While it is on, the button is lit and the top bar says LOCKED; the blue course arrow stays put while the amber pointing marker follows the phone.

## How the ball answers

- **Point and push:** the ball travels where the controller points, turned by the main stick's angle; how far the stick is pushed sets how hard the ball pushes.
- **Changing direction:** a push ahead of or beside the way the ball is rolling turns the ball onto your push at full thrust, and it keeps its speed; a push back against its roll slows it on its own line, and then it goes where you push (between 90° and 110° from its roll the one runs smoothly into the other).
- **Course arrow** (on by default): the blue arrow at the foot of the lane view shows where the ball is being sent right now: where the controller points (LOCK's frozen aim while it is on), turned by the main stick (the held stick while the trigger is squeezed), plus the precision stick. The amber **pointing marker** beside it (with phone turning on) shows where the phone points, so a LOCK shows as the two arrows parting.

Settled on 17 November 2026 and not settings: two sticks, both regular sticks of the same size; the direct change of direction; the stick read from its ring's centre; the precision stick as an offset that springs back. What was tried before and removed is no longer in the page at all: the one-stick controls (the stick curve, the Hold button), the second scheme (hold the line), the main stick's centre band, the precision stick as a slider, Nudge, and the earlier law for changing direction. A phone that had any of those stored simply drops them.

## Driving it with the controller, on a TV

The simulator also reads a Bluetooth gamepad through the browser's Gamepad API, so that a hand-held controller can drive it on a big screen: a laptop running the page in Chrome, shown on a TV over HDMI. An iPhone cannot host such a controller (iOS accepts only console and MFi gamepads, and Safari has no Web Bluetooth).

1. Pair the controller with the computer (Windows: Settings > Bluetooth & devices > Add device; it appears as "RC Bowling Controller"), open the page in Chrome, and press any button on it; Chrome shows a gamepad to a page only after a button press.
2. While a controller is connected the touch panel is hidden, the lane view fills the screen, the text is sized for a TV, and its sticks and its STOP, LOCK and trigger keys are drawn in the lower left corner.
3. The stick drives exactly as the touch stick does. The controller's own turn (its gyro) sets the pointing direction, as the phone does with phone turning on.
4. **STOP** brakes the ball while it is held, as hard as the lane's grip allows; on the result card it takes the next ball. **LOCK** freezes where the controller points until it is pressed again; the **trigger**, while held, holds the main stick (above). **Recenter** sets straight ahead to where the controller points now, and **Reset** puts the ball back.
5. A standard game controller (Xbox, PlayStation) drives with its left stick and makes small aims with its right stick. Its left trigger is the trigger and its right trigger is STOP (Setup can move both). It cannot sense turning, so LOCK does not appear with it.
6. **Settings > Controller** shows what the page sees of it: its axes and the buttons being pressed. **Setup** sets which axis and button does what, so a different gamepad works too.

The stage-1 controller is a design of its own: a printed two-handed shell laid out like an Xbox 360 controller, an ESP32-S3 board, an IMU, two thumb-sticks and four buttons, no soldering. Its firmware (2.3) reports the left stick on axes 1 and 2, the turn on axis 3 (heading / 180°, positive to the right) and the right stick's left–right on axis 4, and STOP, LOCK, Recenter and Reset on buttons 1 to 4. The sticks only move: pressing one down is not reported. These are the page's defaults.

## Notes

- The lane, its markings and the pins are drawn to regulation dimensions, seen from the eye height of a 5 ft 9 in driver standing behind the approach.
- The view always holds the ball, the lane's width at the ball and the pins, framed as tightly as that allows and never larger than life (life size assumes the phone about 35 cm from your eyes). The pins therefore grow as the ball moves away from you. The ball starts 1.5 m before the foul line, 3 m ahead of you; **Ball start** in the settings moves it.
- The pins fall by rigid-body physics that is not validated for pin carry. The percentage on the result card comes from a published USBC chart (Stremmel, "Entry Angle", Fig. 1) and is the better guide.
- Turning with the phone is off by default. When it is on, motion sensors need a secure (https) page and, on an iPhone, a tap to allow them; without them (a desktop browser, for instance) a drag strip above the stick and the arrow keys turn the controller.
- **The shot log** (Settings > Copy shot log) keeps the last 60 balls. Each holds the settings it was driven with (`set`), one row every 0.1 s (`series`; `cols` names the columns: `t, x, y, vx, vy, psi_c, stick_deg, stick_defl, eye_s, fine_deg, locked, held` - the stick columns are the raw main stick, whatever the trigger holds) and the intervals of LOCK, the trigger and STOP (`lock`, `trig`, `stop`). Logs made before the evening of 17 November 2026 also carry the removed options' columns (`reaim_deg`, `line_psi0`) and settings.
- It is one file, `index.html`, loading three.js r128 and cannon.js 0.6.2 from cdnjs.
