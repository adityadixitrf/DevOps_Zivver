# DevOps_Zivver

Following are the steps to set up a microservice application on AWS using EKS (Elastic Kubernetes Service), Docker, GitLab CI/CD, and GitOps approach:

1. Microservice Framework/Language: Flask (Python). I will create a simple REST API that returns a version number.

2. **Python Application**

from flask import Flask

app = Flask(__name__)

@app.route('/')
def version():
    return '3.0.1'

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')

3. **Docker file**

