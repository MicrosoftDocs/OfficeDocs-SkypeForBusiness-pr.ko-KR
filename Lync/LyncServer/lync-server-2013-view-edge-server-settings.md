---
title: 'Lync Server 2013: Edge 서버 설정 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaab70f2f6d651d6446aaa4a569277494b7a9ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="6dd3d-102">Lync Server 2013의 Edge 서버 설정 보기</span><span class="sxs-lookup"><span data-stu-id="6dd3d-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dd3d-103">_**마지막으로 수정한 주제:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="6dd3d-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="6dd3d-104">모든 변경 내용이 정의 된 변경 제어 절차에 따라 문서화 되었는지 확인할 수 있도록 구성 관리 데이터베이스의 데이터에 대해 일반 Edge 서버 구성을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="6dd3d-105">추가 검사에는 다음 섹션에서 설명 하는 항목이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="6dd3d-106">허용 및 차단 목록 확인</span><span class="sxs-lookup"><span data-stu-id="6dd3d-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="6dd3d-107">페더레이션 도메인의 SIP URI "허용" 및 "차단" 목록을 확인 하 여 나열 된 네임 스페이스가 여전히 유효한 지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="6dd3d-108">Windows PowerShell을 사용 하 여 허용 및 차단 된 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="6dd3d-109">허용 된 도메인 목록의 도메인을 검토 하려면 다음 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="6dd3d-110">이 명령은 허용 된 도메인 목록의 도메인에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="6dd3d-111">Id: contoso.com</span><span class="sxs-lookup"><span data-stu-id="6dd3d-111">Identity : contoso.com</span></span>

<span data-ttu-id="6dd3d-112">도메인: contoso.com</span><span class="sxs-lookup"><span data-stu-id="6dd3d-112">Domain : contoso.com</span></span>

<span data-ttu-id="6dd3d-113">ProxyFqdn:</span><span class="sxs-lookup"><span data-stu-id="6dd3d-113">ProxyFqdn :</span></span>

<span data-ttu-id="6dd3d-114">댓글을</span><span class="sxs-lookup"><span data-stu-id="6dd3d-114">Comment :</span></span>

<span data-ttu-id="6dd3d-115">MarkForMonitoring: False</span><span class="sxs-lookup"><span data-stu-id="6dd3d-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="6dd3d-116">댓글을</span><span class="sxs-lookup"><span data-stu-id="6dd3d-116">Comment :</span></span>

<span data-ttu-id="6dd3d-117">차단 된 도메인 목록에 있는 도메인을 검토 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="6dd3d-118">그러면 각 차단 된 도메인에 대해 다음과 같은 정보를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="6dd3d-119">Id: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="6dd3d-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="6dd3d-120">도메인: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="6dd3d-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="6dd3d-121">Windows PowerShell을 사용 하 여 허용 된 도메인 목록에 있는 도메인에 연결할 수 있는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="6dd3d-122">예를 들어이 명령은 Edge 서버 (TargetFqdn)와 페더레이션된 도메인 contoso.com 간의 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="6dd3d-123">이 명령은 Edge 서버와 허용 된 도메인 목록에 있는 모든 도메인 간의 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="6dd3d-124">여러 Edge 서버가 동일한 지 확인</span><span class="sxs-lookup"><span data-stu-id="6dd3d-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="6dd3d-125">부하 분산 배열에 Edge 서버를 여러 개 배포 하는 경우에는 배열의 모든 Edge 서버가 같은 방식으로 구성 되어 있는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="6dd3d-126">컴퓨터 관리 스냅인에 대 한 Lync Server 2013 확장의 세부 정보 창에서 Edge 서버에 대 한 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dd3d-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6dd3d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6dd3d-127">See Also</span></span>


[<span data-ttu-id="6dd3d-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="6dd3d-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="6dd3d-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="6dd3d-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="6dd3d-130">테스트-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="6dd3d-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

