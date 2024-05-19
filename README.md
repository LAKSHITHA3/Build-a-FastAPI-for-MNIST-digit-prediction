# MNIST Digit Classifier API

This project implements a FastAPI application that allows users to upload images of handwritten digits (28x28 pixels) and returns the predicted digit using a pre-trained MNIST model. The API provides a `/predict` endpoint where users can upload an image, and it will respond with the recognized digit.

## Table of Contents
- [MNIST Digit Classifier API](#mnist-digit-classifier-api)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
    - [Running the Server](#running-the-server)
  - [Usage](#usage)
    - [Swagger UI](#swagger-ui)
    - [Using Postman](#using-postman)
  - [Testing](#testing)
  - [Project Structure](#project-structure)
  - [License](#license)

## Getting Started

### Prerequisites

Make sure you have the following installed on your system:
- Python 3.7+
- pip (Python package installer)

### Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/your-username/mnist-digit-classifier.git
    cd mnist-digit-classifier
    ```

2. Install the required Python packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Place your pre-trained MNIST model (`mnist_model.h5`) in the `model/` directory.

### Running the Server

To start the FastAPI server, run the following command, replacing `<path_to_model>` with the actual path to your trained MNIST model:

```bash
python main.py model/mnist_model.h5
```

This will start the server on `http://127.0.0.1:8000`.

## Usage

### Swagger UI

You can access the Swagger UI for testing the API by navigating to `http://127.0.0.1:8000/docs` in your web browser. Here, you can upload an image and see the prediction response from the API.

### Using Postman

You can also use Postman to test the API:

1. Open Postman and create a new POST request.
2. Set the URL to `http://127.0.0.1:8000/predict`.
3. In the Body tab, select `form-data`.
4. Add a new key named `file`, set the type to `File`, and choose an image file of a handwritten digit.
5. Send the request and view the response.

## Testing

Unit tests are included to ensure the robustness of the application. To run the tests, use the following command:

```bash
pytest test_main.py
```

## Project Structure

```
mnist-digit-classifier/
│
├── main.py               # FastAPI application
├── README.md             # Project documentation
├── requirements.txt      # Python dependencies
├── test_main.py          # Unit tests
└── model/
    └── mnist_model.h5    # Pre-trained MNIST model
```
