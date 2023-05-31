# tensorflask

This is a simple example of hosting a TensorFlow model as Flask service for inference. It provides the "Poodle, Pug or Weiner Dog?" image identification service using a retrained MobileNet model. The retrained model/labels are provided here to let you run the service locally.

This is forked from [this project](https://github.com/ActiveState/tensorflask)

## data set

- https://knowyourdata-tfds.withgoogle.com/#tab=STATS&dataset=pet_finder
- https://github.com/tensorflow/models/tree/master/official




## Usage
Run `python app.py` to start the service

Once you've started the service, you can query it on `localhost:8000`. You can either hit it via a web browser, or use `curl` from the commandline. It takes a single parameter `file` which specifies the full path to a local image, so for example:

`curl http://localhost:8000?file=/mypoodle.jpeg`

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
