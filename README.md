# SNOW-Performance

Performance issues can arise with your ServiceNow instance in the network Latency, Application Server response, and Browser Rendering.
![image](https://user-images.githubusercontent.com/12488769/148380719-4f786a76-ad83-404d-bc4e-f10d6a5fa322.png)

One of the first things to consider when troubleshooting performance issues is to determine where the issues originated. This can be accomplished by performing basic troubleshooting steps, such as testing the issues on different computers or using different browsers. 
![image](https://user-images.githubusercontent.com/12488769/148380741-96305fb4-d0fb-46f8-aa2d-815454212afb.png)

### Network Performance
One clear indicator of a network issue is if users in one location have very good performance while users in another location have very poor performance. This indicates that the application server is fine. If the browser settings are identical for these users, the only meaningful difference is the network.

Monitor Ping Times
	The coarsest measure of network response time is a ping, which measures the total 	time for a packet to travel from the source machine to the target and back again. 	Ideally, the response time should be under 100ms in the United States or under 	150 ms in Europe or Asia. In practice, though, anything under 250 ms is not a major 	component in perceived response time. 

Running a Traceroute
If you are observing slow ping times, you can run a traceroute. Traceroutes are great tools for identifying network bottlenecks. 

To run a traceroute in Windows, open a command prompt window and enter: 
tracert <yourinstancename>.service-now.com

  ## Application Server
  Application server performance issues generally manifest themselves in slow response times. Monitoring response times and checking logs can help when identifying performance problems.

Monitor Response Times
	To maintain good performance levels on the application server, regularly monitor 	response times throughout your instance, including at the transaction level and on 	forms. 
Track System Transaction Logs
As you operate ServiceNow, the instance automatically logs the vital statistics of every transaction it processes. That information is available to users with the admin role.
Navigate to System Logs > Transactions.
	
Fixing the issue:
Ensure that a cache flush is not being run during business hours. Be aware, however, that when update sets are committed, they automatically trigger cache flushes, which prevent older data from interfering with changes and updates. So do not schedule update sets to be committed during business hours
If there is no identifiable cause, but overall response time is still slow, contact ServiceNow Technical Support to find out if anything is affecting the application server hardware.

### Browser
  Browser performance issues are often related to how the browser handles and renders compressed data. Monitoring how the browser handles caching of data from secured sites can also affect performance.


Compressing Data
	Make sure that your browser always requests for compressed data. Frequently, a 	proxy or edge device disables gzip compression. Enabling gzip compression would 	speed up the interactions.


Caching items from Secure Websites
If your organization has a policy to never cache items from an https location, every interaction with the ServiceNow server will fetch a large amount of JavaScript and images. 
To prevent this performance impact, make sure the Internet Explorer Do not save encrypted pages to disk option is off (the Microsoft default). 




