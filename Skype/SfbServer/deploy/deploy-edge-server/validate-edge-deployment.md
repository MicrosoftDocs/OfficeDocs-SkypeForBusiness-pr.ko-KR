---
title: 비즈니스용 Skype 서버에서 에지 배포 유효성 검사
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '요약: 에지 서버 또는 에지 서버 풀의 배포가 비즈니스용 Skype 서버에서 작동하고 있는지 확인하는 방법을 설명합니다.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804358"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="8bb17-103">비즈니스용 Skype 서버에서 에지 배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8bb17-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="8bb17-104">**요약:** 에지 서버 또는 에지 서버 풀의 배포가 비즈니스용 Skype 서버에서 작동하고 있는지 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="8bb17-105">에지 서버 또는 에지 서버 풀을 배포한 후 제대로 작동하고 있는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="8bb17-106">다음은 에지 환경이 내부 서버에 연결되고 외부 사용자가 에지를 통해 비즈니스용 Skype 서버 환경에 연결할 수 있는지 확인하는 데 도움이 될 수 있는 몇 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="8bb17-107">내부 서버와 에지 서버 간의 연결 확인</span><span class="sxs-lookup"><span data-stu-id="8bb17-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="8bb17-108">에지 서버가 설치될 때 연결 유효성 검사가 에지 서버 또는 에지 서버 풀에서 자동으로 수행되는 동안 에지 서버와 함께 이 확인을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bb17-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="8bb17-109">중앙 관리 Get-CsManagementStoreReplicationStatus 있는 내부 서버 또는 비즈니스용 Skype 서버 핵심 구성 요소(OcsCore.msi)가 설치된 도메인에 가입된 컴퓨터에서 OcsCore.msi cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="8bb17-110">이 명령을 실행하면 복제에 대해 True가 아닌 False 상태가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="8bb17-111">이 경우 cmdlet을 Invoke-CsManagementStoreReplication 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="8bb17-112">복제를 완료할 시간을 주었다가 다시 Get-CsManagementStoreReplicationStatus 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="8bb17-113">외부 사용자에 대한 연결 확인</span><span class="sxs-lookup"><span data-stu-id="8bb17-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="8bb17-114">에지 서버 구성을 확인하고 에지 서버 시나리오에 대한 올바른 메시지를 연결, 보내고 받는 기능을 확인할 수 있는 훌륭한 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="8bb17-115">원격 연결 [Anaylzer 사이트입니다.](https://testconnectivity.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="8bb17-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="8bb17-116">이 사이트는 Microsoft 지원에서 관리 및 유지 관리되는 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="8bb17-117">이 도구를 사용하려면 웹 사이트를 찾아 지침에 따라 적합한 시나리오를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="8bb17-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="8bb17-118">외부 사용자 연결을 테스트할 때 고려해야 할 것</span><span class="sxs-lookup"><span data-stu-id="8bb17-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="8bb17-119">외부 사용자 액세스 테스트에는 조직에서 지원하는 각 내부 사용자 유형(다음 중 하나 또는 모두 포함)이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="8bb17-120">하나 이상의 페더타 도메인의 사용자(모두 테스트하는 것이 좋습니다).</span><span class="sxs-lookup"><span data-stu-id="8bb17-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="8bb17-121">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="8bb17-121">Anonymous users.</span></span>
    
- <span data-ttu-id="8bb17-122">원격으로 비즈니스용 Skype에 로그인되어 있지만 VPN을 사용하지 않는 조직의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="8bb17-123">이러한 테스트에서는 에지 서버가 다음인지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="8bb17-124">네트워크 외부의 텔넷 클라이언트를 사용하여 필요한 포트를 수신 대기하는지 여부</span><span class="sxs-lookup"><span data-stu-id="8bb17-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="8bb17-125">예: 텔넷 sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="8bb17-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="8bb17-126">배포에 따라 에지 서버 또는 에지 서버 풀에서 사용 하는 포트에 대해 위의 테스트를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="8bb17-127">정확한 외부 DNS 확인을 수행하는지 여부</span><span class="sxs-lookup"><span data-stu-id="8bb17-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="8bb17-128">네트워크 외부에서 에지 서버 또는 에지 서버 풀의 각 외부 FQDNS에 ping합니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="8bb17-129">ping이 실패하는 경우에도 이전에 할당한 IP 주소를 비교할 수 있는 IP 주소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bb17-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

