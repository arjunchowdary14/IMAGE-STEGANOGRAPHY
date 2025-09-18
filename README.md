This Python script is a desktop application that allows users to hide secret text messages inside images or videos and reveal them later.
It uses a technique called steganography, which is the practice of concealing information inside other data so its presence is not obvious.

The program is built with several external libraries:

1.Tkinter is used to build the graphical user interface, including windows, buttons, and text boxes.
2.Pillow (also known as PIL) is used for opening and editing images.
3.Stegano provides ready-made algorithms for hiding text in the least significant bits of an image.
4.OpenCV and NumPy handle video files and frame processing.

When you launch the script, a window appears with two choices: Image Steganography and Video Steganography.
Depending on which one you choose, the program opens the corresponding tool. Both tools share a similar structure.

Imports

At the beginning of the script, several modules are imported:

1.Tkinter and its filedialog module load all the GUI components and the file selection dialog.
2.Pillow’s Image and ImageTk classes handle images and prepare them for display inside Tkinter.
3.The os module provides basic operating system utilities.
4.Stegano’s lsb module implements least significant bit steganography.
5.OpenCV (cv2) manages video and image processing.
6.NumPy is used for handling numerical data, such as arrays of pixels.

The Main Menu:

1.The main_menu function creates the first window the user sees.
2.It sets the title, size, and background color of the window, then displays a heading and two buttons — one for Image Steganography and another for Video Steganography.
3.Each button closes the menu and opens the relevant tool.
4.Finally, the program enters Tkinter’s event loop, which keeps the application running and waits for user input.
5.Image Steganography Tool
6.The image_steganography function opens a new window dedicated to working with images.

Inside this window, you can:

1.Select an image and preview it.
2.Enter a secret key and a message.
3.Hide the message inside the image with the key attached.
4.Save the resulting image as a new file.
5.Reveal any hidden message if the correct key is provided.

The layout is organized with frames:

1.A bar at the top lets you enter the key.
2.The center displays the selected image.
3.A text box with a scrollbar allows you to type or read a message.
4.Buttons along the sides let you open an image, save the hidden version, hide data, show data, or return to the main menu.
5.Video Steganography Tool
6.The video_steganography function has a similar layout, but it works with video files.

You can:

1.Select a video and view its first frame.
2.Enter a key and a message to hide in that frame.
3.Save a new video where the first frame contains the hidden data.
4.Reveal the message later by reading the modified frame.
5.Only the first frame of the video is changed, so you must keep the file that holds that frame if you want to recover the secret later.
6.Program Entry Point
At the bottom of the script is this line:

if __name__ == "__main__":
    main_menu()
    
This tells Python to start the program by running main_menu if the file is executed directly, rather than being imported by another script.

Key Concepts

1.Graphical User Interface (GUI) is the visual part of a program, including windows, buttons, and text fields.
2.Widgets are individual GUI elements such as labels, buttons, or text boxes.
3.An event loop keeps the application open and responds to user actions.
4.Frames in Tkinter group widgets into sections for better organization.
5.Steganography hides information inside other files.
6.The Least Significant Bit (LSB) is the smallest bit in a byte, and changing it slightly alters an image without visible differences.
7.Pillow handles image editing and saving.
8.OpenCV processes video files and frames.
9.NumPy stores large arrays of pixel data efficiently.

How It Works

1.The script starts and shows the main menu.
2.You choose between Image or Video Steganography.
3.A new window opens for the chosen mode.
4.You load a file, type a secret key, and write a message.
5.Clicking “Hide Data” saves a new file with the message hidden inside.
6.Later, using “Show Data” and the correct key, you can reveal the hidden message.

Summary

This program is a complete desktop application for hiding and revealing messages in images and videos.
It embeds text into media files by changing tiny details in their pixels, making the changes invisible to the human eye.
The user interacts with a friendly interface built in Tkinter, while Pillow, Stegano, OpenCV, and NumPy handle the underlying processing.

It’s a good example of how different Python libraries can work together to create a functional, user-friendly tool.
