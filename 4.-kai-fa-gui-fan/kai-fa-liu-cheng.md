# 4.3 开发流程

随着项目越来越复杂，项目必须逐步走出仅仅依赖肉眼、依赖人多＋运气的质量保障模式。

**自动化测试、以及更加规范的Review流程**，则是必然出现，而且将越来越重要的环节之一。

## 开发规范

1. 开发方法 Scrum + Kanban
2. 每周为一个 Sprint 迭代
3. 周一上午 10 点 - 计划会议，阐述这周的任务目标
4. 每天 10 点准时**站会**
5. 任务完成后从 feature 分支合并代码到 develop 分支, 根据部署可用版本
6. 周五下午 6 点前 - Demo 会议，演示这周的任务（当前 Sprint 的所有任务至少要部署到测试环境）, **对于没有上线的任务，在下周一下班前保证上线**

## 看板定义

* 所有任务以 trello 看板为准
* **所有人** 必须及时更新任务状态
* **优先解决 BUG 任务**, 经测试后及时上线
* 列表定义:
  * **Todo**: 每个 Sprint 待完成的任务列表
  * **Doing**: 正在做的任务列表
  * **Done**: 完成列表，任务已经经过测试后，已经合并到 develop 分支，并部署到 Stage \(Lyon\) 环境，可以让产品经理做验收测试
  * **Sprint Online**: 当前 Sprint 中的任务已经部署到生产环境
  * **Pending**: 由于一些原因，引起功能不能按时上线的，必须在 Comments 中注明原因

## 测试

* 单元测试 + 集成测试
  * 所有后端项目 （API，Library）的**单元测试覆盖率 60% 以上, 否则不允许上线**
  * 由于语言特性，保证所有的功能都在单元测试中体现
  * 与其他的第三方系统的测试（如美团，阿里，Git等），不使用 Mock 数据，保证其**真正可用**
  * 测试既需求，保证测试中覆盖需求中的功能点
* 经过手工测试后，并保证代码静态检查、单元测试通过后，才可合并到 develop 分支，保证 develop 分支的功能完整性

## Git 分支管理

1. 使用 Git 多分支结构
2. 功能分支: 基于 develop 分支建立，命名规则为 feature/xxx
3. Hotfix: 线上的 hotfix ，基于 master 分支建立，命名规则为 hotfix/xxx
4. 功能分支/hotfix 分支在合并到 develop/master 分支时，提交Pull Request请求，同时邀请相关同事进行 Code Review
5. 功能分支/hotfix 分支上线后，及时删除，避免分支过多

![&#x5206;&#x652F;&#x7B56;&#x7565; - &#x9891;&#x7E41;&#x96C6;&#x6210;](https://images-cdn.shimo.im/xLXbhoLVmhI8pOnE/Screen%20Shot%202017-04-24%20at%205.05.15%20PM.png)

![&#x5206;&#x652F;&#x7B56;&#x7565; - &#x5408;&#x5E76;](https://images-cdn.shimo.im/SYLsZryv9xICK65R/Screen%20Shot%202017-04-24%20at%205.11.34%20PM.png!thumbnail)

## Code Review

* Pull Request 时进行 Code Review
* Code Review 前保证静态代码检查，单元测试通过
* **首先 Review 单元测试**，保证从单元测试中覆盖所做的功能点

## 生产环境上线流程

1. 在 develop 分支上的代码，经过产品经理验收后，才可部署到生产环境
2. 如果功能依赖，可以使用 feature toggle 等，关掉依赖功能后上线

