# Cookie

- Cookie是用户访问Web服务器时，服务器在用户硬盘上存放的信息，好像是服务器送给客户的点心
- 服务器可以根据Cookie来跟踪，识别用户，这对于需要区别用户的场合（如登录）非常有效

- 一个cookie包含一对Key/Value。下面的代码生成一个Cookie并将其通过浏览器写入到用户硬盘中

  ```java
  Cookie cookie = new Cookie("cookieName", "cookieValue");
  response.addCookie(cookie);
  ```

  