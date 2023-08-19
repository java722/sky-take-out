# sky-take-out



#### 项目结构
分为 管理端-外卖商家使用 和 用户端-点餐用户使用
| **序号** | **名称**     | **说明**                                                     |
| -------- | ------------ | ------------------------------------------------------------ |
| 1        | sky-take-out | maven父工程，统一管理依赖版本，聚合其他子模块                |
| 2        | sky-common   | 子模块，存放公共类，例如：工具类、常量类、异常类等           |
| 3        | sky-pojo     | 子模块，存放实体类、VO、DTO等                                |
| 4        | sky-server   | 子模块，后端服务，存放配置文件、Controller、Service、Mapper等 |

#### 网关
nginx 做反向代理和负载均衡

#### 文档
Swagger 的knife4j 做接口文档

#### 异常处理
用@RestControllerAdvice和@ExceptionHandler注解写的全局异常处理器，处理项目中抛出的业务异常

#### 拦截器
用的Spring Boot拦截器验证是否带有token，login接口在注册自定义拦截器中排除了，登录成功后会返回token

#### ThreadLocal
比如在在管理端添加员工功能时拦截器代码中会将当前管理员的ID存入到ThreadLocal，在添加员工接口时就可以给创建人ID赋值了