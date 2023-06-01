# ActiveState Tensorflow Demo

In this tutorial, we will explore using an ActiveState Python runtime to help us explore some data in Jupyter Notebook with Panadas and Matplotlib. We will also learn how to operationalize a TensorFlow model with Flask.

## Prerequisites

1. Ensure you have Docker installed on your machine and running.
2. Pull the docker image to your machine with ```docker pull ecole5/tensorflow-ml-demo:latest```
2. Make an ActiveState account (www.platform.activestate.com)

# Tutorial 
## 1. Create a new ActiveState project

Navigate to www.platform.activestate.com and log in to your account.

Create a new project with Python 3.10.10 and name it demo.

Take a look at the git repository. https://github.com/ActiveState/tensorflow_ml_demo and open the requirements.txt file. Copy the contents into your clipboard.

Go back to your project and add the requirements to your new project using the import from file button.

Go to your project setting, and under the Git Repo field, copy and paste the URL of the repo https://github.com/ActiveState/tensorflow_ml_demo to link your runtime environment to the git repo containing the code.

## 2. Start your container

Using the image you downloaded earlier, spin up a docker container using the following command

``` docker run ecole5/tensorflow-ml-demo:latest -it -p 5000:5000 -p 8000:8000 ```

Complete the rest of the tutorial in this container.

## 3. Checkout your runtime

In the container, the ActiveState state tool will already be installed. Checkout the ActiveState runtime using

```state checkout ORG/Demo```

You will notice that the packages you configured on the ActiveState platform will begin to download in addition to the code in the GitHub repository.

When you first download a runtime, it will take a while. All files are cached, so future updates are quick. Escape this process and navigate into 

```cd tensorflow-ml-demo```

Here an activeState runtime, and our project files have already been checked out. They were shipped in the container image.

## 4. Update your runtime.
Inside the tensorflow-ml-demo directory, run the ```state pull``` command.

## 5. Explore the data using jupyter notebook.
1. Go to the data_explore directory ```cd data_explore```.
2. Create a virtual environment  using ```state shell```.
3. Start the jupyter notebook using ```cd jupyter notebook --ip 0.0.0.0 --port 5000 --no-browser --allow-root```.
4. In yor browser navigate to localhost:5000.

## 5. Run the tensorflask service
1. Move to the tensorflask directory ```cd ../tensorflask```.
2. Start the tensorflask app with ```state exec python3 app.py```.
3. On your local machine open up a new terminal and run ```curl http://localhost:8000?file=/mypoodle.jpeg```
The path is a path to a picture of a dog or cat. We have included a picture of a poodle you can download from the tensorflask folder from the repo on GitHub. 

# License & Acknowledgements

Licensed under the Apache 2.0 license. See the LICENSE file for details.
Based on work from [this project](https://github.com/ActiveState/tensorflask) 
and here
https://www.kaggle.com/code/valchovalev/pets-ownership-cats-vs-dog-popularity-in-usa