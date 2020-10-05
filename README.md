# 前言

此项目是基于spring的购物平台和后台管理系统。服务端开发主要是java+spring架构，前端页面是基于Vue+elemnt-ui、javaScript开发。
数据库全程使用了MySql。

# 最新说明

2020-10-05 夏晨商城1.0版本发布

# 一、项目架构

## 1.1 购物平台

我的购物平台全名为夏晨商城，前端页面内容暂不说明。后端的服务为springboot服务，为了更好地体现spring微服务地概念，在这里我把整个购物系统分为六大服务：页面服务、网关服务、商品服务、订单服务、用户服务和右键服务。
下面将逐个说明每个服务的功能。

### 1.1.1 服务设计详细说明

#### 页面服务（主要服务）

页面服务提供网页的展示，你可以访问到任何平台的页面，其它的用户、商品、订单的信息都由其余的服务所提供。这样，主要的页面信息得到了展示无需担心其它服务崩溃时造成的影响。

#### 商品服务

商品服务提供了商品的展示和商品的分类，如在主页面中你可以看到所有的商品是三级分类的，商品都在三级分类目录被选中的情况下被展示。在后续的补充中，还预设了商品的检索服务。这将在版本2.0中提供更新。

### 订单服务

作为购物平台，不仅要展示商品，还要提供商品的选择、下单服务。在订单服务中，商品添加到用户的购物车、在购物车进一步选中、删除、提交结算都是订单服务的工作。需要注意的是，添加到购物车和下单都是基于用户已经登录的状态下，而用户的获取、登录、注册都是放在用户服务之下的。

#### 用户服务

上面已经说到了订单服务在很大的程度上依赖于用户服务，但用户服务除了可以提供以上功能外，还提供一个会员中心的功能。在会员中心中，用户可以管理自己所有的基础个人信息，还可以修改这些信息；当然，作为购物平台，用户要能看到自己所有发生的交易明细，订单的状态等等。

#### 邮件服务

在用户注册、修改密码和下单时都需要向用户发送邮件。另外，在用户注册首次注册账号时还需要检测用户邮箱服务器是否存在（能正常工作），这也是邮件服务的一部分。

#### 网关服务（主要服务）

由于服务众多，在使用sringboot时，不同的服务使用了不同的端口号，随着后续服务的增加，很多时候并不记得端口号，为了更好地解决这个问题，我使用了网关服务对其余的服务做了端口转发和路径重写（适应整体系统的需要），达到统一的目的。

## 1.2 后台管理系统
