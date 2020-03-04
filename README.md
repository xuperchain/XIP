# XuperChain Improvement Proposals(XIPs)

[中文](#中文-1)
-----
## Introduction
XuperChain Improvement Proposals (XIPs) describe standards for the XuperChain platform which external developer participated in, including libraries, tools, protocols, client APIs, and contract standards. This changes need to be first discussed, and sometimes formally documented, before they can be implemented.

This document describes the process for proposing, documenting, and implementing changes to the XuperChain project.

## The Complete Process
The following process is the process for reviewing a proposal, reaching
a decision about whether to accept or decline the proposal, designing, developing, testing and released with xuperchain version. 

![](https://github.com/xuperchain/XIP/blob/master/pictures/process.png)

### Proposal Collecting
#### 【Goal】
Make xuperchain more perfect and meet the needs of more community developers. This stage will be continuously open to the whole community, and all valuable needs are welcome to put forward.

#### 【How】
The proposal of the community is maintained by the of issue. [XuperChain Feature Request Template](https://github.com/xuperchain/xuperchain/issues/new?assignees=&labels=&template=xuperchain-feature-request-template.md&title=)

#### 【Source】
 There are three main sources of proposals:
 - **XuperChain Working Group**:Xuperchain working group will release some relatively independent and complete proposals to [issue](https://github.com/xuperchain/xuperchain/issues) area regularly.
 - **Community Users**: When using xuperchain, community users can put forward any improvements that need to be made.
 - **External Cooperation Team**: The need from external cooperation developers.

#### 【Output】
 There will be many feature issues in the issue area, which will be reviewed by the issue open source working group and discussed under issue, and managed by [Proposals Project](https://github.com/xuperchain/xuperchain/projects/2).

### Proposal Publishing
#### 【Goal】
The received proposal will be included in the management plan. These proposals will be published and community developers will be recruited to claim. After claiming, follow-up work can be carried out.

#### 【Sponser】
XuperChain Working Group

#### 【How】
XuperChain Working Group Meeting.

#### 【Output】
XuperChain Working Group will publish requirement document.

### Designing 
#### 【Goal】
For the requirement document, the owner of the requirement needs to design.

#### 【Sponser】
The owner of the requirement

#### 【How】
After community developers claim the requirements, they need to carry out detailed design, and the design documents will be published in the proposal repo of xuperchain，[XIP(XuperChain Improvement Proposals)](https://github.com/xuperchain/XIP). Here are the Design Template[XuperChain Technical Design Template](https://github.com/xuperchain/XIP/blob/master/design/TEMPLATE.md). Design document naming specification: IssueNo.-Function.md, for example 888-poa.md. After the design document is released, add the link of the design document to the original requirement issue, and discuss in the issue area.

#### 【Output】
Design document.

### Developing
#### 【Goal】
Complete development.

#### 【Participant】
- **Requirement Owner**: Develop the Requirement.
- **XuperChain Working Group**: Review the PR submitted by the developer.

#### 【Development Specification】
**Branch Strategy**
The development mode of xuperchain is **Develop on master, Release on master**. After completing an iteration cycle, create a new release branch.

**Bugfix Strategy**
Before the branch is created, it only needs to be repaired in the master. After the branch is created, it needs to be repaired in the master and cherry pick to the branch.

**Code Specification**
The code submitted needs to meet the following specifications, which are also the standards referenced by reviewer:

-  Passing gofmt check.
-  Passing golint check [go report](https://goreportcard.com/report/github.com/xuperchain/xuperchain).
-  Passing travis-ci check [travis-ci](https://travis-ci.org/xuperchain/xuperchain)；
-  Good code style, Recommended reading [go guide](https://github.com/xxjwxc/uber_go_guide_cn).
-  Unit test coverage of new code **no less than 65%**.
-  Use cases of the code.

**Review Specification**
The PR can not be merged unless two Member Approved.

### Testing
#### 【Goal】
Guarantee project quality.

#### 【Participant】
XuperChain Working Group.

#### 【Output】
Publish testing report.

### Release
The community and the internal use the same version for maintenance. The whole version takes about **5 weeks** from the proposal published to complete the test. 

=====

# 中文

## 介绍
XuperChain Improvement Proposals (XIPs) 描述了外部用户或者开发者向XuperChain提出建议和参与工作组工作的流程规范，包括库、工具、协议、客户端API和合约标准等。这些提案在接收之前，会首先进行讨论, 接收后还需要提供相应的详细需求文档和设计文档，然后会进入开发阶段。

本文档描述了XuperChain改进提案的提出、讨论、设计到实现的全流程。

## 流程全景图
![图片]()

## 迭代过程
###  提案收集
#### 【目的】
 让XuperChain更加完善，满足更多社区开发者需求，这个阶段会向全社区持续开放，所有有价值的需求都欢迎提出。
#### 【途径】
 开源社区的需求通过Issue的形式维护起来，提出新的需求，使用 [XuperChain Feature Request Template](https://github.com/xuperchain/xuperchain/issues/new?assignees=&labels=&template=xuperchain-feature-request-template.md&title=)

#### 【来源】
 需求的来源主要有3个：
 - **XuperChain工作组**：XuperChain工作组会定期整理一些比较独立完整的需求到Issue区；
 - **社区用户**：社区用户在使用XuperChain时觉得有任何需要改进的地方都可以通过Issue的方式提出；
 - **外部合作团队**：外部合作开发者合作的需求也通过Issue区维护起来；
#### 【输出】
 Issue区会有很多Feature Issue，这些Issue后续开源工作组会进行review，对有价值的Issue会通过[Proposals Project](https://github.com/xuperchain/xuperchain/projects/2)进行状态管理；
###  提案发布
#### 【目的】
对Accept的Issue，会纳入后续的开源迭代管理计划，这些提案会发布出来并招募社区开发者进行认领，认领后可开展后续的工作。
#### 【发起人】
XuperChain开源工作组
#### 【途径】
XuperChain开源工作组每周会进行一次会议，在会议上进行提案的正式发布。由于Issue也会提前建立起来，感兴趣的朋友们也可以直接认领。

#### 【输出】
XuperChain开源项目组会输出详细的提案文档。

### 设计阶段
#### 【目的】
针对提案文档，提案Owner需要进行技术方案设计，以保证设计上的合理性。
#### 【发起人】
认领提案的开发者
#### 【途径】
社区开发者认领提案后，需要进行详细设计，设计文档发布在XuperChain的提案的仓库中，[XIP(XuperChain Improvement Proposals)](https://github.com/xuperchain/XIP)中，设计文档的模板参见[XuperChain Technical Design Template](https://github.com/xuperchain/XIP/blob/master/design/TEMPLATE.md)。设计文档命名规范：Issue编号-功能点.md，例如 888-poa.md 。设计文档发布后，在原来的提案Issue中添加上该设计文档的链接，并在Issue区进行交流讨论。
#### 【输出】
XIP 仓库下新增该提案的详细设计文档。

###  开发阶段
#### 【目的】
完成提案的开发
#### 【参与人】
- **提案Owner**：开发需求
- **XuperChain开源工作组**：对开发者提交的PR进行Review

#### 【开发规范】
**分支策略：**
XuperChain的开发采取**主干开发，分支发布**的方式，完成一个迭代周期后，新建一个分支。

**Bugfix策略:**
分支建立前，仅需要在master修复即可；分支建立后，需要在master修复并cherry-pick到分支。

**代码规范:**
为了保障代码的质量，XuperChain提交的代码需要满足如下规范，这些规范也是Reviewer参考的标准：

-  代码需要通过gofmt检查；
-  确保项目自动检测的golint得分不下降：[go report](https://goreportcard.com/report/github.com/xuperchain/xuperchain)；
-  代码提交通过CI流程检查：[travis-ci](https://travis-ci.org/xuperchain/xuperchain)；
-  代码的风格符合Go语言的编程规范，推荐阅读：[go guide](https://github.com/xxjwxc/uber_go_guide_cn)；
-  新加代码单测覆盖率**不低于65%**；
-  提交PR时需要附带功能的使用case；

**Review规范：**
所有的PR需要通过至少2个Member Approve后才可能合入。

### 测试阶段
此阶段是内部流程，PR合入后，XuperChain开源工作组QA同学会介入测试。
#### 【目的】
对工程质量进行把控
#### 【参与人】
XuperChain工作组QA同学

#### 【输出】
Issue测试报告
### 版本发布
开源社区和内部使用同一个版本进行维护，整个版本从提案确定到测试完毕大约需要**5周**的时间。


