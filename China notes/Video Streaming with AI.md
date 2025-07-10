- Kaigui Bian

## Content Distribution

- Data Center --> Edge Server --> Device
- Distribution Streaming is between edge server and device

- Increasing resolution increases latency (because the weight of the video is increased that bandwitch may not catch up with)
- Decreasing resolution decreases the latency since the video weight is lower

- *Proactive Cache by AI*
	- CDN (content distribution network built on the modern network infrastructure)
	- ISP (internet service provider)

- How do ISPs charge video-service companies?
	- *Charge by overall throughput*
	- *In China, charge is by daily peak bandwidth consumption*
		- Thus companies want to lower the peak bandwidth usage to lower the costs for renting servers from ISP

- What is the solution for lowering peak bandwidth?
	- Predict content popularity in different regions (use neural networks)
	- Pre-cache popular content at edge at off-peak time

- Machine learning helps in predicting the content popularity
	- Contextual Features
	- Semantic Features
	- Use probability by analyzing features to pre-cache content to specific regions


## Content Transmission

## Content Recommendations