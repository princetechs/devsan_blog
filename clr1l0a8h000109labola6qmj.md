---
title: "Building a Simple Single-Page Web Server in Ruby"
seoTitle: "Building a Simple Single-Page Web Server in Ruby"
seoDescription: "Building a Simple Single-Page Web Server in Ruby"
datePublished: Sat Jan 06 2024 04:45:20 GMT+0000 (Coordinated Universal Time)
cuid: clr1l0a8h000109labola6qmj
slug: building-a-simple-single-page-web-server-in-ruby
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704516216403/795530b3-c0b2-4316-8f2e-9e3253dbceba.png
tags: productivity, programming-blogs, http, ruby, server, rails, web-development, ruby-on-rails, developer, tips, coding, programming-tips

---

Imagine crafting a web server in just a few lines of Ruby code! Let's explore how to create a basic single-page web server using Ruby's `socket` library.

#### Interactive Q&A: Exploring the Basics

**Q:** What library does Ruby offer for handling low-level networking operations? **A:** The `socket` library.

**Q:** What does [`TCPServer.new`](http://TCPServer.new)`('`[`localhost`](http://localhost)`', 8080)` in Ruby do? **A:** It initializes a TCP server on the [localhost](http://localhost) at port 8080.

Embracing Ruby's Socket Magic

With the power of the `socket` library, you can craft a minimalist web server in Ruby:

```ruby
require 'socket'

server = TCPServer.new('localhost', 8080)

loop do
  client = server.accept

  request = client.gets

  puts "Request: #{request}"

  response = "HTTP/1.1 200 OK\r\nContent-Type: text/html\r\n\r\n<html><body><h1>Hello, World!</h1></body></html>"

  client.puts response

  client.close
end
```

#### Exploring the Server Logic

This code snippet initializes a TCP server on [`localhost`](http://localhost) at port `8080`. It enters an infinite loop to continuously handle incoming client connections.

* Upon connection, it retrieves the client's request.
    
* It responds with a simple HTTP/1.1 200 OK response containing a basic HTML page displaying "Hello, World!".
    

#### Running the Server

1. **Save the Code:** Store this code in a file, say `simple_server.rb`.
    
2. **Run the Server:** Open your terminal and execute `ruby simple_server.rb`.
    

#### Accessing Your Single-Page Site

Open a web browser and visit [`http://localhost:8080`](http://localhost:8080). You'll behold the magic of your Ruby-built web server displaying a "Hello, World!" message.

#### Conclusion: Crafting a Basic Web Server in Ruby

With minimal code, Ruby's `socket` library empowers you to create a functioning web server. This simple example showcases the essence of handling incoming requests and serving responses—all within Ruby!