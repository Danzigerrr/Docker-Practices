FROM python:3.9

# expose default Flask port
EXPOSE 5000

# create and cd into app directory
WORKDIR /app

# install requirements
COPY requirements.txt /app
RUN pip install -r requirements.txt

# run the Flask app
COPY app.py /app
CMD python app.py