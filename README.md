The challenge
---

Use [beanstalkd](http://kr.github.io/beanstalkd/), mongodb, nodejs

Get the xe.com exchange rate, store it in mongodb for every 1 min.


How it work?
---
1. Seed your job in beanstalkd, tube_name = your_github_username

2. Code a nodejs worker, get the job from beanstalkd, get the data from xe.com and save it to mongodb.
	a. If reqqust fail, reput to the tube and delay with 3s.
	b. If request is done, reput to the tube and delay with 60s.

3. Stop the task if you tried 10 times.

Tools you need
---
1. beanstalkd server is setup for you already, make a JSON request to this:

	/POST http://challenge.aftership.net:9578/v1/beanstalkd
	header: aftership-api-key: a6403a2b-af21-47c5-aab5-a2420d20bbec

2. Get a free mongodb server at [mongolab](https://mongolab.com/welcome/)

3. You should need [fivebeans](https://github.com/ceejbot/fivebeans) npm

4. You may also need [Beanstalk console](https://github.com/ptrofimov/beanstalk_console)

5. Our [cook book](https://github.com/AfterShip/coding-guideline-javascript)


Help?
---
am9ic0BhZnRlcnNoaXAuY29t
