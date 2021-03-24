---
title: 모니터링할 비즈니스용 Skype 서버 컴퓨터 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: '요약: 모니터링할 비즈니스용 Skype 서버 2015 컴퓨터에 Operations Manager 에이전트 파일을 설치하고 System Center 프록시 역할을 하도록 컴퓨터를 구성합니다.'
ms.openlocfilehash: bb4dc64a1c04bbef1b6cb0e391fc27568edfef43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111684"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="0684a-103">모니터링할 비즈니스용 Skype 서버 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="0684a-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="0684a-104">**요약:** 모니터링할 비즈니스용 Skype 서버 2015 컴퓨터에 Operations Manager 에이전트 파일을 설치하고 System Center 프록시 역할을 하도록 컴퓨터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2015 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="0684a-105">모니터링할 각 비즈니스용 Skype 서버 2015 컴퓨터는 해당 존재를 관리 서버에 자체 보고할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-105">Each Skype for Business Server 2015 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="0684a-106">이 프로세스를 사용하도록 설정하려면 모니터링할 각 컴퓨터에 Operations Manager 에이전트 파일을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="0684a-107">에이전트 파일을 설치한 후 System Center 프록시 역할을 하도록 컴퓨터를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="0684a-108">이러한 절차를 수행하기 전에 먼저 이러한 컴퓨터에 비즈니스용 Skype 서버를 설치하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="0684a-109">경계 네트워크 외부에 위치한 감시자 노드에 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="0684a-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="0684a-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="0684a-110"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="0684a-111">경계 네트워크(예: 비즈니스용 Skype 서버 에지 서버) 또는 엔터프라이즈 외부(예: 외부 가상 트랜잭션 감시자 노드) 또는 Active Directory 트러스트 경계를 통해 실행되는 System Center Operations Manager 에이전트는 System Center Operations Manager 게이트웨이 서버를 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="0684a-112">이 서버 역할을 사용하면 루트 관리 서버와 트러스트 관계가 없는 에이전트가 경고를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="0684a-113">자세한 내용은 [Managing Gateway Servers in Operations Manager 2012를 참조합니다.](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12))</span><span class="sxs-lookup"><span data-stu-id="0684a-113">For details, see [Managing Gateway Servers in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12)).</span></span>

<span data-ttu-id="0684a-114">이러한 위치 중 하나에 에이전트를 배포하는 경우 감시자 노드가 System Center Operations Manager로 알림을 보낼 수 있도록 하는 인증서를 요청하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="0684a-115">이 프로세스를 간소화하기 위해 Operations Manager 팀은 감시자 노드 컴퓨터에 올바른 유형의 인증서를 요청하고 설치할 수 있게 해주는 유틸리티 집합을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="0684a-116">자세한 내용을 보고 이러한 유틸리티를 다운로드하려면 인증서 생성 마법사를 통해 도메인에 가입되지 않은 에이전트에 대한 인증서 [얻기를 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="0684a-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="0684a-117">Operation Manager Agent 파일 설치</span><span class="sxs-lookup"><span data-stu-id="0684a-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="0684a-118">System Center 설치 미디어에서 를 두 **번Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="0684a-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="0684a-119">System Center Operation Manager 설치 마법사에서 Install Agent under Optional Installations에서 **Operations Manager Agent** 설치를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="0684a-120">System Center 설치 마법사의 System Center Operations Manager 설치 시작 마법사 페이지에서 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0684a-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="0684a-121">대상 폴더 페이지에서 Operations Manager 에이전트 파일이 설치될 폴더를 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0684a-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="0684a-122">관리 그룹 구성 페이지에서 관리 그룹 **정보 지정을 선택하고** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0684a-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="0684a-123">관리 그룹 구성 페이지의 **관리 그룹 이름** 상자에 Operations Manager 관리 그룹의 이름을 입력하고 **관리 서버** 상자에 Operations Manager 서버의 이름(예: atl-scom-001)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="0684a-124">Operations Manager에서 사용하는 포트 번호를 변경한 경우 관리 서버 포트 상자에 새 포트 번호를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="0684a-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="0684a-125">그렇지 않으면 포트를 기본값인 5723으로 그대로 두고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0684a-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="0684a-126">에이전트 작업 계정 페이지에서 로컬 시스템을 **선택하고** 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0684a-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="0684a-127">Microsoft 업데이트 페이지에서 Microsoft 업데이트를 사용하지 않습니다.를 선택하고 **다음** 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0684a-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="0684a-128">설치 준비 완료 페이지에서 **설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="0684a-129">System Center Operations Manager 설치 마법사 완료 중(Completing the System Center Operations Manager Setup wizard) 페이지에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="0684a-130">**끝내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-130">Click **Exit**.</span></span>

<span data-ttu-id="0684a-131">이 System Center 2012 시작, 모든 프로그램, System Center   **Operations Manager 2012, Operations** **2012** Manager Shell을 클릭하여 에이전트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="0684a-132">Operations Manager 셸에서 다음 Windows PowerShell 입력한 다음 Enter를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="0684a-133">모든 Operations Manager 에이전트의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="0684a-134">System Center 검색에 참여할 비즈니스용 Skype 서버 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="0684a-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="0684a-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="0684a-135"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="0684a-136">새 비즈니스용 Skype 서버 에이전트가 System Center Operations Manager의 검색 프로세스에 참여하는지 확인하려면 System Center Operations Manager 콘솔이 설치된 각 컴퓨터에서 다음 절차를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="0684a-137">관리 탭에서 **에이전트에서 관리** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="0684a-138">검색 **마법사를 클릭하고** 검색할 컴퓨터의 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="0684a-139">상태 에이전트 서비스를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="0684a-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="0684a-140">서비스를 다시 시작하면 새 컴퓨터 검색이 강제로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="0684a-141">서비스를 다시 시작하지 않는 경우 System Center Operations Manager에서 새 시스템을 검색하기까지 4시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="0684a-142">Operations Manager 이벤트 로그에 기록된 오류 이벤트가 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="0684a-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="0684a-143">에이전트가 푸시된 컴퓨터는 "에이전트 관리" 목록에 표시되고 에이전트가 수동으로 설치된 컴퓨터는 "보류 중인 관리"에 표시되고 컴퓨터 이름을 클릭하고 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="0684a-144">컴퓨터의 이름을 마우스 오른쪽 단추로 클릭하고 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-144">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="0684a-145">속성 대화 상자의 보안 탭에서 **이 에이전트를 프록시로 허용하고 다른 컴퓨터에서 관리되는 개체 검색** 을 선택하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0684a-145">In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>