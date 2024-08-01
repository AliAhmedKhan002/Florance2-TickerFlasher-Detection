# florence2-training-api
Training api for tricker, flasher and scene detection using Florence 2


This repository contains a FastAPI application for running an object detection model using the Florence 2 model from Hugging Face. The application processes image inputs and returns detected objects with bounding boxes and in case of scene detection it return the detected Scene in an image.
Table of Contents

    Installation
    Usage
    API Endpoints
    Dataset Format
    Fine-tuning
    Acknowledgments

Installation

    Clone the repository:

    bash

git clone https://github.com/your-username/florence2-object-detection.git
cd florence2-object-detection

Create and activate a virtual environment (optional but recommended):

bash

python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

Install the required dependencies:

bash

    pip install -r requirements.txt

Usage

For Scene Detection 

Navigate to Florance-SceneDetection folder and run the command python florance.py 


For Ticker/Flasher

Naviaget to Florance_TickerFlasher_File and run the command python florance.py

The application will be accessible at http://192.168.18.164:8007/docs.
API Endpoints
POST /process-image/

Processes an uploaded image and returns detected objects with bounding boxes.

Request:

    file: Image file to be processed (form-data).

Response:

json

{
  "results": {
    "labels": [
      "label1",
      ...
    ]
  }
}

Dataset Format

The dataset annotations should be in JSONL format, with each line representing an annotation for one image. The format is as follows:

json

{
    "image": "path/to/image.jpg",
    "prefix": "prefix text",
    "postfix": "postfix text",
    "bboxes": [
        [x1, y1, x2, y2],
        ...
    ],
    "labels": [
        "label1",
        ...
    ]
}

Fine-tuning

To fine-tune the Florence 2 model on a custom detection dataset, follow the steps outlined in the Jupyter notebook provided in this repository.

    Open the notebook how_to_finetune_florence_2_on_detection_dataset.ipynb in Jupyter Notebook or Jupyter Lab.
    Follow the instructions to prepare your dataset and fine-tune the model.

Acknowledgments

This project uses the following open-source libraries and models:

    FastAPI
    Hugging Face Transformers
    PyTorch
    Matplotlib
