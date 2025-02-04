# Classifier API Server

This Flask app utilizes the Hugging Face Transformers library to classify text into multiple categories. It is intended to be run locally on your machine.

## Prerequisites

Before you can run the app, you need to have the following software installed on your machine:

- Python 3.6 or higher
- pip package manager

## Installation

1. Clone the repository to your local machine:

```
https://github.com/nz-m/SocialEcho.git
```

2. Navigate to the project directory:

```
cd SocialEcho/classifier_server
```

3. Install the required Python packages:

```
pip install -r requirements.txt
```

## Usage

To run the app, use the following command:

```
python classifier_api.py
```

This will start the Flask app on `http://localhost:5000`.

**Note:** Before running the app locally, please note that it requires downloading the model files, which have a size of approximately 1.6GB+. These files will be automatically downloaded when you run the app for the first time.

If you prefer not to download the model files and do not have Python and pip installed, you can use a Docker image to run the app. Follow the steps below:

Pull the Docker image:

```
docker pull neaz/classifier_api
```

Then run the image using:

```
docker run -p 5000:5000 neaz/classifier_api
```

This will start the app in a Docker container, and you can access it on `http://localhost:5000`.

The app has two endpoints:

- `/`: Returns a simple JSON response to indicate that the app is running.
- `/classify`: Accepts a JSON payload with a `text` field, and returns a JSON response with a list of categories and their scores.

To use the `/classify` endpoint, send a POST request to `http://localhost:5000/classify` with the following JSON payload:

```json
{
  "text" : "Python is a high-level programming language that is widely used for web development, scientific computing, data analysis, artificial intelligence, and more."
}
```

The app will return a JSON response with a list of categories and their scores, sorted by score in descending order:

```json
{
  "response": {
    "categories": [
      {
        "label": "Programming",
        "score": 0.8015680313110352
      },
      {
        "label": "Science and technology",
        "score": 0.05600866675376892
      },
      {
        "label": "Business and entrepreneurship",
        "score": 0.016151048243045807
      },
      ...
    ]
  }
}
```

---

## About the Maintainer

This project is currently maintained by **Sai Venkata Reddy Vanga**.

Sai is a Full Stack Developer with over 4 years of experience in architecting and delivering high-performance, scalable web applications. His expertise includes robust backend systems and modern front-end interfaces, with a strong focus on designing RESTful APIs, integrating third-party services, and optimizing application performance. He is also skilled in DevOps practices, including CI/CD pipelines and containerization.

For inquiries or collaborations, you can reach Sai via:
- **Email:** saivanga7781@gmail.com
- **LinkedIn:** Sai Venkata Reddy Vanga
- **GitHub:** Sai Venkata Reddy Vanga

---