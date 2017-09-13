# PID Controller
---

## Reflections on PID Components

P component: 
* This is the value of CTE.
* This affects the momentum for the vehicle to approach the reference trajectory.
* If the value is too large, the vehicle can easily run off the track with a large steering value.
* In this example, the value of P component was 1.0 initailly, and the vehicle ran off the track in 2-3 seconds. When the value wass set to 0.065, the vehicle can finish half of the track without running off.


I component:
* A cumulation of all previous CTEs. This implies that the value has to be very small. Otherwise, the vehicle would run off the track easily.
* The importance of I component is realized when the track has sharp turns because this component is responsible for the vehicle to adjust back to the reference trajectory.
* Without setting I component, the vehicle could not stay on track when making rapid turns.
* The value would likely to be orders of magnitudes smaller than P components.


D component:
* The difference between current CTE and the previous CTE.
* This affects how fast and smooth the vehicle turns. If set too small, the vehicle would overshoot the refernce trajectory every time. By setting D component, the vehicle would have samller oscillations.
* However, if the value of this component is too large, the vehicle will take too much time to adjust back to the reference trajectory. In a straight line or small turns, large values do not have high impact on the vehicle, but when there is a sharp turn, a large value of D component will make the vehicle to run off the track.


With the right values of these three components, the vehicle can finish the track smoothly. I manually tuned these parameters. In the beginning, I tuned P and D to make sure the vehicle to run a lap without running off the track (but still a dangerous drive!). Then I tuned I component so that the vehicle can stay in safe zone when and after making a rapid turn.




