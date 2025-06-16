HTTP is a TCP/IP-based application layer protocol

Works over TCP port 80, HTTPS uses port 443

HTTP/0.9 (1991):

Only GET

No headers

Response had to be HTML

Connection closed after response

HTTP/1.0 (1996):

Added POST, HEAD

Introduced headers, status codes, character sets, caching, content encoding

Multiple content types supported

Single request per connection

Three-way TCP handshake: SYN → SYN-ACK → ACK

HTTP/1.1 (1999):

Added PUT, PATCH, OPTIONS, DELETE

Host header required

Persistent connections by default

Pipelining (multiple requests over same connection)

Chunked transfer encoding for dynamic content

Enhanced features: caching, byte ranges, cookies, compression, new status codes

SPDY (2009):

Experiment from Google to reduce latency

Introduced multiplexing, compression, prioritization

HTTP/2 (2015):

Binary protocol

Uses frames and streams

Multiplexing: multiple requests over one connection

Header compression (HPACK)

Server Push (PUSH_PROMISE)

Request prioritization

Mostly used over TLS (HTTPS) with modern encryption requirements