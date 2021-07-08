# Multi-Dimensional-Kalman-Filter

Our state vector:
X = [ x ẋ y ẏ]
The following equations will help us to design our state matrix (phi) :
x = x0 + ẋ ∗ dt
y = y0 + ẏ ∗ dt

Xo = [ x_o_gps ẋ_o 𝑦_𝑜_𝑔𝑝𝑠 ẏ_o ]
For ẋo and ẏo we could make line fit and get them from gps


Here we design our Conversion matrix so it correspondence to the reading from both sensors
Linear acceleration sensor (after double integrating it to get position) and GPs
Z = [ x_gps x_acc y_gps y_acc]


For measurement noise I consider the gps to have error of 5 meters and linear acceleration sensor 
have very noisy data so I will make it’s error 25 meters

For P initial values we can initate it with high values and it will diverge eventually


Even if we started P with different values it will diverge to same P after some iterations

The green line is our gps measurments
The black line is linear accelormter measurments
The blue line is our Filtred values
The red line is our model values

Conclusion:
Despite the very noisy measurment from linear accelormeter that goes to the extend of corrupted 
sensor measurments the Multidimensional Kalman Filter could handle it and adjust it’s weight 
matrcies to this and give us good values …. We just need to check our sensors variance and panlize 
sensors with bad measurments so the algorthim give us better values and also as the algorithim 
we move in iterations it will adjust it’s P and K matrcies to gives balanced weights based on our 
measurments and noise
