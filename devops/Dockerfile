FROM nhatthai/devops_deeplearning:latest
RUN apt-get update
RUN apt-get -y install cmake
COPY requirements ./requirements
RUN pip install -r requirements/requirement.txt