# ActiveState Tensorflow Demo

In this tutorial, we will explore using an ActiveState Python runtime to help us explore some data in Jupyter Notebook with Panadas and Matplotlib. We will also learn how to operationalize a TensorFlow model with Flask.

## Prerequisites

1. Ensure you have Docker installed on your machine and running.
2. Pull the docker image to your machine with ```docker pull ecole5/tensorflow-ml-demo:latest```
2. Make an ActiveState account (www.platform.activestate.com)

# Tutorial 
## 1. Create a new ActiveState project

1. Navigate to www.platform.activestate.com and log in to your account
2. Create a new project with Python 3.10.10 and name it Demo
3. Navigate to the requirements.txt file in this git repository and copy the contents into your clipboard
4. Go back to your project and add the requirements to your new project using the import from file button
5. Go to your project setting, and under the Git Repo field, copy and paste the URL of this repo https://github.com/ActiveState/tensorflow_ml_demo to link your ActiveState runtime

## 2. Start your container

Using the image you downloaded earlier, spin up a docker container using the following command:

``` docker run -it -p 8888:8888 -p 8000:8000 ecole5/tensorflow-ml-demo:latest```

You will complete the rest of the tutorial in this container.

## 3. Checkout your runtime

In the container, the ActiveState State Tool will already be installed. Checkout the ActiveState runtime you creating using the following command. Replace ORG with the name of your ActiveState organization. 

```state checkout ORG/Demo```

You will notice that the packages you configured on the ActiveState platform will begin to download in addition to the code in this repository.

When you first download a runtime, it will take a while. Updates are fast becasue the files are cached. Escape this process and navigate into 

```cd tensorflow-ml-demo```

Here an ActiveState runtime, and our project files have already been checked out. Notice that the activestate.yaml point to this project https://platform.activestate.com/ActiveStateSE/tensorflow-ml-demo.

## 4. Check for updates
Inside the tensorflow-ml-demo directory, run the ```state pull``` command.

## 5. Explore the data using jupyter notebook.
1. Go to the data_explore directory ```cd data_explore```.
2. Create a virtual environment using ```state shell```.
3. Start the jupyter notebook using ```jupyter notebook --ip 0.0.0.0 --no-browser --allow-root```.
4. Copy the address of the jupyter server with the token that Jupyter provides. For example http://127.0.0.1:8888/?token=449902b48ae7b665b9f682d2c4185a9e169f26a4f3c6169d. Navigate to it using a local browser. 

## 5. Run the tensorflask service
1. Move to the tensorflask directory ```cd ../tensorflask```
2. Start the tensorflask app with ```state exec python3 app.py```
3. Download a picture of the poodle from the tensorflask folder to your local machine
4. On your local machine open up a new terminal and run ```curl http://localhost:8000?file=/poodle.jpeg``` where the file path is the location where you saved the poodle

# License & Acknowledgements

Licensed under the Apache 2.0 license. See the LICENSE file for details.
Based on work from [this project](https://github.com/ActiveState/tensorflask) 
and here
https://www.kaggle.com/code/valchovalev/pets-ownership-cats-vs-dog-popularity-in-usa
