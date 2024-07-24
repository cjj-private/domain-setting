# 域名配置文档


每当添加域名时，需要:

1) 在 [Cloudflare](https://dash.cloudflare.com/) 上添加域名解析。
2) 在 Nginx配置文件 添加域名。
3) 在 [Manage后台](https://manage.d-prod.xyz/) 注册对应域名, 然后点击 `启用`。
4) 确认域名能正常访问。

> 相关脚本：[DevOps / document / 自动化脚本 / NameCheap-Cloudflare /](https://git.theone.quest/devops/document/-/tree/main/%E8%87%AA%E5%8A%A8%E5%8C%96%E8%84%9A%E6%9C%AC/Namecheap-Cloudflare)

# 目录

- [D-PROD 域名文档](#d-prod-域名文档)
- [目录](#目录)
- [域名指向分类](#域名指向分类)
- [推广专属APP域名](#推广专属app域名)
- [防封域名](#防封域名)
- [主站域名](#主站域名)
- [落地页域名](#落地页域名)
- [H5域名](#h5域名)
- [代理H5专属域名](#代理h5专属域名)
- [推广专属H5域名](#推广专属h5域名)
- [代理后台推广域名](#代理后台推广域名)
- [推广后台域名](#推广后台域名)
- [云平台域名](#云平台域名)
  - [增加云平台域名到数据库 SQL](#增加云平台域名到数据库-sql)
- [Manage后台](#manage后台)
  - [怎么添加域名](#怎么添加域名)
  - [怎么删除域名](#怎么删除域名)
  - [怎么修改代理ID](#怎么修改代理id)
  - [怎么查代理ID](#怎么查代理id)
- [文档更改](#文档更改)


# 域名指向分类

| S/N | 域名类型      | Nginx配置文件       | 域名指向          |
|-----|--------------|--------------|--------------|
| 1   | 云平台域名 | [backend-frontend/cloud-web.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/backend-front/conf/cloud-web.conf) | af9921fd6867f4998a99ab0731f1e717-dd77b54993a37953.elb.ap-northeast-1.amazonaws.com
| 2   | 防封域名 / 推广专属APP域名 / 代理渠道专属域名 | [/etc/nginx/domain.conf](https://git.theone.quest/devops/domainrouter-nginx/-/blob/main/domain.conf) | 54.250.163.70
| 3   | 主站域名 | [/etc/nginx/domain-zhu.conf](https://git.theone.quest/devops/domainrouter-nginx/-/blob/main/domain-zhu.conf) | 54.250.163.70 |
| 4   | 落地页域名 | [game-frontend/luodi.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/game-front/conf/luodi.conf) | a1fa323a7fd3d48f080592a158155cc9-3da8961289a5a005.elb.ap-northeast-1.amazonaws.com |
| 5   | H5域名 / 代理H5专属域名 / 推广专属H5域名 | [game-web/frontend.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/game-web/conf/frontend.conf) | a52baef66cebd46759fb6472746b3d40-7cb9d3f62def0df3.elb.ap-northeast-1.amazonaws.com |
| 6   | 代理后台推广域名 | [backend-frontend/carshnet-web.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/backend-front/conf/carshnet-web.conf) | af9921fd6867f4998a99ab0731f1e717-dd77b54993a37953.elb.ap-northeast-1.amazonaws.com |
| 7   | 推广后台域名 | [backend-frontend/promote-web.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/backend-front/conf/promote-web.conf) | af9921fd6867f4998a99ab0731f1e717-dd77b54993a37953.elb.ap-northeast-1.amazonaws.com

<details>
<summary> 域名类型图（点击查看） </summary>
![Alt text](pictures/500w-drawing.jpg)
</details>

# 推广专属APP域名

域名指向跟防封域名一样。

* www.panalopoker.io

解析到: 54.250.163.70

> 【PROD】Nginx 配置: [/etc/nginx/domain.conf](https://git.theone.quest/devops/domainrouter-nginx/-/blob/main/domain.conf)

# 防封域名

防封域名 - 主要的功能就是给落地页当炮灰吧。

当访问 `{防封域名}/prod1251219_1/` 后， 会自动跳转到 `{落地页}/prod1251219_1/`。

* www.ffz88z.com
* www.ffax1.com
* www.ffbo2.com
* www.ffbi3.com
* www.ffcb4.com
* www.ffup5.com
* www.ffme6.com
* www.ffoi7.com
* www.ffgl8.com
* www.fflj9.com
* www.ffx1o.com
* www.yihuuo.com
* www.xugtty.com
* www.zvnnopu.com
* www.2qwa9yo0lfj7y3e3.xyz
* www.9dphapp.org
* www.ffzx35.com
* www.panalopoker.com
* www.panalopoker.store
* www.bww666.com


解析到: 54.250.163.70

>  【PROD】Nginx 配置: [/etc/nginx/domain.conf](https://git.theone.quest/devops/domainrouter-nginx/-/blob/main/domain.conf)

# 主站域名

* www.qpz88z.com
* www.jvdpt7.com
* www.hawkgaming.com.ph
* www.hawkgaming.com
* www.hawkesports.com
* www.jili747.com
* www.qp53d.com
* www.panalo.poker
* www.jvd2demoapp.com
* www.panalopoker.ph
* www.bw77777.com



解析到: 54.250.163.70

> 【PROD】Nginx 配置: [/etc/nginx/domain-zhu.conf](https://git.theone.quest/devops/domainrouter-nginx/-/blob/main/domain-zhu.conf)

# 落地页域名

原域名: https://luodi.d-prod.xyz

* www.ldz88z.com


解析到 nginx-game-front (NLB): 

```
a1fa323a7fd3d48f080592a158155cc9-3da8961289a5a005.elb.ap-northeast-1.amazonaws.com
```

> 【PROD】Nginx 配置: [game-frontend/luodi.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/game-front/conf/luodi.conf)

# H5域名

原域名: www.d-prod.xyz

* www.h5z88z.com




解析到 nginx-game-web (NLB): 

```
a52baef66cebd46759fb6472746b3d40-7cb9d3f62def0df3.elb.ap-northeast-1.amazonaws.com
```

> 【PROD】Nginx 配置: [game-web/frontend.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/game-web/conf/frontend.conf)

# 代理H5专属域名

* www.ph9d.com


解析到 nginx-game-web (NLB): 

```
a52baef66cebd46759fb6472746b3d40-7cb9d3f62def0df3.elb.ap-northeast-1.amazonaws.com
```

> 【PROD】Nginx 配置: [game-web/frontend.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/game-web/conf/frontend.conf)

# 推广专属H5域名

* www.jili747.ph
* www.jili747.vip



解析到 nginx-game-web (NLB): 

```
a52baef66cebd46759fb6472746b3d40-7cb9d3f62def0df3.elb.ap-northeast-1.amazonaws.com
```

> 【PROD】Nginx 配置: [game-web/frontend.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/game-web/conf/frontend.conf)

# 代理后台推广域名

原域名: carshnet.d-prod.xyz

* www.dlz88z.com
* www.dlax1.com


解析到 nginx-backend-front (NLB):

```
af9921fd6867f4998a99ab0731f1e717-dd77b54993a37953.elb.ap-northeast-1.amazonaws.com
```

> 【PROD】Nginx 配置: [backend-frontend/carshnet-web.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/backend-front/conf/carshnet-web.conf)

# 推广后台域名

原域名: promote.d-prod.xyz

* www.tgz88z.com


解析到 nginx-backend-front (NLB): 

```
af9921fd6867f4998a99ab0731f1e717-dd77b54993a37953.elb.ap-northeast-1.amazonaws.com
```

> 【PROD】Nginx 配置: [backend-frontend/promote-web.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/backend-front/conf/promote-web.conf)

# 云平台域名

原域名: cloud.d-prod.xyz

* www.cpz88z.com
* www.cpax1.com


解析到 nginx-backend-front (NLB): 

```
af9921fd6867f4998a99ab0731f1e717-dd77b54993a37953.elb.ap-northeast-1.amazonaws.com
```

> 【PROD】Nginx 配置: [backend-frontend/cloud-web.conf](https://git.theone.quest/fruit/infrastructure/aws/prod-ap-northeast-1/kubernetes/fruit-helm/-/blob/main/nginx-prod/sites-enabled/backend-front/conf/cloud-web.conf)

## 增加云平台域名到数据库 SQL

截止 28 Dec 2023, 已可以直接在 Manage 前端添加 “云平台域名”。

<details>
  <summary> 怎么手动在 Cloud DB 添 ”云平台域名“ (点击查看) </summary>

截止 18 Oct 2023, 前端还不能添加 ”云平台域名“，我们需要手动在 Cloud DB 添加，以下是步骤：

```sql
--1. 进入 Cloud 数据库 (PROD 环境)
use cloud;

--2. 添加域名
INSERT INTO cloud_global_white_listed_domain( admin_id, create_admin_id, create_time, update_time, deleted, white_domain, status, domain_type, free_type) VALUES (0, 0, 1611733247, 1611733247, 0, 'https://www.cpz88z.com', 1, 1, 2);
```

</details>

# Manage后台

## 怎么添加域名

添加步骤：

1. 登录: https://manage.d-dqa.xyz/

2. 点击 “新增”

![Alt text](pictures/1.ManagePlatform-Login.png)

3. 输入域名（批量添加的话，可以用回车来分割）

4. 填写代理ID (JVD三方的代理ID是 207)

5. 选择对应的域名分类（需跟三方确认），然后点击 "确定"

![Alt text](pictures/2.ManagePlatform-Explained.png)

6. 向下划滚，在域名分类里 点击 “启用”

![Alt text](pictures/3.ManagePlatform-Activate.png)

## 怎么删除域名

为了避免意外，Manage前端并不提供删除域名的功能，因为误删会直接影响游戏。

若我们想在 Manage 删除域名，必须在 Cloud DB 手动操作。

```sql
--1. 进入 Cloud 数据库 (PROD 环境)
use cloud;

--2. 首先在 cloud_global_domain表 查看并确认你想删除的域名 (这里我们以查看3个域名为例)
select id, domain from cloud_global_domain where domain in ("xugtty.com", "yihuuo.com", "zvnnopu.com");

--3. 确认上述是想删除的对象后，直接用 DELETE 直接删除 （!小心慎用!）
delete from cloud_global_domain where domain in ("xugtty.com", "yihuuo.com", "zvnnopu.com");
```

演示:

![Alt text](pictures/ManagePlatform-delete.png)

## 怎么修改代理ID

目前只能用 SQL 修改，尽量让开发组长自己操作。

```sql
--1. 进入 Cloud 数据库 (PROD 环境)
use cloud;

--2. 首先在 cloud_global_domain表 查看并确认你想修改 代理ID 的域名。 (这里我们以 jili 域名为例)
SELECT id, admin_id, domain FROM cloud_global_domain WHERE domain like '%jili%';

+----+----------+----------------+
| id | admin_id | domain         |
+----+----------+----------------+
| 74 |      207 | jili747.com    |
| 75 |      207 | jili747.ph     |

+----+----------+----------------+

--3. 确认上述是想修改的对象后，更新代理。（这里我们以更新成 217 为例）
UPDATE cloud_global_domain SET admin_id = 217 WHERE domain like '%jili%';

+----+----------+----------------+
| id | admin_id | domain         |
+----+----------+----------------+
| 74 |      217 | jili747.com    |
| 75 |      217 | jili747.ph     |

+----+----------+----------------+
```

## 怎么查代理ID

**常见情况**: 三方人员不知道 `代理ID`，只知道对应的 `代理用户名`。

```
(三方): 请帮忙加新域名 "bw5201314.love" 到 H5域名
(运维): 好的, 请问代理ID多少?
(三方): 我不知道，我只知道用户叫 bigwinner 什么的..
(运维): 好的，我查下。
```

不用怕！有了关键字，我们可以这样查 `代理ID`:

```sql
-- 以 `代理用户名` 来查
SELECT cloud_sys_admin.id, cloud_sys_admin.username, cloud_global_domain.domain 
FROM cloud_sys_admin JOIN cloud_global_domain 
ON cloud_sys_admin.id = cloud_global_domain.admin_id 
WHERE cloud_sys_admin.username LIKE '%bigwinner%';

-- Output
+-----+----------------+-----------------+
| id  | username       | domain          |
+-----+----------------+-----------------+
| 792 | bigwinneradmin | bww666.com      |
| 792 | bigwinneradmin | bw8686win.com   |

+-----+----------------+-----------------+

-- 通过这个SQL执行，我们可以了解:
-- id = 代理ID
-- username = 代理用户名
-- domain = 该 `代理用户` 所持有的域名

```

# 文档更改

📝 改动记录这里

| S/N | 日期            | 修改                             |
|-----|-----------------|-------------------------------------| 
| 1   | 25 Sep 2023     | 给每个域名添加一个 备用域名             
