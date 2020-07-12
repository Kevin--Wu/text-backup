## 一、简介

nginx是一个高性能的HTTP转发服务器，用于提供反向proxy

- 正向proxy：到达WEB服务器之前所加的proxy，比如通过某类软件访问外网。对于正向proxy来说，用户可以感知使用了proxy，但服务器无法感知是否使用了proxy。

  ```mermaid
  graph LR
  	1[用户]-->3[正向proxy]
  	3-->4[服务器]
  ```

- 反向proxy：到达WEB服务器之后所加的proxy，比如访问百度。中间有个负载proxy服务器，用于指向实际的服务器。对于反向proxy来说，用户无法感知使用了proxy，但服务器可以感知使用了proxy。

  ```mermaid
  graph LR
  	1[用户]-->3[服务器的反向proxy]
  	3-->4[server 1]
  	3-->5[server 2]
  	3-->6[server 3]
  ```