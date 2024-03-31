
broadcast content to millions of people.

1. **Define the requirements from the user perspective**, list down all the requirements and choose the most important features first. For live streaming app, user should watch the content live whether it can be in HD or 480p that can be the secondary thing, make sure server doesn't go down
2. Reduce features into data definations


![[p1.canvas]]

3. Engineering requirements
	1. None of our service should fail in case of an outage
	2. Extensibility - How easy to change this solution, Build a system that can scale and extend as and when requirement change
	3. Design testing - Run through couple of requests with common case and edge case and see whether this cases having a sensible flow in the system. Do load test and capacity estimation for feasibility.


---
## Product Requirement

1. Streaming video
2. Processing video
3. Broadcasting (sending video to multiple customers)
4. Failproof 
5. Showing advertisement
6. Allowing reactions (Like/Dislike)
7. Showing disclaimers / news flashes
8. Having graceful degradation of video quality (in case of low bandwidth)
9. Allowing multiple device support

---
MVP