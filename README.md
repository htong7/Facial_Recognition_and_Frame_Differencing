# Face Detection in Video

This project is about detecting faces in a video using the `face_recognition` and `opencv-python` libraries. The script processes the video frame by frame and checks for faces in each frame.

## Dependencies

- Python 3.6 or above
- face_recognition
- opencv-python

You can install the necessary libraries using pip:

```bash
pip install face_recognition opencv-python

Usage
The main function in the script is detect_faces_in_video(video_path), where video_path is the path to the video file you want to process.

The function reads the video file frame by frame. It checks for faces in each frame using the face_recognition.face_locations function with the “cnn” model. The results are stored in a list, where 1 indicates that a face was detected in the frame, and 0 indicates that no face was detected.

The function also calculates and prints the processing time.

Here’s an example of how to use it:

results = detect_faces_in_video("path_to_your_video.mp4")

Output
The function returns a list of integers representing the detection results for each second of the video. It also prints the detection results and the processing time.

Note
This script uses the CNN model for face detection, which is computationally intensive. If you’re running this on a machine with limited resources, consider using the “hog” model instead.

Please replace `"path_to_your_video.mp4"` with the actual path to your video file.
