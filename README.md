
# Text-to-Video Converter

This project is a simple Python application that converts a series of text phrases into a video, with customizable text animations, background color, and more. The video is generated frame by frame, with each phrase displayed for a specified duration. This can be useful for creating dynamic text-based videos, intros, and other visual content.

## Features

- **Customizable Text**: Easily set the phrases to be displayed in the video.
- **Dynamic Text Animations**: Includes fade-in effects for smooth transitions.
- **Customizable Background**: Choose a background color for each frame.
- **Adjustable Frame Rate**: Configure the frames per second (FPS) for video smoothness.
- **Configurable Duration**: Set the duration for each text phrase in the video.
- **Font Options**: Select your preferred font style and size.
- **Text Positioning**: Customize the text's position on the screen.
  
## Requirements

- Python 3.x
- OpenCV (`cv2`)
- NumPy
- TTF font file (e.g., Arial Bold)

To install the required libraries, run:

```bash
pip install opencv-python numpy
```

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yassin549/text-to-video.git
cd text-to-video
```

2. Ensure you have a valid `.ttf` font file for displaying text (e.g., Arial Bold).
3. Modify the path to your `.ttf` font file in the code (in the `font_path` variable).
4. Run the Python script to generate the video:

```bash
python text_to_video.py
```

## Customization

- **Text Phrases**: Modify the `phrases` list to add the text you want to display.
- **Frame Duration**: Adjust `duration_per_phrase` to change how long each phrase appears.
- **Background Color**: Update the `frame` array to change the background color for each frame.
- **Text Position**: Change the `text_position` variable to position text anywhere on the frame.

## Usage

Once the script is run, the video will be saved as `text_to_video.avi` in the same directory. Each phrase will appear one after another with smooth fade-in animations. The video will be displayed frame by frame in a window, and the script will finish after displaying all the phrases.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact
For any kind of issue related to project, feel free to reach out at officialyassinkhoualid@gmail.com

