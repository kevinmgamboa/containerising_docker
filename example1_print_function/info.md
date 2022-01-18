## Print Function in a Container

In this example, I created a container that runs a function that prints some text. To achieve this basically we need two things:

1. A python script that contains the code that print the text.
2. A Docker file from which the image is created.

The creation of a Python file that prints some text is pretty straight forward. First, I created a Python file that just prints some predetermine text (in another example we will introduce the text to be print when running the container). After this, we can create the Docker file that takes this Python file and makes an image from it. This can be done as follows:

```commandline
# Defining Docker Image
FROM python:3.8
# Defining present working directory
WORKDIR /heart_disease_prediction_app
# Copy repo content into working dir
ADD . /heart_disease_prediction_app
# Installing dependencies (requirements.txt)
RUN pip install -r app_requirements.txt
# Define commands when starting container
CMD ["python", "app.py"]
```
After this Docker file is created, we will have to build the image by typing the commands `docker build -t image_name .`. The `-t` specify the "tag" or name for the image. Then we can type the magic words `docker run --rm image_name` where the `--rm` means that we remove the container after running it.