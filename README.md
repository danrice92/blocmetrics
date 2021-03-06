## Blocmetrics

![](app/assets/images/blocmetrics-chart.jpg)

Blocmetrics is my third Rails project for my Software Engineering Track at [Bloc](http://bloc.io). It is an analytics service to track events on websites.

Blocmetrics now allows users to create an account, verify their email, and add web apps to track. Once the app is added and the Blocmetrics API is implemented in their app, users can view a pie chart and line graph of usage throughout their app.

This is the JavaScript snippet developers can put in their app to track events. In Rails, a good place to put it is app/assets/javascripts/application.js:

	var blocmetrics = {};
	blocmetrics.report = function(eventName){
    	var event = {event: { name: eventName }};
	    var request = new XMLHttpRequest();
	    request.open("POST", "http://localhost:3000/api/events", true);
	    request.setRequestHeader('Content-Type', 'application/json');
	    request.send(JSON.stringify(event));
	};

You can check out more about Blocmetrics, the rest of my portfolio, my blog, and my experience at Bloc at my [website](http://danrice.me). Blocmetrics itself is live through [Heroku](http://dan-rice-blocmetrics.herokuapp.com).

Made with my mentor at [Bloc](http://bloc.io).