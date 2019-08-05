---
title: 비즈니스용 Skype 서버에서 Edge 배포의 유효성 검사
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '요약: Edge 서버 또는 Edge 서버 풀이 비즈니스용 Skype 서버에서 작동 하는지 확인 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 0c432cba78e97add71bb7c4e21e155f92c9fe66a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197780"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="56d64-103">비즈니스용 Skype 서버에서 Edge 배포의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="56d64-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="56d64-104">**요약:** Edge 서버 또는 Edge 서버 풀이 비즈니스용 Skype 서버에서 작동 하는지 확인 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="56d64-105">Edge 서버 또는 Edge 서버 풀을 배포한 후에는 제대로 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="56d64-106">여기에는 Edge 환경이 내부 서버에 연결 되어 있는지 확인 하는 데 도움이 되는 몇 가지 내용과 외부 사용자가 Edge를 통해 비즈니스용 Skype 서버 환경에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="56d64-107">내부 서버와 Edge 서버 간 연결 확인</span><span class="sxs-lookup"><span data-stu-id="56d64-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="56d64-108">Edge 서버 또는 Edge 서버에서 연결에 대 한 유효성 검사를 자동으로 수행 하는 동안에도 계속 해 서 Windows PowerShell을 사용 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="56d64-109">중앙 관리 저장소가 있는 내부 서버에서 CsManagementStoreReplicationStatus cmdlet을 실행 하거나 비즈니스용 Skype Server Core 구성 요소 (Ocx 점수. msi)가 설치 된 도메인에 연결 된 컴퓨터에 대해 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="56d64-110">이 명령을 실행 하면 복제에 대해 True가 아닌 잘못 된 상태가 제공 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="56d64-111">이러한 경우 CsManagementStoreReplication cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="56d64-112">복제를 완료 하는 데 시간을 제공 하 고 CsManagementStoreReplicationStatus cmdlet을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="56d64-113">외부 사용자에 대 한 연결 확인</span><span class="sxs-lookup"><span data-stu-id="56d64-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="56d64-114">Edge 서버 구성을 확인 하 고 Edge 서버 시나리오에 대 한 올바른 메시지를 보내고 받을 수 있는 기능을 제공 하는 훌륭한 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="56d64-115">[원격 연결 Anaylzer 사이트](https://testconnectivity.microsoft.com/)입니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="56d64-116">이 사이트는 Microsoft 지원에서 관리 하 고 유지 관리 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="56d64-117">이 도구를 사용 하려면 웹 사이트로 이동 하 여 지침에 따라 적절 한 시나리오를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="56d64-118">외부 사용자 연결을 테스트할 때 고려해 야 할 사항</span><span class="sxs-lookup"><span data-stu-id="56d64-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="56d64-119">외부 사용자 액세스에 대 한 모든 테스트에는 조직에서 지 원하는 각 유형의 내부 사용자가 포함 되어야 하며, 여기에는 다음 중 일부 또는 모두가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="56d64-120">하나 이상의 페더레이션 도메인에서 사용자를 테스트 하는 것이 좋습니다 (모든 경우에 해당 합니다).</span><span class="sxs-lookup"><span data-stu-id="56d64-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="56d64-121">익명 사용자.</span><span class="sxs-lookup"><span data-stu-id="56d64-121">Anonymous users.</span></span>
    
- <span data-ttu-id="56d64-122">조직에서 원격으로 비즈니스용 Skype에 로그인 했지만 VPN을 사용 하지 않는 사용자</span><span class="sxs-lookup"><span data-stu-id="56d64-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="56d64-123">이러한 테스트는 Edge 서버가 다음과 같은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="56d64-124">네트워크 외부의 텔넷 클라이언트를 사용 하 여 필요한 포트를 수신 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="56d64-125">예: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="56d64-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="56d64-126">배포에 따라 Edge 서버 또는 Edge 서버 풀에서 사용 중인 포트에서 앞의 테스트를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="56d64-127">정확한 외부 DNS 확인을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="56d64-128">네트워크 외부에서 Edge 서버 또는 Edge 서버 풀의 각 외부 Fqdn에 대해 ping을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="56d64-129">Ping이 실패 하더라도 이전에 할당 한 IP 주소를 비교할 수 있는 IP 주소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56d64-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

