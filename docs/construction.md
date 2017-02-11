Inverse kinematics, i.e. computation of joint angles out of the gripper’s position can be hard. If the design is too playful, nearly impossible complex. So, it is a good idea to ease the maths by having the upper three axes joining in one point. Later in the chapter Kinematics we will see that with that limitation kinematics becomes possible without having a mathematician at hand (still not easy, but feasible). 

## Dimensioning 

Before starting the design of the construction it is necessary to calculate the torque in all actuators in order to select the steppers and gear ratios properly. In principle, this is simple: The gripper should be able to manipulate 500gr, the forarm has a length of 400mm and the upperarm a length of 350mm, assuming a certain weight per actuator the law of the lever allows to compute the torque of each motor. Tricky part is, that depending on the stepper you choose, the weight of an actuator changes.  In the end I did that computation with excel, and came to these torques 
and gear ratios, which are used to select the stepper dimensions.

| Actuator | ActuatorTorque   | Gear Ratio | Min Stepper Torque | Stepper Size     | Act. Stepper Torque | 
|--------- |------------------| ---------- | ------------------ | ---------------- | ------------------- |
| Wrist    | 0.6 Nm           |  1:4       | 0.18 Nm            | NEMA 17 42x42x39 | 0.4Nm               |
| Elbow    | 0.6 Nm           |  1:7       | 0.11 Nm            | NEMA 17 42x42x25 | 0.17Nm              |
| Forearm  | 11 Nm            |  1:14      | 0.8 Nm             | NEMA 24 60x60x57 | 1.9Nm               |
| Upperarm | 34 Nm            |  1:18      | 1.8 Nm             | NEMA 24 60x60x87 | 3 Nm                |
| Hip      | 8 Nm             |  1:9       | 0.9 Nm             | NEMA 23 57x57x56 | 1.2 Nm              |

The steppers are placed in the previous actuator of the moved actuator in order to move the centre of gravity away from the biggest lever. So, the three  heavy steppers actually do not move when the arm goes up or down.

## Gripper

Due to space limitations, it seems to be appropriate to use a servo for the gripper. I used a standard principle where one lever is driven, in the other lever repeats the same movement by a gear wheel. The servo is hidden in a small box, it is a HerkuleX Robot Servo with 0.12 Nm.

<img width="500px" src="https://github.com/jochenalt/Walter/blob/master/docs/images/cad-gripper.png" >

## Wrist

The wrist is also designed with the same servo. A small flange connects the wrist with the two halves of the gripper housing, the hole hides the cable of the gripper servo. Worth to mention is that the bearings of the wrist have a different size, since the servo looks through the inner hole of the bigger bearing. On the other side, in the middle of the smaller bearing there is the hole for the magnet used by the magnetic encoder of the forearm. The cable of both servos (gripper and wrist) is going through the wrist underneath the servo.

<img align width="800px" src="https://github.com/jochenalt/Walter/blob/master/docs/images/cad-wrist.png" >

## Forearm

The forearm is more complex, the wrist ist driven with a belt drive and a stepper motor with an gear ratio of 1:4. The belt drive is hold tight with a spanner. At the other side of the wrist, the magnetic encoder is located. All cables are meeting in the space at the bottom of the forearm, and going down through the hole of the disk.

<img align width="800px" src="https://github.com/jochenalt/Walter/blob/master/docs/images/cad-forearm.png" >

## Elbow

The elbow consumed most time for design, it is a two stage belt-drive with a ratio of 1:7 and a stepper with 17Ncm. The flange in the middle is the connection to the forearm. It is mounted with two  bigger bearings and has a cable channel with space for a self made cable drag chain that allows to have the cables inside. This was difficult since the centre of the flange was already occupied by an magnetic encoder.

<img align width="600px" src="https://github.com/jochenalt/Walter/blob/master/docs/images/cad-elbow.png" >

## Upperarm

The upperarm contains a strong stepper with 1.9Nm and a two-staged gear with a ratio of 1:14. On the left side a magnetic encoder samples the angle of the ellbow, above the encoder the cable channel is located. The cables are going down through a hole in the middle block down to the left side of the bttom part. The ride side contains the belt to the elbow. All belts are tighened with a clamp that can be adjusted from outside.

<img align width="800px" src="https://github.com/jochenalt/Walter/blob/master/docs/images/cad-upperarm.png" >

## Shoulder

the shoulder contains the strongest stepper moving the upperarm with approx. 3 Nm. A gear ratio of 1:18 could give above 50Nm, but this number more theoretical, since I do not think that 3D-printed parts would survive this. But, this allows to reduce the current and use intense micro-stepping to make the movement more silent and smooth.

On the left flange, there is a segmented cable channel below the location of the magnetic encoder. The right flange has a big hole to make room for the stepper back. This is hidden by a lid that moves with the upperarm, which gives a nice technical touch. Inside the middle block between the flanges, there is a shaft with two  
drive pulleys for the two-staged gearbox, same as in the upperarm.

<img align width="800px" src="https://github.com/jochenalt/Walter/blob/master/docs/images/cad-shoulder.png" >

## Hip

Finally, the hip stepper is what makes the housing of the shoulder look like an iglu. It is a simple belt drive to the shoulder. The shoulder is residing on a drive pulley disk that is mounted on a big bearing.

<img align width="800px" src="https://github.com/jochenalt/Walter/blob/master/docs/images/cad-hip.png" >

## Housing

The housing of the shoulder is not only to hide the hip stepper, but also to stabilize the shoulder by having lots of small bearing on the top edge.

<img align width="800px" src="https://github.com/jochenalt/Walter/blob/master/docs/images/cad-housing.png" >

Continue reading with [Speed Profile](https://github.com/jochenalt/Walter/wiki/Speed-Profile).
