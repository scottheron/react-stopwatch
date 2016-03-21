#React Stopwatch

Let's build a stopwatch using React. Feel free to use the Codepen starter template and fork it.

http://codepen.io/bhague1281/pen/JXEaeK

To submit, create a pull request with a link to your fork.

##Part 1 - Time display

Create a component called `TimeDisplay` 

* should take a time as a number of seconds (includes fractions) and displays it in a stopwatch format: `00:00:00`
* should have one property called `time`. The `time` should be required and must be a number.
* should maintain the format regardless of the number of seconds (up to `59:59.99`). Examples: `00:01.10`, `01:05.02`, `01:15.12`, etc.
  * Note: You may want to take advantage of the `substr` function to take care of the leading zeroes in the time. That said, if you can't get the format perfect, don't waste too much time and move on to the next parts.
* make sure the component can be rendered to the page.

##Part 2 - Timer

Create a component called `Timer` that includes a `<TimeDisplay />` and 3 buttons (start, stop, clear).

* The timer should default to 0 (`00:00.00`).
* `Start` should make the display count up by "centiseconds" (1/100th of a second).
  * `setInterval` is very handy for this
* `Stop` should pause the timer.
* If start is clicked again it should resume where it left off.
* `Clear` should stop the timer and set it back to 0.
* make sure the component can be rendered to the page.

##Part 3 - Counting laps

Add a "Lap" button to the `Timer` when it is clicked the timer should keep running, but the time when the button was clicked should be stored (added to an array).

* each lap should be displayed in a list below the buttons using the `TimeDisplay` to keep it formatted (use CSS to make the font smaller on the laps if needed).
* each lap time should have the lap number next to it (Lap 1, Lap 2, etc...).

The clear button should clear all laps.

##Bonus - Multiple Timers

Create a component called `StopWatch` when it first loads it should only show a button that says "Add Timer" (or similar).

* `Add Timer` should add a `<Timer />` component to the view each time it is clicked.
* Each `<Timer />` should keep it's own separate time and laps. The start / stop / clear buttons should be independent.
* Each `<Timer />` should have a delete button.
  * The correct timer should be removed.
  * The timer's interval should stop (you'll get errors if it doesn't stop)

####Hints:

* If you want the delete button to be inside of the `<Timer />` component you'll need to pass a function in as a prop.
* Use a unique `key` for each item to ensure the correct item is removed.
* Remember all items in the array after the removed item will be re-numbered.
