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
<!--SR:!2025-10-20,28,270-->

## Batch Processing with Unix tools
?
- Ngix default access log format: `$remote_addr - $remote_user [$time_local] "$request" $status $body_bytes_sent "$http_referer" "$http_user_agent"
<!--SR:!2025-11-02,37,294-->

### Simple Log Analysis
?
- Given the log file with lines of default access log formats listed above, we will create a report using Unix tools to find 5 most popular pages on the website. We group Unix commands using a pipe operator (|):
```Unix
cat /var/log/nginx/access.log |
awk '{print $7}' |
sort |
uniq -c |
sort -r -n |
head -n 5
```
Enumerated steps:
	1.  Read log file using cat command
	2. Split each line into fields by whitespace and output only the seventh such field from each line, which is the requested URL
	3. Alphabetically sort the listed requested URLs
	4. Filters out repeated lines and -c parameter tells to output a counter of how many times the listed distinct URLs appeared in the input
	5. Sort by number (-n), number of times URL was requested, -r reverses the order, so it's largest to smallest
	6. Outputs first 5 of input and discards the rest
Note: Unix tools are powerful and we can manipulate the commands to serve a specific analysis purpose.
<!--SR:!2025-10-17,25,274-->

### Chain of Commands vs. Custom Programs
?
- Simple programs can achieve the same thing as Unix commands, for example:
```Ruby
counts = Hash.new(0)
File.open('/var/log/nginx/access.log') do |file|
 file.each do |line|
 url = line.split[6]
 counts[url] += 1
 end
end
top5 = counts.map{|url, count| [count, url] }.sort.reverse[0...5]
top5.each{|count, url| puts "#{count} #{url}" }
```
Enumerated steps:
	1. initialize counts to a hash table that keeps a counter of # of each URL, set it to zero by default
	2. Open file and from each line of log, split line into fields and access URL the 7th field by 6th index
	3. Increment counter for the URL in the current line of log, repeat until the end of log file
	4. Sort the hash table contents by descending counter values and obtain top 5 entries
	5. Print the top five entries
<!--SR:!2025-11-07,42,294-->

### Sorting vs. In-memory aggregation
?
- Ruby keeps in-memory hash table of URLs, whilst the Unix pipeline doesn't
- *Working set of the job* (the amount of memory to which job needs random access) depends only on the number of distinct URLs.
- If number of distinct URLs is small eough, using in-memory hashtable works fine, however if there is a bigger website with a lot of distinct URLs, this depletes memory
	- Instead, using sorting approach via Unix pipeline can take advantage of efficient use of disks
...
<!--SR:!2025-11-11,46,294-->

### Unix Philosophy
?
- Analogy of building a pipeline where each program is connected to each other
1. Have a program do a particular task and only that task
	 a) To do new job, build new program
2. Expect output of each program to become input of the other, one which isn't cluttered with meaningless information for easier use.
3. Design & Build software early to be tried early.
4. Use tools to lighted a programming tasks even if you may end up throwing them away after finishing using them.
<!--SR:!2025-09-29,15,290-->

### Uniform Interface
- Transferring input/output values between the programs requires for these to be the same data format --> same input/output interface
- Interface in Unix is a file descriptor, consisting of ordered sequences of bytes which is used by many things to be represented and thus able to be plugged together
- Many Unix programs treat files as ASCII text
- 


### Separation of Logic and Wiring
?
- Uses standard input/output (stdin/stdout). Default keyboard/screen. *Can specify input/output to be files*
- Pipes allow to connect stdout of one process to stdin of another process. Uses in-memory buffer, but no intermediate data stream to disk
- Custom programs can take part of this pipeline by using stdin/stdout directly
<!--SR:!2025-09-29,15,294-->

### Transparency and Experimentation
?
- Input files are viewed as immutable
- Can end pipeline whenever you wish, good for debugging
- Can save output of pipeline to a file and use that file as an input to the next stage.
- Ran only on a single machine, *Hadoop* solves that
<!--SR:!2025-09-30,16,290-->