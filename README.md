# Jmeter-api-automation-framework

1. Load Test Summary

Total Samples: 50
Test Duration: ~9 seconds
Throughput: ~5.4 requests/sec
Average Response Time: ~115 ms
Min Response Time: 32 ms
Max Response Time: 3359 ms
Error Rate: 0%

Observations:
System performed stably under normal load conditions
Response time mostly stayed under 200 ms
No failures observed (0% error rate)
Occasional spike (3359 ms) indicates minor latency under peak moment

2. Stress Test Summary

Total Samples: 1000
Test Duration: ~16 seconds
Throughput: ~62.1 requests/sec
Average Response Time: ~72 ms
Min Response Time: 25 ms
Max Response Time: 5726 ms
Error Rate: 0.1% (1 failed request)

 Observations:
System handled high load efficiently up to ~62 req/sec
Average response time remained stable (~70 ms) even under stress
One failure observed (0.1%), indicating minor instability under peak load
Max response time spike (5726 ms) suggests occasional bottleneck / server delay

 3. Overall Performance Insights

System is highly stable under load
Under stress, rare failures occur
Throughput is strong and consistent (~60+ req/sec)
Response time remains within acceptable range for most requests

Below is my Framework Architecture as per Assignment Requirement

jmeter-api-automation-framework/
│
├── jmeter/
│   ├── testplans/
│   │   ├── JsonPlaceholder_LoadTest.jmx
│   │   ├── JSONPlaceholder_StressTest.jmx
│   │
│   ├── reports/
│   │   ├── baseline-test-report/
│   │   │   └── (HTML report files)
│   │   │
│   │   ├── stress-test-report/
│   │   │   └── (HTML report files)
│   │
│   ├── results/
│       ├── baseline-results.jtl
│       ├── stress-results.jtl
│    
├── README.md
└── LICENSE

How to Run JMeter Tests

# Load Test
jmeter -n -t jmeter/testplans/JsonPlaceholder_LoadTest.jmx -l jmeter/results/baseline-result.jtl -e -o jmeter/reports/baseline-test-report

# Stress Test
jmeter -n -t jmeter/testplans/JSONPlaceholder_StressTest.jmx -l jmeter/results/stress-result.jtl -e -o jmeter/reports/stress-test-report


