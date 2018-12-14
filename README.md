###Spring Security

Spring security基本原理

![](https://i.imgur.com/7c1PoAb.png)

授权流程：
 
       所有请求url -> BasicAuthenticationFilter / 
       UsernamePasswordAuthenticationFilter -> 
       FilterSecurityInterceptor -> 
       BasicAuthenticationFilter / UsernamePasswordAuthenticationFilter -> FilterSecurityInterceptor -> 
       controller层

    
       1）所有的请求进入BasicAuthenticationFilter进行过滤
       2）然后进入 FilterSecurityInterceptor 过滤器进行权限验证
       3）如果在 FilterSecurityInterceptor 中权限验证不通过就会跳转到 /login 请求进行处理
       5）然后在进入 BasicAuthenticationFilter 或者 UsernamePasswordAuthenticationFilter 过滤器
       6）再进入 FilterSecurityInterceptor
       7）只有当 FilterSecurityInterceptor 过滤通过了才会跳转到之前的请求路径