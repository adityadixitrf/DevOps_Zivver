# DevOps_Zivver

Following are the steps to set up a microservice application on AWS using EKS (Elastic Kubernetes Service), Docker, GitLab CI/CD, and GitOps approach:

1. Microservice Framework/Language: Flask (Python). I will create a simple REST API that returns a version number.

2. **Python Application**
   **app.py**

    from flask import Flask
    
    app = Flask(__name__)
    
    @app.route('/')
    def version():
        return '3.0.1'
    
    if __name__ == '__main__':
        app.run(debug=True, host='0.0.0.0')

4. **Docker file**

     From python:3.8-slim

     WORKDIR /app

     COPY requirement.txt .

     RUN pip install --no-cache-dir -r requirements.txt

     COPY ..

     CMD ["python", "app.py"]
  
    

