---
title: 모니터링할 비즈니스용 Skype 서버 컴퓨터 구성
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 모니터링할 비즈니스용 Skype 서버 2019 컴퓨터에 Operations Manager 에이전트 파일을 설치 하 고 System Center 프록시로 작동 하도록 컴퓨터를 구성 합니다.'
ms.openlocfilehash: ae5e1c2ab3d8eb17449c391ea321cfb44272368f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189759"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="9a350-103">모니터링할 비즈니스용 Skype 서버 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="9a350-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="9a350-104">**요약:** 비즈니스용 Skype Server 2019 컴퓨터에 Operations Manager 에이전트 파일을 설치 하 고 시스템 센터 프록시로 작동 하도록 컴퓨터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="9a350-105">모니터링할 각 비즈니스용 Skype Server 2019 컴퓨터는 관리 서버에 대 한 존재를 자체 보고할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="9a350-106">이 프로세스를 사용 하도록 설정 하려면 모니터링할 각 컴퓨터에 Operations Manager 에이전트 파일을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="9a350-107">에이전트 파일을 설치한 후에는 컴퓨터를 System Center 프록시로 작동 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="9a350-108">이러한 절차를 수행 하기 전에 먼저이 컴퓨터에 비즈니스용 Skype 서버를 설치 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="9a350-109">경계 네트워크 외부에 있는 감시자 노드에 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="9a350-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="9a350-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="9a350-110"></span></span>

<span data-ttu-id="9a350-111">경계 네트워크 (예: 비즈니스용 Skype Server Edge Server)에서 실행 되는 System Center Operations Manager 에이전트 (예: 외부 가상 트랜잭션 감시자 노드 등) 또는 Active Directory 신뢰 경계를 넘어 서 작업을 수행 해야 할 수 있습니다. System Center Operations Manager 게이트웨이 서버의 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="9a350-112">이 서버 역할은 루트 관리 서버와 신뢰 관계가 없는 에이전트를 사용 하도록 설정 하 여 알림을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="9a350-113">자세한 내용은 [Operations Manager 2012에서 게이트웨이 서버 관리](https://technet.microsoft.com/en-us/library/hh212823.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a350-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span></span>

<span data-ttu-id="9a350-114">이러한 위치 중 하나에 에이전트를 배포 하는 경우에는 감시자 노드가 System Center Operations Manager에 알림을 보낼 수 있도록 하는 인증서도 요청 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="9a350-115">이 프로세스를 간소화 하기 위해 Operations Manager 팀은 감시자 노드 컴퓨터에서 올바른 형식의 인증서를 요청 하 고 설치할 수 있는 유틸리티 집합을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="9a350-116">이 유틸리티를 다운로드 하는 방법에 대 한 자세한 내용은 [인증서 생성 마법사로 쉽게 만들 수 있는 비도메인 가입 에이전트에 대 한 인증서 가져오기를](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a350-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="9a350-117">Operation Manager 에이전트 파일 설치</span><span class="sxs-lookup"><span data-stu-id="9a350-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="9a350-118">System Center 설정 미디어에서 Setup.exe를 두 번 클릭 **합니다**.</span><span class="sxs-lookup"><span data-stu-id="9a350-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="9a350-119">System Center operations Manager 설치 마법사의 설치 에이전트에서 **Operations Manager 에이전트 설치**(선택적 설치의 경우)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="9a350-120">System Center 설정 마법사의 System Center Operations Manager 설치 마법사 시작 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="9a350-121">대상 폴더 페이지에서 Operations Manager 에이전트 파일을 설치할 폴더를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="9a350-122">관리 그룹 구성 페이지에서 **관리 그룹 정보 지정** 을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="9a350-123">관리 그룹 구성 페이지의 **관리 그룹 이름** 상자에 Operations Manager 관리 그룹의 이름을 입력 한 다음 관리 서버에 operations manager 서버의 호스트 이름 (예: atl-scom-001)을 입력 합니다. \*\* \*\*상자입니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="9a350-124">Operations Manager에 사용 되는 포트 번호를 변경한 경우 **관리 서버 포트** 상자에 새 포트 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="9a350-125">그렇지 않으면 포트를 기본값인 5723으로 두고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="9a350-126">에이전트 작업 계정 페이지에서 **로컬 시스템** 을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="9a350-127">Microsoft 업데이트 페이지에서 **Microsoft 업데이트 사용 안 함을** 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="9a350-128">설치 준비 페이지에서 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="9a350-129">System Center Operations Manager 설치 마법사 완료 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="9a350-130">**끝내기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-130">Click **Exit**.</span></span>

<span data-ttu-id="9a350-131">System Center 2012의 경우 **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **System Center operations manager 2012**을 클릭 하 고 **Operations 2012 Manager Shell**을 클릭 하 여 에이전트가 만들어졌는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="9a350-132">Operations Manager 셸에서 다음 Windows PowerShell 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```
Get-SCOMAgent
```

<span data-ttu-id="9a350-133">모든 Operations Manager 에이전트 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="9a350-134">System Center Discovery에 참가 하도록 비즈니스용 Skype Server 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="9a350-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="9a350-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="9a350-135"></span></span>

<span data-ttu-id="9a350-136">새 비즈니스용 Skype 서버 에이전트가 System Center Operations Manager의 검색 프로세스에 참여 하도록 하려면 System Center Operations Manager 콘솔이 설치 된 각 컴퓨터에서 다음 절차를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="9a350-137">관리 탭에서 **에이전트 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="9a350-138">**검색 마법사** 를 클릭 하 고 컴퓨터를 검색할 마법사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="9a350-139">상태 에이전트 서비스를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="9a350-140">서비스를 다시 부팅 하면 새 컴퓨터를 강제로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="9a350-141">서비스를 다시 부팅 하지 않으면 시스템 센터 Operations Manager에서 새 컴퓨터를 검색 하기 전에 4 시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="9a350-142">Operations Manager 이벤트 로그에 오류 이벤트가 기록 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="9a350-143">에이전트가 성공적으로 푸시된 컴퓨터가 "에이전트 관리" 목록에 표시 되며 수동으로 설치 된 에이전트가 "보류 중인 관리" 아래에 표시 되는 경우 컴퓨터 이름을 클릭 하 고 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="9a350-144">컴퓨터의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-144">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="9a350-145">속성 대화 상자의 보안 탭에서 **이 에이전트가 프록시로 작동할 수 있도록 허용을 선택 하 고 다른 컴퓨터에서 관리 되는 개체를 검색**한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a350-145">In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


