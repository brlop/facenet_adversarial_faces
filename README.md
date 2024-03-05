*NOTE: This repository is just a copy of a contribution I made to the Cleverhans library: github.com/cleverhans-lab/cleverhans/tree/b54f65921a013aa57eb55f8ff6fd3a58018dbb0f/examples/facenet_adversarial_faces*

# FGSM against Facenet
This directory contains an implementation of the FGSM attack against one of the face recognition CNNs of the Facenet library.

## How to run

In order to run this example you need to do the following:

1. Install the Facenet library, download and align the LFW faces and download a pretrained Facenet model. You can do that following the next Facenet tutorial: https://github.com/davidsandberg/facenet/wiki/Validate-on-LFW
(Running the validate_on_lfw script is not necessary). The datasets and the models folders must be in the folder of this example.

2. Install Pillow: https://pillow.readthedocs.io/en/stable/

3. Change the following line in the facenet_fgsm.py script with the name of the .pb file of the model you downloaded:
    ```
    model_path = "models/facenet/20180402-114759/20180402-114759.pb"
    ```

4. Run the script:
    ```
    python facenet_fgsm.py
    ```
	
5. The Facenet models dimensions are sometimes changed by its developer, so if the script gives you an error regarding the dimensions of the input shapes, you must change this line to use the proper number:
    ```
	self.victim_embedding_input = tf.placeholder(
        tf.float32,
        shape=(None, 512))
	```
