FROM python
WORKDIR /project
ADD . /project
ENV MQTT_SERVER $MQTT_SERVER
RUN pip install -r requirements.txt
CMD ["python","app.py"]

# docker image build -t mu-iot .
# docker run -p 5001:5000 -d mu-iot