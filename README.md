import cv2
import numpy as np

# Define the phrases to be displayed
phrases = ["Welcome", "To the World Of Dreamers", "Let's Dream together"]

# Define video parameters
fps = 30  # Frames per second
duration_per_phrase = 3  # Duration for each phrase in seconds
frame_size = (640, 480)  # Frame size (width, height)
background_color = (0, 0, 0)  # Black background color
font_path = 'path_to_arial_bold.ttf'  # Replace with the actual path

# Create a VideoWriter object to save the video
fourcc = cv2.VideoWriter_fourcc(*'XVID')
out = cv2.VideoWriter('enhanced_text_to_video.avi', fourcc, fps, frame_size)

# Function to add text animation (e.g., fade-in)
def add_text_animation(frame, text, position, font, font_scale, font_thickness, font_color, animation_type='fade_in'):
    if animation_type == 'fade_in':
        for i in range(0, 255, 5):
            frame_copy = frame.copy()
            cv2.putText(frame_copy, text, position, font, font_scale, (i, i, i), font_thickness, lineType=cv2.LINE_AA)
            cv2.imshow('Text to Video', frame_copy)
            out.write(frame_copy)
            cv2.waitKey(50)
    else:
        cv2.putText(frame, text, position, font, font_scale, font_color, font_thickness, lineType=cv2.LINE_AA)
        out.write(frame)
        cv2.imshow('Text to Video', frame)
        cv2.waitKey(1000 // fps)

# Start creating the video
for phrase in phrases:
    for t in range(fps * duration_per_phrase):
       # Create a frame with a customizable background color
        frame = np.full((frame_size[1], frame_size[0], 3), background_color, dtype=np.uint8)

        # Calculate the position of the text dynamically (centered)
        text_position = (int(frame_size[0] / 4), int(frame_size[1] / 2))

        # Load the font and set parameters
        font = cv2.FONT_HERSHEY_SIMPLEX
        font_scale = 1
        font_thickness = 2
        font_color = (255, 255, 255)  # White

        # Add text with animation (fade-in effect)
        add_text_animation(frame, phrase, text_position, font, font_scale, font_thickness, font_color, animation_type='fade_in')

# Release the VideoWriter and close the display window
out.release()
cv2.destroyAllWindows()

# Display a message when the video is created
print("Enhanced video created successfully!")
