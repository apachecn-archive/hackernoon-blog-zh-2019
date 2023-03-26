# nebula container orchestrator——面向物联网设备和分布式系统的容器编排

> 原文：<https://medium.com/hackernoon/nebula-container-orchestrator-container-orchestration-for-iot-devices-distributed-systems-45f8a9a605f8>

![](img/69be21f20cb00dcb8fba32de197ed677.png)

Photo by [Mateusz Dach](https://www.pexels.com/@mateusz-dach-99805) on [Pexels.com](http://www.pexels.com)

比方说，你开始了一份新的工作，在一家公司担任开发人员/开发人员/SRE/etc，该公司开发了一款新的智能音箱(想想亚马逊 Echo 或 Google home)，你说这款设备取得了很大的成功，你很快发现自己拥有了一百万个客户，每个人家里都有一台设备，听起来很棒，对吧？现在，您面临的唯一问题是如何处理分布在世界各地的一百万台设备的部署？

*   你可以走大多数老厂商的路，发布一个软件包供最终用户下载并安装在公司网站上，但在这个时代，这将很快让你的客户流失到竞争对手那里，他们没有这么高的维护需求。
*   你可以在你的代码库中创建一个自我更新的系统，但是这需要开发团队进行大量的维护和投入大量的人力&即使这样也可能会导致问题和失败。
*   您可以将代码库容器化，在每个智能音箱上创建一个单独的服务器 Kubernetes 集群，并从所有这些集群中创建一个巨大的联合集群(因为 Kubernetes 不支持这种规模，也不支持延迟容忍工作人员，这是必需的)，但这将导致所有资源的巨大成本，仅运行所有上述集群就浪费了这些资源。
*   你可以使用[Nebula Container Orchestrator](https://nebula-orchestrator.github.io/)——它正是为解决这种分布式编排需求而设计的。

你可能已经从标题中猜到了，我想讨论列表中的最后一个选项。

[Nebula Container Orchestrator](https://nebula-orchestrator.github.io/)旨在帮助开发人员和运营人员像对待分布式 Dockerized 应用程序一样对待物联网设备。它的目标是充当物联网设备以及分布式服务(如 CDN 或边缘计算)的 Docker orchestrator，这些服务可以跨越全球数千台(甚至数百万台)设备，而且它是开源和完全免费的。

**不同的需求导致不同的指挥**

仔细想想，分布式编制器有以下要求:

*   它需要能够容忍延迟，如果物联网设备是分布式的，那么每个设备都将通过互联网连接到 orchestrator，连接可能不总是稳定或快速的。
*   它需要向外扩展以处理成千上万(甚至成千上万)的物联网设备，大规模部署正迅速变得越来越普遍。
*   它需要在多种架构上运行——许多物联网设备都使用 ARM 板。
*   它需要自我修复——你不希望每次出现一点小故障就不得不穿过城市去重置设备，对吧？
*   代码需要与硬件耦合——如果你的公司制造了上述例子中的智能扬声器&智能冰箱，你将需要确保代码与打算在其上运行的设备耦合(在物联网用例中，不要将不同的应用打包到相同的设备中)。

这与三大 orchestrator(Kubernetes、Mesos 和 Swarm)截然不同，它们旨在将尽可能多的不同应用程序/微服务打包到单个(或相对较少的)数据中心的相同服务器上，因此没有一个提供真正的延迟容忍连接，Swarm 和 Kubernetes 的可扩展性仅限于几千名员工。

**星云架构**

![](img/8b33e3d7c7f7b098e034882ce3ac393a.png)

[Nebula](https://nebula-orchestrator.github.io/) 设计了无状态 RESTful Manger 微服务，以提供管理集群的单点，以及提供所有容器检查更新的单点，在基于拉的方法中使用 Kafka 启发的单调 ID 配置更新， 这确保了对 Nebula 管理的任何应用程序的更改同时被拉至所有被管理的设备，并且还确保了所有设备将总是具有最新版本的配置(由于单调 ID)，所有数据都存储在 MongoDB 中，这是系统的单点事实， 在工人方面，它基于每个设备上的工人容器，负责启动/停止/更改在该设备上运行的其他容器，由于其设计，每个组件都可以向外扩展&，因此 Nebula 可以根据您的需要进行扩展。

你可以在 https://nebula.readthedocs.io/en/latest/architecture/[的](https://nebula.readthedocs.io/en/latest/architecture/)阅读更多关于星云建筑的内容

**星云特征**

由于 Nebula 完全是为了支持分布式系统而设计的，因此它有一些简洁的功能，允许它控制分布式物联网系统:

*   旨在横向扩展其所有组件(物联网设备、API 层和 Mongo 全部横向扩展)
*   能够管理数百万台物联网设备
*   容许延迟—即使设备离线，当他恢复在线时，它也会重新同步
*   动态添加/删除受管设备
*   快速简单的代码部署，使用新的容器图像标签(或其他配置更改)的单一 API 调用，它将被推送到该应用程序的所有设备。
*   安装简单——MongoDB &一个无状态 API 是管理层所需要的全部内容&您想要管理的每个物联网设备上的一个包含一些 envvars 的容器负责工作层
*   管理所有设备的单一 API 端点
*   允许使用同一个 Nebula orchestrator 控制多个设备(多个应用和设备组)
*   不限于物联网，对其他类型的分布式系统也很有用
*   API、Python SDK 和 CLI 控件可用

**举个小例子**

以下命令将安装一个[星云](https://nebula-orchestrator.github.io/)集群供你玩，还将创建一个示例应用程序，需要安装 Docker，curl & docker-compose:

```
curl -L "https://raw.githubusercontent.com/nebula-orchestrator/docs/master/examples/hello-world/start_example_nebula_cluster.sh" -o start_example_nebula_cluster.sh && sudo sh start_example_nebula_cluster.sh
```

但是让我们回顾一下这个命令的作用，以便更好地理解这个过程:

1.  脚本下载并运行 docker-compose.yml 文件，该文件创建:

> A)MongoDB 容器——保存 Nebula 应用程序当前状态的后端数据库。
> 
> b)一个管理器容器——一个 RESTful API 端点，管理员从这里管理 Nebula 设备从这里获取最新的配置状态，以匹配它们的当前状态
> 
> c)工人容器—这通常在物联网设备上运行，每个设备上只需要一个，但这只是一个示例，它运行在与管理层组件运行的服务器相同的服务器上。

值得一提的是 worker 容器上设置的“DEVICE_GROUP=example”环境变量，这个 DEVICE_GROUP 变量控制哪些 nebula 应用程序将连接到设备(类似于其他 orchestrators 中的 pod 概念)。

2.然后，脚本等待 API 变得可用。

3.一旦 API 可用，脚本将发送以下两个命令:

```
curl -X POST \                               
http://127.0.0.1/api/v2/apps/example \
-H 'authorization: Basic bmVidWxhOm5lYnVsYQ=='  \                            -H 'cache-control: no-cache'    \                     
-H 'content-type: application/json'    \                            -d '{
    "starting_ports": [{"81":"80"}],  
    "containers_per": {"server": 1},        
    "env_vars": {},                       
    "docker_image" : "nginx",                        
    "running": true,                                
     "volumes": [],  
     "networks": ["nebula"],                 
     "privileged": false,           
     "devices": [],     
     "rolling_restart": false        
}'
```

该命令创建一个名为“example”的应用程序，并将其配置为运行 nginx 容器来监听端口 81，正如您所看到的，它还可以控制通常传递给 docker run 命令的其他参数，如 envvars、networks 或 volume mounts。

```
curl -X POST \                                
 http://127.0.0.1/api/v2/device_groups/example \                                 -H 'authorization: Basic bmVidWxhOm5lYnVsYQ==' \                                 -H 'cache-control: no-cache' \                                
-H 'content-type: application/json' \                                 -d '{ 
    "apps": ["example"]             
}'
```

该命令创建一个名为“example”的设备组，并将名为“example”的应用程序连接到该设备组，

4.在 nebula API 上创建应用程序& device_groups 后，worker 容器将获取对 device_group 的更改，device _ group 被配置为该应用程序的一部分(本例中为“示例”)，并将在服务器上启动 Nginx 容器，您可以运行“docker logs worker”来查看 Nginx 容器在启动前的下载情况(如果您的连接速度较慢，这可能需要一点时间)。完成后，你可以在浏览器上访问[http://<server _ exterior _ FQDN>:81/](http://127.0.0.1:81/)来查看它的运行情况

现在我们已经有了一个运行的星云系统，我们可以开始使用它来看看它的真正优势:

*   我们可以通过在远程工作者上运行工作者容器来添加更多的远程工作者:

```
sudo docker run -d --restart unless-stopped -v /var/run/docker.sock:/var/run/docker.sock --env DEVICE_GROUP=example --env REGISTRY_HOST=https://index.docker.io/v1/ --env MAX_RESTART_WAIT_IN_SECONDS=0 --env NEBULA_MANAGER_AUTH_USER=nebula --env NEBULA_MANAGER_AUTH_PASSWORD=nebula --env NEBULA_MANAGER_HOST=<your_manager_server_ip_or_fqdn> --env NEBULA_MANAGER_PORT=80 --env nebula_manager_protocol=http --env NEBULA_MANAGER_CHECK_IN_TIME=5 --name nebula-worker nebulaorchestrator/worker
```

值得一提的是，通过上面的命令传递的许多 envvars 是可选的(具有相同的默认值)&我们可以在多少台设备上运行该命令没有限制，在某些时候，您可能必须向外扩展管理器和/或后端数据库，但这些也没有限制。

*   我们可以通过一个 API 调用来更改所有设备上的容器映像，例如，让我们将容器映像替换为 Apache 来进行模拟

```
curl -X PUT \[http://127.0.0.1/api/](http://127.0.0.1/api/apps/example/update)v2/[apps/example/update](http://127.0.0.1/api/apps/example/update) \-H ‘authorization: Basic bmVidWxhOm5lYnVsYQ==’ \-H ‘cache-control: no-cache’ \-H ‘content-type: application/json’ \-d ‘{“docker_image”: “httpd:alpine”}’
```

*   同样，我们也可以更新应用的任何参数，如 env_vars、特权权限、卷挂载等，API 端点以及 Python SDK 和 CLI 的完整列表可在[https://nebula.readthedocs.io/en/latest/](https://nebula.readthedocs.io/en/latest/)的文档页面上找到

希望这个小指南能让你看到物联网 docker orchestrator 的需求及其使用案例&如果你有兴趣阅读更多相关信息，你可以访问位于 https://nebula-orchestrator.github.io/[的](https://nebula-orchestrator.github.io/)[Nebula Container Orchestrator](https://nebula-orchestrator.github.io/)网站，或者直接跳到 https://Nebula . readthedocs . io 上的文档