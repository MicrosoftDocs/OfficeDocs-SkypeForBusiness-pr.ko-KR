---
title: 영구 채팅 서버를 비즈니스용 Skype 서버 2015 토폴로지에 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: '요약: 이 항목을 읽고 영구 채팅 서버를 비즈니스용 Skype 서버 2015 토폴로지에 추가하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 3b0f3ca57af4b9bf53125e38e1aa3005099b5b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825108"
---
# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a><span data-ttu-id="034e4-103">영구 채팅 서버를 비즈니스용 Skype 서버 2015 토폴로지에 추가</span><span class="sxs-lookup"><span data-stu-id="034e4-103">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>
 
<span data-ttu-id="034e4-104">**요약:** 이 항목을 읽고 영구 채팅 서버를 비즈니스용 Skype 서버 2015 토폴로지에 추가하는 방법을 배워 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-104">**Summary:** Read this topic to learn how to add Persistent Chat Server to your Skype for Business Server 2015 topology.</span></span>
  
<span data-ttu-id="034e4-105">영구 채팅 서버를 배포할 각 서버에 선행 구성 소프트웨어가 설치되면 토폴로지 작성기에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-105">After you install the prerequisite software on each server on which you plan to deploy Persistent Chat Server, you use Topology Builder to:</span></span> 
  
- <span data-ttu-id="034e4-106">영구 채팅 서버를 포함하게 토폴로지 업데이트</span><span class="sxs-lookup"><span data-stu-id="034e4-106">Update your topology to include Persistent Chat Server</span></span>
    
- <span data-ttu-id="034e4-107">업데이트된 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="034e4-107">Publish the updated topology</span></span>
    
> [!NOTE] 
> <span data-ttu-id="034e4-108">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="034e4-109">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="034e4-110">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="034e4-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="034e4-111">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="update-your-topology-to-include-persistent-chat-server"></a><span data-ttu-id="034e4-112">영구 채팅 서버를 포함하게 토폴로지 업데이트</span><span class="sxs-lookup"><span data-stu-id="034e4-112">Update your topology to include Persistent Chat Server</span></span>

<span data-ttu-id="034e4-113">재해 복구 구성 없이 단일 영구 채팅 서버 풀을 설치하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-113">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="034e4-114">고가용성 및 재해 복구를 위해 확장된 영구 채팅 서버 풀을 구성하는 내용은 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)영구 채팅 서버에 대한 고가용성 및 재해 복구 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="034e4-114">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span>
  
<span data-ttu-id="034e4-115">여러 영구 채팅 서버 풀을 배포하기 위해 각 풀에 대해 동일한 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-115">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>
  
1. <span data-ttu-id="034e4-116">비즈니스용 Skype 서버를 실행하는 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 로컬 Users 그룹의 구성원인 계정(또는 동등한 사용자 권한을 가지는 계정)을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-116">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="034e4-117">로컬 Users 그룹의 구성원인 계정을 사용하여 토폴로지 정의 그러나 비즈니스용 Skype 서버를 설치하는 데 필요한 토폴로지 게시를 위해서는 Domain **Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원인 계정을 사용하고 영구 채팅 서버 파일 저장소에 사용할 파일 저장소에 대한 모든 권한(읽기, 쓰기 및 수정)을 가진 계정(토폴로지 작성기에서 필요한 DACL을 구성할 수 있도록) 또는 동일한 권한이 있는 계정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-117">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install Skype for Business Server, you must use an account that is a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>
  
2. <span data-ttu-id="034e4-118">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-118">Start Topology Builder.</span></span>
    
3. <span data-ttu-id="034e4-119">콘솔 트리에서 영구 채팅  풀 노드로 이동한 다음 확장하여 비즈니스용 Skype 서버 풀을 선택하거나 노드를 마우스 오른쪽 단추로 클릭하고 새 영구 채팅 풀을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="034e4-119">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Skype for Business Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="034e4-120">풀의 FQDN(정식 도메인 이름)을 정의하고 풀이 단일 서버 풀 또는 다중 서버 풀 배포인지를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-120">You must define the pool's fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="034e4-121">다중 컴퓨터 풀 또는 **단일** 컴퓨터 **풀을 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="034e4-121">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="034e4-122">영구 채팅 서버 풀에 프런트 엔드 서버가 두 개 이상 있는 경우 이전을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="034e4-122">Choose the former if you are planning to have more than one Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="034e4-123">단일 컴퓨터 풀을 만든 후 나중에 서버를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-123">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="034e4-124">다중 컴퓨터 풀을 선택하는 경우 풀을 구성하는 개별 프런트 엔드 서버의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-124">If you choose a multiple computer pool, enter the names of the individual Front End Servers that comprise the pool.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="034e4-125">Standard Edition 서버에 영구 채팅 서버 역할을 설치하는 경우 FQDN은 Standard Edition 서버의 FQDN과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-125">If the Persistent Chat Server role is being installed on a Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span> 
  
4. <span data-ttu-id="034e4-126">영구 **채팅** 서버 풀에 대한 간단한 표시 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-126">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="034e4-127">표시 이름은 사용자 지정 클라이언트에서 사용할 수 있으며, 특히 채팅방을 차별화하기 위한 영구 채팅 서버 풀이 여러 개 있는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-127">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools to differentiate rooms.</span></span>
    
5. <span data-ttu-id="034e4-128">영구 채팅 서버에서 비즈니스용 Skype 서버 프런트 엔드 서버와 통신하는 데 사용하는 포트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-128">Define the port used by the Persistent Chat Server to communicate with Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="034e4-129">기본 포트는 5041입니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-129">The default port is 5041.</span></span>
    
6. <span data-ttu-id="034e4-130">조직에 준수 지원이 필요한 경우에는 **준수 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-130">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="034e4-131">선택한 경우 영구 채팅 서버 프런트 엔드 서버와 동일한 컴퓨터에 영구 채팅 서버 준수 서비스가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-131">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="034e4-132">나중에 영구 채팅 서버 준수를 위해 SQL Server 백 엔드 서버를 선택하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-132">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>
    
7. <span data-ttu-id="034e4-133">영구 채팅 서버 풀에 대한 사이트 연결성을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-133">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="034e4-134">사이트 **\<SiteName\> 확인란의** 기본 풀로 이  풀을 선택하거나 모든 사이트의 경우 이 풀을 기본값으로 사용하여 이 영구 채팅 서버 풀을 현재 사이트 또는 모든 사이트의 기본 풀로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-134">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="034e4-135">비즈니스용 Skype 클라이언트를 사용하여 채팅방을 만들고 관리하는 경우 채팅방 만들기 및 관리 환경이 채팅방 만들기 및 관리 작업을 해당 풀로 라우팅할 수 있도록 사용자의 사이트와 연결된 기본 풀이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-135">When the Skype for Business client is used to create and manage rooms, the default pool associated with the user's site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="034e4-136">이는 여러 영구 채팅 서버 풀을 배포하고 영구 채팅 서버의 채팅방 만들기 및 관리 기능을 사용하려는 경우만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-136">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="034e4-137">영구 채팅 서버 SDK(소프트웨어 개발 키트)를 사용하여 채팅방 만들기 및 관리 기능을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-137">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span> 
  
8. <span data-ttu-id="034e4-138">다음 SQL 수행하여 영구 채팅 서버 백 엔드(채팅방 콘텐츠가 저장되는 **위치)에** 대한 웹 저장소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-138">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
   - <span data-ttu-id="034e4-139">기존 SQL Server 저장소를 사용하려면 드롭다운 목록에서 사용할 SQL Server 저장소의 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-139">To use an existing SQL Server store, in the drop-down list, click the name of the SQL Server store that you want to use.</span></span>
    
   - <span data-ttu-id="034e4-140">새 SQL Server 지정하려면 새로하기를 클릭하고 새 SQL **저장소 정의에서** 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="034e4-140">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
   - <span data-ttu-id="034e4-141">FQDN을 SQL Server 새 데이터베이스를 만들 SQL Server **FQDN을** SQL Server 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-141">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
   - <span data-ttu-id="034e4-142">기본 인스턴스를 사용하려는 경우 **기본 인스턴스** 를 선택하고, 다른 인스턴스를 지정하려면 **명명된 인스턴스** 를 선택해서 사용하려는 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-142">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="034e4-143">재해 복구를 위해 SQL Server 백업 데이터베이스를 구성하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)영구 채팅 서버에 대해 고가용성 및 재해 복구 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="034e4-143">For details about how to configure SQL Server backup databases for disaster recovery, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
9. <span data-ttu-id="034e4-144">준수를 SQL Server 준수 저장소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-144">Define the SQL Server compliance store if you enabled Compliance.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="034e4-145">영구 채팅 서버 SQL Server 및 영구 채팅 서버 준수 데이터베이스에 대해 고가용성을 위해 미러를 구성하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)영구 채팅 서버에 대한 고가용성 및 재해 복구 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="034e4-145">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md).</span></span> 
  
10. <span data-ttu-id="034e4-146">파일 저장소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-146">Define the file store.</span></span> <span data-ttu-id="034e4-147">파일 저장소는 파일 저장소에 업로드된 파일의 복사본이 저장되는 폴더입니다(예: 채팅방에 게시된 첨부 파일 저장).</span><span class="sxs-lookup"><span data-stu-id="034e4-147">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="034e4-148">다중 서버 영구 채팅 서버 토폴로지의 경우 이 경로는 UNC(범용 이름 규칙) 경로가 되어야 합니다. 단일 서버 영구 채팅 서버 토폴로지의 경우 로컬 파일 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-148">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="034e4-149">기존 파일 저장소를 사용하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-149">To use an existing file store, perform the following steps:</span></span>
    
    - <span data-ttu-id="034e4-150">파일 **서버 FQDN에서** 새 파일 저장소를 만들 컴퓨터의 FQDN을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-150">In **File Server FQDN**, specify the FQDN of the machine on which you want to create the new file store.</span></span>
    
    - <span data-ttu-id="034e4-151">**파일 공유** 에 사용하려는 파일 공유를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-151">In **File Share**, specify the file store that you want to use.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="034e4-152">파일 저장소를 만들기 전에 토폴로지 작성기에서 파일 저장소를 정의할 수 있지만 토폴로지 게시 전에 정의한 정의된 위치에 파일 저장소를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-152">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span> <span data-ttu-id="034e4-153">파일 저장소가 없는 경우 토폴로지 게시 시도가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-153">If the file store doesn't already exist, attempts to publish the topology will fail.</span></span> 
  
11. <span data-ttu-id="034e4-154">이 영구 채팅 서버 풀의 다음 홉으로 사용할 프런트 엔드 서버 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-154">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="034e4-155">영구 채팅 서버 요청을 이 풀로 라우팅할 수 있는 프런트 엔드 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-155">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>
    
12. <span data-ttu-id="034e4-156">구성을 저장하려면 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-156">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="034e4-157">영구 채팅 서버 풀은 토폴로지 작성기에서 특정 풀 설정과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-157">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="034e4-158">영구 채팅 서버를 추가한 업데이트된 토폴로지 게시는 업데이트된 토폴로지 게시를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="034e4-158">To publish your updated topology to which you've added Persistent Chat Server, see Publish the updated topology.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="034e4-159">토폴로지 작성기가 이미 열려 있는 경우 업데이트된 토폴로지 게시의 3단계로 진행하여 업데이트된 토폴로지 게시를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-159">With Topology Builder already open, you can proceed to step 3 in Publish the updated topology to begin publishing your updated topology.</span></span> 
  
## <a name="publish-the-updated-topology"></a><span data-ttu-id="034e4-160">업데이트된 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="034e4-160">Publish the updated topology</span></span>
<span data-ttu-id="034e4-161"><a name="BKMK_PublishTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="034e4-161"><a name="BKMK_PublishTopology"> </a></span></span>

<span data-ttu-id="034e4-162">토폴로지 작성기에서 토폴로지 업데이트 후 토폴로지가 중앙 관리 저장소에 게시되어야 비즈니스용 Skype 서버를 구성하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-162">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Skype for Business Server.</span></span> <span data-ttu-id="034e4-163">모든 서버가 토폴로지 및 기타 구성 변경 내용과 동기화되도록 데이터의 읽기 전용 복사본이 토폴로지의 모든 서버에 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-163">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>
  
<span data-ttu-id="034e4-164">토폴로지 게시 전에 영구 채팅 서버용 데이터베이스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-164">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="034e4-165">토폴로지 작성기에서 작업 및  데이터베이스 설치를 선택하여 **데이터베이스를 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="034e4-165">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>
  
1. <span data-ttu-id="034e4-166">비즈니스용 Skype 서버를 실행하는 컴퓨터 또는 비즈니스용 Skype 서버 관리 도구가 설치된 컴퓨터에서 **Domain Admins** 그룹과 **RTCUniversalServerAdmins** 그룹의 구성원인 계정 및 영구 채팅 서버 파일 저장소에 사용할 파일 저장소에 대한 모든 권한(읽기, 쓰기 및 수정)을 가진 계정(토폴로지 작성기에서 필요한 DACL(사용자 지정 액세스 제어 목록)을 구성할 수 있도록) 또는 동등한 사용자 권한이 있는 계정을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-166">On a computer that is running Skype for Business Server or on which the Skype for Business Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>
    
2. <span data-ttu-id="034e4-167">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-167">Start Topology Builder.</span></span> <span data-ttu-id="034e4-168">로컬로 **저장한** 경우 로컬 파일에서 토폴로지 열기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-168">Select **Open Topology from a local file** if you saved it locally.</span></span>
    
3. <span data-ttu-id="034e4-169">콘솔 트리에서 비즈니스용 **Skype 서버 2015를** 마우스 오른쪽 단추로 클릭한 다음 토폴로지 **게시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="034e4-169">In the console tree, right-click **Skype for Business Server 2015**, and then click **Publish Topology**.</span></span>
    
4. <span data-ttu-id="034e4-170">**토폴로지 게시** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-170">On the **Publish the topology** page, click **Next**.</span></span>
    
5. <span data-ttu-id="034e4-171">**게시 마법사 완료** 페이지에서 토폴로지가 게시되었는지 확인하고 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="034e4-171">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    

