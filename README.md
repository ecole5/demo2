# tensorflask

This is a simple example of hosting a TensorFlow model as Flask service for inference. It provides the "Poodle, Pug or Weiner Dog?" image identification service using a retrained MobileNet model. The retrained model/labels are provided here to let you run the service locally.

This is forked from [this project](https://github.com/ActiveState/tensorflask)

## data set

- https://knowyourdata-tfds.withgoogle.com/#tab=STATS&dataset=pet_finder
- https://github.com/tensorflow/models/tree/master/official

## Setup

1. Install docker
2. Downloaded the training data set
3. Get your requirements. You need a Python, Flask and TensorFlow installed. You can [download ActiveState runtime - https://platform.activestate.com/DemoOrg/tensorflow-ml-demo-3.10.11/releases](https://platform.activestate.com/DemoOrg/tensorflow-ml-demo-3.10.11/releases) which has all the required dependencies already pre-installed. This will install the ActiveState CLI tool.
4. Clone to repository by clicking the clone button above. 
5. Run `python app.py`.

## Usage
Once you've started the service, you can query it on `localhost:8000`. You can either hit it via a web browser, or use `curl` from the commandline. It takes a single parameter `file` which specifies the full path to a local image, so for example:

`curl http://localhost:8000?file=/home/pete/mypoodle.jpg`

Will send the photo to the service, which will run the model and return JSON identifying the probabilties of each type of dog breed. In this case you'll get results like:

```json
[
  [
    "poodle", 
    "pug", 
    "dachshund"
  ], 
  [
    0.9994891881942749, 
    1.1696176443365403e-05, 
    0.0004991634050384164
  ]
]
```

And you can see that the model is 99% sure that the image is a poodle.

## License

Licensed under the Apache 2.0 license. See LICENSE file for details.
