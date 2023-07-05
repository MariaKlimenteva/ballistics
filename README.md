# Ballistics

Author : Klimenteva Maria

### The task
The task was to create a model of the movement of a ballistic target and to extend it using the Runge-Kutta method.
You can see the python code in Jupiter Notebook. The following graphs have turned out to clearly show the movement of the bullet:

- #### Height from time
- #### Height from distance
<img src="charts\Высота от времени.png" width=50% height=50%><img src="charts\Высота от дальности.png" width=50% height=50%>

- #### Speed versus time
- #### Speed from distance
<img src="charts\Скорость от времени.png" width=50% height=50%><img src="charts\Скорость от дальности.png" width=50% height=50%>

- #### Acceleration from time
- #### Acceleration from distance
<img src="charts\Ускорение от времени.png" width=50% height=50%><img src="charts\Ускорение от дальности.png" width=50% height=50%>

- #### Target trajectory in 3D
<img src="charts\Траектория 3D.png" width=50% height=50%>


---
---
### A brief description of the work done
1) First of all, I have the equations(coordinate, speed) function. This function calculates the second and first derivatives of coordinates using the system of equations derived in the Prolongation file, where the acceleration components are equal to the components of the second derivatives of coordinates.

2) Next, I use the Runge-Kutta method of 4 orders to convert the obtained second and first derivatives of coordinates into an array of coordinates and speeds, i.e. to lower the order of differential equations.

3) I have the main function get_result(), which, using the initial values (coordinates and speeds at zero point in time) outputs the necessary data in the form of a list.

4) Everything that was received before was in the Greenwich rectangular coordinate system. Therefore, I translate all this into a system related to the target (the local terrestrial coordinate system), using a matrix of guiding cosines (where I found an inaccuracy in the formula in the sign, more about this is written in the code) - the function recalculation_GPSK_MZSK(result).

5) And in the end, I just select individual values from the answer and draw the necessary graphs.
