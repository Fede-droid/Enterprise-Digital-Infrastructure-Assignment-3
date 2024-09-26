# Enterprise-Digital-Infrastructure-Assignment-3
Publication of my personal assignment 3

# Web Technologies Performance and Benchmarking Report

## Author:
- Federico Cignoli

## Date:
- July 9, 2024

## Abstract
This report covers four main topics related to web technologies:
1. **Parallel Connections**
2. **Cache Mechanism**
3. **Benchmarking Tools**
4. **Performance Evaluation**

## Section 1: Parallel Connections Impact on Page Load Times

### Objective:
To analyze the impact of parallel connections on the page load times of commercial/institutional websites running HTTP/1.1, HTTP/2, or HTTP/3.

### Key Findings:
- Tested with 6, 20, and 50 parallel connections using the institutional website: `https://web.unipv.it/`.
- **Results**: Increasing the number of parallel connections resulted in higher page load times.
  - 6 connections: 0.755s
  - 20 connections: 0.984s
  - 50 connections: 1.60s
- Overloading the server with too many parallel connections can cause performance degradation.

## Section 2: Impact of Cache Mechanisms on Page Load Times

### Objective:
To examine the effect of caching on various websites using HTTP/1.1, HTTP/2, and HTTP/3 (both secure and non-secure connections).

### Websites Tested:
- `http://www.inf.uniroma3.it/` (HTTP/1, non-secure)
- `https://vision.unipv.it/wmt/` (HTTP/1, secure)
- `https://www.amazon.it/` (HTTP/2, secure)
- `https://www.netflix.com/` (HTTP/3, secure)

### Key Findings:
- Cache implementation significantly reduced page load times.
  - **Example**: For `https://www.amazon.it/`, the page load time without cache was 3.96s and with cache it was reduced to 0.765s.
- HTTP headers such as `Cache-Control` define caching behavior, including directives like `no-cache`, `private`, and `public`.

## Section 3: Website Performance Benchmarking with Apache Benchmark (ab)

### Objective:
To evaluate the performance of commercial/institutional websites using the Apache Benchmark tool.

### Key Findings:
- Tested `https://www.zara.com/` and `https://www.fbi.gov/`.
  - Zara: 10 requests completed in 11.875s with an average request time of 1187ms.
  - FBI: 10 requests completed in 0.641s with an average request time of 64ms.
- Results showed the FBI website performed much better under the same conditions compared to Zara, with more consistent request times.

## Section 4: Performance Evaluation with nghttp and h2load

### Tools Used:
- **nghttp**: For interacting with HTTP/2 servers and analyzing performance.
- **h2load**: For benchmarking HTTP/2 and HTTP/1.1 websites.

### Key Findings:
- **nghttp**: Showed detailed information about connection setup, headers, and response frames for `https://www.zara.com/`.
- **h2load**: Performed load testing on Zara’s website, with 100 requests sent using 50 clients. TLSv1.3 was used for encryption, and HTTP/2 was the application protocol.

### Performance Testing:
- Load testing with custom duration (`-D` flag) showed how server performance evolved over a specified time frame.
- Warming-up periods (`--warm-up-time` flag) allowed preloading and performance comparison during subsequent tests.

## Conclusion:
This report provided hands-on experience with various web performance techniques, including parallel connections, caching mechanisms, and website benchmarking tools. Practical testing offered valuable insights into theoretical concepts learned during coursework.

## License
This project is for educational purposes only.
