# Micro SSR


![](https://img2020.cnblogs.com/blog/436453/202012/436453-20201207102648809-1655234126.png)

## 背景
笔者在逛掘金的时候，有幸看到掘友[狼族小狈](https://juejin.cn/user/219558054215229)开源的 [genesis](https://github.com/fmfe/genesis) — 一个可以支持 `SSR` 和 `CSR` 渲染的微服务解决方案。总体来说思想不错，但是基于 Kubernetes 云原生部署方面一直没有完整的实践。所以笔者决定做个非官方的 Demo 供大家参考。

这个项目怎么用，它的官方文档已经很详细，这里就不做教程了。

## 上云

笔者已部署到：[https://micro-ssr.hacker-linner.com](https://micro-ssr.hacker-linner.com/)

### Demo 项目介绍：
* [micro-ssr](https://github.com/Hacker-Linner/micro-ssr)：Helm Chart 部署文件
* [micro-ssr-common](https://github.com/Hacker-Linner/micro-ssr-common)：基础的页面聚合渲染微服务，包含公共导航
* [micro-ssr-home](https://github.com/Hacker-Linner/micro-ssr-home)：首页渲染微服务
* [micro-ssr-about](https://github.com/Hacker-Linner/micro-ssr-about)：关于我们页面渲染微服务

### Helm 部署聚合微服务

```sh
git clone https://github.com/Hacker-Linner/micro-ssr
cd micro-ssr
helm install micro-ssr ./micro-ssr -f values.yaml -n micro-ssr
```

### Helm 部署首页微服务

```sh
helm install micro-ssr-home ./micro-ssr -f values-home.yaml -n micro-ssr
```

### Helm 部署关于我们微服务

```sh
helm install micro-ssr-about ./micro-ssr -f values-about.yaml -n micro-ssr
```

![](https://img2020.cnblogs.com/blog/436453/202012/436453-20201207102707377-1005837617.png)

![](https://img2020.cnblogs.com/blog/436453/202012/436453-20201207102715529-518851577.png)


### Refs

* [前端云原生，以 Kubernetes 为基础设施的高可用 SSR(Vue.js) 渲染微服务初探（开源 Demo）](https://mp.weixin.qq.com/s/N5cZYdqZlnR2EHH33hSwCg)
* [深入理解 TypeScript](https://jkchao.github.io/typescript-book-chinese/project/namespaces.html)
* [Genesis](https://fmfe.github.io/genesis-docs/)
* [tms](https://followmetech.github.io/tms/)