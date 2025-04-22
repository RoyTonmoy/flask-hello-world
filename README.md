# Simple Flask Hello World App

This is a minimal Flask web application that displays "Hello, World!" on the root endpoint (`/`). The project includes a Dockerfile to containerize the app, and instructions to build, push to Docker Hub, and run the app.

## Project Structure
- `app.py`: The Flask application code.
- `Dockerfile`: Instructions to build the Docker image.

## Prerequisites
- Python 3.9+ (if running locally without Docker)
- Docker (for containerization)
- Docker Hub account (to push the image)

## Setup and Run Locally (Without Docker)

1. Clone the repository:
```bash
git clone <repository-url>
cd <repository-directory>
```
2. Install Flask:
```bash
pip install flask
```
3. Run the app:
```bash
python app.py
```
4. Open your browser and go to `http://localhost:5000`. You should see "Hello, World!".

## Using Docker
### Build the Docker Image
1. Build the image:
```bash
docker build -t flask-hello-world:latest .
```
### Run the App
1. Run the container:
```bash
docker run -p 5000:5000 flask-hello-world:latest
```
2. Open `http://localhost:5000` in your browser to see "Hello, World!".
### Push to Docker Hub

1. Log in to Docker Hub:
```bash
docker login
```
2. Tag the image (replace yourusername with your Docker Hub username):
```bash
docker tag flask-hello-world:latest yourusername/flask-hello-world:latest
```
3. Push the image:
```bash
docker push yourusername/flask-hello-world:latest
```
### Pull and Run from Docker Hub
1. Pull the image:
```bash
docker pull yourusername/flask-hello-world:latest
```
2. Run the container:
```bash
docker run -p 5000:5000 yourusername/flask-hello-world:latest
```
## Notes
If port 5000 is in use, map a different port, e.g., docker run -p 8080:5000 ... and access at `http://localhost:8080`.

## License
This project is licensed under the MIT License.
