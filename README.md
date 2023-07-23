# Face Recognition and Clustering

This project contains a Python Notebook that uses face recognition and machine learning techniques to cluster images based on the faces they contain. The script identifies the faces in each image, encodes them into vectors, and uses these vectors to group similar faces together.

## How It Works

1. **Face Recognition**: The script uses the `face_recognition` library, which is built on top of Dlib's state-of-the-art face recognition techniques. It identifies faces in an image and encodes them into a vector of 128 measurements.

2. **Face Encoding**: Each face in an image is transformed into a 128-dimensional vector (or encoding) that represents the facial features. This encoding is used to compare faces.

3. **Clustering**: The script uses DBSCAN (Density-Based Spatial Clustering of Applications with Noise), a density-based clustering algorithm from the `scikit-learn` library, to cluster the face encodings. DBSCAN groups together points that are close in the 128-dimensional space and have a minimum number of points in their neighborhood. The points that are far away from any cluster are treated as noise.

4. **Organizing Images**: Once the faces are clustered, the script organizes the original images based on the clustering results. For each cluster, it creates a separate folder and saves all the images containing faces from that cluster into the corresponding folder. Images with faces that couldn't be confidently assigned to a cluster are placed in a separate folder named 'doubtful but clustered'.

5. **Representative Face**: For each cluster, the script saves a representative face (the first face from the cluster) as a separate image in the cluster's folder.

## Installation

To run this script, you need Python 3.7 or later.

1. Clone this repository to your local machine.
2. Install the necessary Python packages using pip: pip install -r requirements.txt

## Usage

1. Collect the images you want to cluster in a folder. These can be .jpg, .png, or .jpeg files.
2. Update the `image_folder` variable in the script to the path of a folder that contains images you wish to cluster.
3. Run all the cells in the notebook.
4. The script will create an 'output' folder in the same directory. Inside this folder, you will find separate folders for each cluster of images, named 'cluster_0', 'cluster_1', etc. Images with faces that couldn't be confidently assigned to a cluster will be in the 'doubtful (possibly clustered)' folder.

## Notes

This script works best with clear, front-facing images of faces. Images with side views, occlusions, or low quality may not be clustered accurately. The chosen similarity threshold for face clustering is 0.68 (1 - 0.32), where 0.32 is a common threshold in face recognition tasks that states two faces are from the same person if their distance is less than 0.32.

## Contribution

Contributions to improve this script are welcome. Please feel free to fork the repository, make changes, and create a pull request.
