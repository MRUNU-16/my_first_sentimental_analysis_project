# Sentiment-Analysis-Keras-Flask
A simple web service to predict Sentiment using CNN.


A keras model is trained and saved once. When there is an API call to the web service the model is loaded the first time as a global variable and the sentiment of the text thats is passed in the POST request is predicted.


## API USAGE:

```
curl -i -H "Content-Type: application/json" -X POST -d '{"review":"This movies is good"}' http://localhost:5000/review
```


```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 33
Server: Werkzeug/0.11.15 Python/3.6.1
Date: Fri, 05 Jan 2018 23:38:14 GMT

{
  "sentiment   ": "positive"
}
```


```
curl -i -H "Content-Type: application/json" -X POST -d '{"review":"This movies is bad"}' http://localhost:5000/review
```


```
HTTP/1.0 200 OK
Content-Type: application/json
Content-Length: 33
Server: Werkzeug/0.11.15 Python/3.6.1
Date: Fri, 05 Jan 2018 23:38:53 GMT

{
  "sentiment   ": "negative"
}
```

### Improving the Model

This can be done by adding more examples and re-running the training process and saving it.



