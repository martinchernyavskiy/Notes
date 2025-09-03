## Types of systems
?
- ### Services (online)
	- Waits for request/ instruction from client
	- Attempts to handle as quickly as possible and sends response back
	- *Response time*
- ### Batch Processing Systems (offline)
	- Takes large amount of input data
	- Runs *job* to process the data and produces *output data*
	- Job may take from several minutes to several days
	- No client awaiting
	- *Job scheduling*
	- *Throughput*
- ### Stream Processing Systems (near-real-time)
	- Between online/offline processing
	- Takes input and produces output
	- Operates on events shortly after they happen, contrary to batch where job operates on a fixed set of input data
	- *Lower latency* compared to batch systems

## Batch Processing with Unix tools
?
- Ngix default access log format: `$remote_addr - $remote_user [$time_local] "$request" $status $body_bytes_sent "$http_referer" "$http_user_agent"

### Simple Log Analysis
- Given the log file with lines of default access log formats listed above, we will create a report using Unix tools to find 5 most popular pages on the website. We group Unix commands using a pipe operator (|):
```
cat /var/log/nginx/access.log |
awk '{print $7}' |
sort |
uniq -c |
sort -r -n |
head -n 5
```
Enumerated steps:
	1.  Read log file using cat command
	2. Split each line into fields by whitespace and output only the seventh such field from eadch l