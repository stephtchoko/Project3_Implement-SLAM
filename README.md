Project 3: Implement SLAM
Project Overview
In this project, you'll implement SLAM for robot that moves and senses in a 2 dimensional, grid world!

SLAM gives us a way to both localize a robot and build up a map of its environment as a robot moves and senses in real-time. This is an active area of research in the fields of robotics and autonomous systems. Since this localization and map-building relies on the visual sensing of landmarks, this is a computer vision problem.

Using what you've learned about robot motion, representations of uncertainty in motion and sensing, and localization techniques, you will be tasked with defining a function, slam, which takes in six parameters as input and returns the vector mu.

mu contains the (x,y) coordinate locations of the robot as it moves, and the positions of landmarks that it senses in the world

You can implement helper functions as you see fit, but your function must return mu. The vector, mu, should have (x, y) coordinates interlaced, for example, if there were 2 poses and 2 landmarks, mu will look like the following, where P is the robot position and L the landmark position:

mu =  matrix([[Px0],
              [Py0],
              [Px1],
              [Py1],
              [Lx0],
              [Ly0],
              [Lx1],
              [Ly1]])
You can see that mu holds the poses first (x0, y0), (x1, y1), ..., then the landmark locations at the end of the matrix; we consider a nx1 matrix to be a vector.

Generating an environment
In a real SLAM problem, you may be given a map that contains information about landmark locations, and in this example, we will make our own data using the make_data function, which generates a world grid with landmarks in it and then generates data by placing a robot in that world and moving and sensing over some numer of time steps. The make_data function relies on a correct implementation of robot move/sense functions, which, at this point, should be complete and in the robot_class.py file. The data is collected as an instantiated robot moves and senses in a world. Your SLAM function will take in this data as input. So, let's first create this data and explore how it represents the movement and sensor measurements that our robot takes.
