# ActiveState Tensorflow Demo

In this tutorial we will explore how to build ActiveState Python runtime to help us explore some data in Jupyter notebooks with panadas and matplotlib and  how to operatnalize a TensorFlow model with Flask


## Prerequists

1. Ensure you have Docker installed on your machine and running. 
2. Make an ActiveState account (www.platform.activestate.com)

# Tutorial 
## 1. Download the docker image ahead of time

To ensure everyone can follow along with this tutorail we are going to complete this tutorial inside a docker container instead of on bare metal. Open up your command line and type

```docker pull ecole5/tensorflow-ml-demo:latest```


## 2. Create a new ActiveState project

Navigate to platform.activestate.com and login to your account.

Create a new project with Python 3.10.10 and name it demo.

Take a look at the git repository. https://github.com/ActiveState/tensorflow_ml_demo and open the requirments.txt file. Copy the contents into your clipboard.

Go back to your project and add the requirments to your new project using the import from file button.

Go to your project setting and under the Git Repo field copy and paste the URL of the repo https://github.com/ActiveState/tensorflow_ml_demo to link your runtime envrionemnt to the git repo containing the code.

## 3. Start your container

Using the image you downloaded earlier spin up a docker container using the following command

``` docker run ecole5/tensorflow-ml-demo:latest -it -p 5000:5000 -p 8000:8000 ```

Complete the rest of the tutorial in this container.

## 4. Checkout your runtime

In the container the ActiveState state tool will already be installed. Checkout the ActiveState runtime using

```state checkout ORG/Demo```

You will notice the packages you configured on the ActiveState platform will begin to download in addtion to the code in the GitHub repository.

When you first download a runtime it will take awhile. All files are chached so future updates are quick. Escape this process and navigate into 

```cd tensorflow-ml-demo```

Here an activeState runtime and our project files have already been checked out. They were shipped in the container image.

## 5. Update your runtime.
Inside the tensorflow-ml-demo directory run the state pull command.

## 6. Explore the data using jupyter notebook.
```cd data_explore```
```state shell```
```cd jupyter notebook --ip 0.0.0.0 --port 5000 --no-browser --allow-root```
On your local browser navigate to localhost:5000

## 7. Run the tensorflask service
```cd ../tensorflask```
```state exec python3 app.py```
On your local machine open up a new terminal and run 

```curl http://localhost:8000?file=/mypoodle.jpeg```
Where the path is a path to a picture of a dog or cat. We have inlcuded a picture of a poodle you can download from the tensorflask folder from the repo on GitHub. 

#License & Acknowledgements

Licensed under the Apache 2.0 license. See LICENSE file for details.
Bbased on work from [this project](https://github.com/ActiveState/tensorflask) 
and here
https://www.kaggle.com/code/valchovalev/pets-ownership-cats-vs-dog-popularity-in-usa
