# XuperChain Improvement Proposals(XIPs)

## Introduction
XuperChain Improvement Proposals (XIPs) describe standards for the XuperChain platform which external developer participated in, including libraries, tools, protocols, client APIs, and contract standards. This changes need to be first discussed, and sometimes formally documented, before they can be implemented.

This document describes the process for proposing, documenting, and implementing changes to the XuperChain project.

## The Complete Process
The following process is the process for reviewing a proposal, reaching
a decision about whether to accept or decline the proposal, designing, developing, testing and released with xuperchain version. 

![]()

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