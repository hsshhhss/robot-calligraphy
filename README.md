# robot-calligraphy

The robot-calligraphy application repo

Use cv.cv to extract and store the writing paths of 3000+ commonly use Chinese characters.
Use calligrapht.robot_writing_logics to let UR5 write.


Path and stroke width extraction:
By chronologically parsing the GIFs, the stroke order information can be obtained.


Extraction Procedure:
Transfer the GIF of a given character to an array of JPGs
Only keep the JPGs that contain a whole stroke
Apply gaussian blur to eliminate noises
Apply  CV2 inrange method to separate the red stroke
Apply Zhang-Suen thinning to get the thinned image
Apply BFS on each pixel to get the width of the stoke at that location

Control:
calligraphy.robot_writing_logics would create control points of UR5 tool trajectory for the real world
calligraphy.robot_writing_logics would call easy_ur5.py as API to control the real robot
The velocity of tool trajectory is calculated in easy_ur5.py

Detailed Documentation:
Detailed documentation for a module can be found in docstrings of corresponding modules.

No unit tests are contained in this application, as real robot experiments do tests.
