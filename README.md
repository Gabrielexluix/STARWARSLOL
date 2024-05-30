# OPENCVSTARWARS
In this project, we focused on creating an environment that is fun, impressive, and particularly challenging to develop. First, we organized ourselves to select the game for our project, and we chose "Star Wars Rogue Squadron."
We chose it due to its intuitive, fun, and easy-to-understand gameplay. Additionally, one of our team members owns the main ship from the game as a toy (the white ship with red stripes, same as the one on the game cover shown in an image above). This ship will be used later for a demonstration where camera sensors will link the ship's movements to the game. Red paper sheets will be added to the ship to improve movement detection, and RGB lights were considered for more FPS, but we opted for paper sheets for realism.
We started working on the functional part of our code and motion sensors, encountering various issues such as the camera having difficulty detecting movements, and our code presenting some errors. The most serious problem was that the game did not detect the camera's movements, hence not recognizing the assigned controls. This problem caused several days of delays and headaches. We will present each function and tool in the project's code so you can understand its functionality and enjoy it fully.
Lastly, it is important to clarify that this project was carried out in collaboration with JellyMan46766 and 185239.github.io , and myself. You might also find the documentation on their profiles. Additionally, we include a demonstration video of the final result. Below, I will attach the descriptions and functions of the code.

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
Function to move the mouse cursor by dx, dy
void MoveMouse(int dx, int dy) {
    POINT cursorPos;
    GetCursorPos(&cursorPos); // Get current cursor position
    SetCursorPos(cursorPos.x + dx, cursorPos.y + dy); // Set new cursor position
}
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////



Libraries Included:

opencv2/core.hpp and opencv2/opencv.hpp: For OpenCV functions and classes.
iostream: For standard I/O operations.
vector: For using the std::vector container.
windows.h: For Windows-specific functions like mouse events.
Function MoveMouse(int dx, int dy):

Gets the current cursor position.
Moves the cursor by (dx, dy).
Function SimulateMouseClick():

Simulates a left mouse button press and release with a delay in between.
Main Function:

Initializes video capture from the default camera.
Sets HSV thresholds for color calibration, mouse movement control, and click control.
Creates a window for adjusting color thresholds using trackbars.
Continuously captures frames from the camera.
Converts the frames from BGR to HSV color space.
Creates masks based on the HSV thresholds for movement and click detection.
Finds contours in the masks.
Identifies the largest contour for movement and click masks.
Calculates the centroid of the largest movement contour.
Moves the mouse based on the centroid's position.
Simulates a mouse click if a large click contour is detected.
Displays the masks and the original frame.
Exits the loop if the ESC key is pressed.
Mouse Movement Logic:

Divides the frame into sections.
Moves the mouse in different directions based on the section where the centroid is located.
Mouse Click Logic:

Simulates a mouse click if the largest click contour's area is greater than 600.
Exit Condition:

Breaks the loop and exits the program if the ESC key is pressed.
