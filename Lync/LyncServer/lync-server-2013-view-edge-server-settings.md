---
title: Lync Server 2013:에 지 서버 설정 보기
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
ms.openlocfilehash: 3c76eb9580c7ee394e0e60e5d0f8cfe38dcae65e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="4b9bf-102">Lync Server 2013의에 지 서버 설정 보기</span><span class="sxs-lookup"><span data-stu-id="4b9bf-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b9bf-103">_**마지막으로 수정 된 항목:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="4b9bf-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="4b9bf-104">일반에 지 서버 구성을 구성 관리 데이터베이스의 데이터에 대해 검토 하 여 모든 변경 내용이 정의 된 변경 제어 절차에 따라 문서화 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="4b9bf-105">추가 검사에는 다음 섹션에서 설명 하는 항목이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="4b9bf-106">허용 및 차단 목록 확인</span><span class="sxs-lookup"><span data-stu-id="4b9bf-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="4b9bf-107">페더레이션 도메인에 대해 SIP URI "허용" 및 "차단" 목록을 확인 하 여 나열 된 네임 스페이스가 여전히 유효한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="4b9bf-108">Windows PowerShell을 사용 하 여 허용 및 차단 된 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="4b9bf-109">허용 도메인 목록에서 도메인을 검토 하려면 다음 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="4b9bf-110">이 명령은 허용 된 도메인 목록에 있는 도메인에 대해 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="4b9bf-111">Id: contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9bf-111">Identity : contoso.com</span></span>

<span data-ttu-id="4b9bf-112">도메인: contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9bf-112">Domain : contoso.com</span></span>

<span data-ttu-id="4b9bf-113">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="4b9bf-113">ProxyFqdn :</span></span>

<span data-ttu-id="4b9bf-114">설명이</span><span class="sxs-lookup"><span data-stu-id="4b9bf-114">Comment :</span></span>

<span data-ttu-id="4b9bf-115">MarkForMonitoring: False</span><span class="sxs-lookup"><span data-stu-id="4b9bf-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="4b9bf-116">설명이</span><span class="sxs-lookup"><span data-stu-id="4b9bf-116">Comment :</span></span>

<span data-ttu-id="4b9bf-117">차단 된 도메인 목록의 도메인을 검토 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="4b9bf-118">그러면 각 차단 된 도메인에 대해 다음과 같은 정보가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="4b9bf-119">Id: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="4b9bf-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="4b9bf-120">도메인: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="4b9bf-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="4b9bf-121">Windows PowerShell을 사용 하면 허용 된 도메인 목록에 있는 도메인에 연결할 수 있는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="4b9bf-122">예를 들어 다음 명령은에 지 서버 (TargetFqdn)와 페더레이션 도메인 contoso.com 간의 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="4b9bf-123">그리고이 명령은 허용 된 도메인 목록에 있는 모든 도메인 및에 지 서버 간의 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="4b9bf-124">여러에 지 서버가 동일 확인</span><span class="sxs-lookup"><span data-stu-id="4b9bf-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="4b9bf-125">부하 분산 된 배열에 여러 개의에 지 서버를 배포 하는 경우에는 배열의 모든에 지 서버가 동일한 방식으로 구성 되었는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="4b9bf-126">컴퓨터 관리 스냅인에 대 한 Lync Server 2013 extension의 세부 정보 창에서에 지 서버에 대 한 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9bf-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b9bf-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b9bf-127">See Also</span></span>


[<span data-ttu-id="4b9bf-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="4b9bf-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="4b9bf-129">Get-csblockeddomain</span><span class="sxs-lookup"><span data-stu-id="4b9bf-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="4b9bf-130">Test-csfederatedpartner</span><span class="sxs-lookup"><span data-stu-id="4b9bf-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

