---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-11-29T20:18
---
---

- curl is a request sending 
### Basic Usage

- **GET request**
    
    ```bash
    curl https://example.com
    ```
    
- **Save output to file**
    
    ```bash
    curl -o output.txt https://example.com
    ```
    
- **Follow redirects**
    
    ```bash
    curl -L https://example.com
    ```
    

### HTTP Methods

- **POST request**
    
    ```bash
    curl -X POST https://example.com
    ```
    
- **PUT request**
    
    ```bash
    curl -X PUT https://example.com
    ```
    
- **DELETE request**
    
    ```bash
    curl -X DELETE https://example.com
    ```
    

### Sending Data

- **Form data**
    
    ```bash
    curl -d "key=value" https://example.com
    ```
    
- **JSON data**
    
    ```bash
    curl -H "Content-Type: application/json" -d '{"name": "Sol"}' https://example.com
    ```
    

### Headers

- **Add header**
    
    ```bash
    curl -H "Authorization: Bearer TOKEN" https://example.com
    ```
    
- **Multiple headers**
    
    ```bash
    curl -H "Accept: application/json" -H "User-Agent: custom" https://example.com
    ```
    

### Authentication

- **Basic Auth**
    
    ```bash
    curl -u username:password https://example.com
    ```
    
- **Bearer Token**
    
    ```bash
    curl -H "Authorization: Bearer <token>" https://example.com
    ```
    

### File Upload

- **Upload file**
    
    ```bash
    curl -F "file=@path/to/file" https://example.com/upload
    ```
    

### Downloading

- **Download and keep filename**
    
    ```bash
    curl -O https://example.com/file.zip
    ```
    
- **Resume download**
    
    ```bash
    curl -C - -O https://example.com/file.zip
    ```
    

### Debugging

- **Verbose mode**
    
    ```bash
    curl -v https://example.com
    ```
    
- **See only headers**
    
    ```bash
    curl -I https://example.com
    ```
    

### Proxy

- **Use proxy**
    
    ```bash
    curl -x http://proxy:8080 https://example.com
    ```
    

### Cookies

- **Send cookies**
    
    ```bash
    curl -b "cookie=value" https://example.com
    ```
    
- **Save cookies**
    
    ```bash
    curl -c cookies.txt https://example.com
    ```
    

### Timeout

- **Set max time**
    
    ```bash
    curl --max-time 10 https://example.com
    ```
    

### User-Agent

- **Custom UA**
    
    ```bash
    curl -A "MyBrowser/1.0" https://example.com
    ```