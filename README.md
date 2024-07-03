# Algorithm-For-Controlling-The-Leg-Movement-Of-Robot
## This pseudocode provides an overview of the algorithm steps required to control the leg movement of a legged robot:
```
// Initialization
attachServos()  // Connect the hip and knee servos to the microcontroller
setInitialPositions()  // Set both hip and knee servos to 90 degrees

// Define Parameters
stepLength = 30  // Length of each step (in degrees)
footLiftHeight = 60  // Height of foot lift (in degrees)
movementSpeed = 50  // Speed of movement (in milliseconds)

// Leg Movement Loop
while (true):  // Repeat the walking cycle indefinitely
    // Lift the Leg
    incrementallyRotate(hipServo, 90, 120)  // Rotate hip servo from 90 to 120 degrees
    decrementAngle(kneeServo, 90, 60)  // Decrease knee servo angle from 90 to 60 degrees
    delay(movementSpeed)

    // Swing the Leg Forward
    incrementallyRotate(hipServo, 120, 90)  // Rotate hip servo from 120 back to 90 degrees
    incrementAngle(kneeServo, 60, 90)  // Increase knee servo angle from 60 back to 90 degrees
    delay(movementSpeed)

    // Lower the Leg
    incrementAngle(kneeServo, 90, 120)  // Increase knee servo angle from 90 to 120 degrees
    maintainAngle(hipServo, 90)  // Keep hip servo at 90 degrees

    // Shift Weight
    incrementallyRotate(hipServos, 90, 80)  // Shift weight by rotating both hip servos from 90 to 80 degrees

    // Repeat for the Opposite Leg
    // (mirror the sequence of actions for the other leg)
```
## Explanation:

### Initialization:
  attachServos(): This function would connect the hip and knee servos to the appropriate pins on the microcontroller.
 
 
  setInitialPositions(): This function would set both the hip and knee servos to the neutral position of 90 degrees, preparing the robot to stand still.
### Define Parameters:
  stepLength: The length of each step, measured in degrees of servo rotation.

 
  footLiftHeight: The height of the foot lift, measured in degrees of knee servo rotation.

 
   movementSpeed: The speed of the leg movement, measured in milliseconds of delay between servo angle adjustments.

 
### Leg Movement Loop:
Lift the Leg:


incrementallyRotate(hipServo, 90, 120): Gradually rotate the hip servo from 90 to 120 degrees to lift the leg.


decrementAngle(kneeServo, 90, 60): Decrease the knee servo angle from 90 to 60 degrees to lift the foot.


delay(movementSpeed): Introduce a delay to ensure smooth motion.


Swing the Leg Forward:


incrementallyRotate(hipServo, 120, 90): Gradually rotate the hip servo back from 120 to 90 degrees to swing the leg forward.


incrementAngle(kneeServo, 60, 90): Increase the knee servo angle from 60 back to 90 degrees to straighten the leg.


delay(movementSpeed): Maintain consistent timing for fluid motion.


Lower the Leg:


incrementAngle(kneeServo, 90, 120): Increase the knee servo angle from 90 to 120 degrees to lower the foot.


maintainAngle(hipServo, 90): Keep the hip servo at 90 degrees to position the foot correctly.


 Shift Weight:


incrementallyRotate(hipServos, 90, 80): Shift the body's weight by rotating both hip servos from 90 to 80 degrees.


Repeat for the Opposite Leg:


The same sequence of actions would be executed for the other leg, mirroring the movements.


Continue the Cycle:


The leg movement loop would repeat indefinitely to maintain a smooth and balanced walking motion.
