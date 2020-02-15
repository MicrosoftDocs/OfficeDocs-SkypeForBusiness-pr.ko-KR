---
title: Exchange 통합 메시징 대화 상대 개체 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c02e391fa66084a27e3790ccaf42753bcaeaa16
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="4303b-102">Exchange 통합 메시징 대화 상대 개체 이동</span><span class="sxs-lookup"><span data-stu-id="4303b-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4303b-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4303b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4303b-104">자동 전화 교환 (AA) 및 SA (구독자 액세스) 연락처 개체를 새 Lync Server 2013 배포로 마이그레이션하려면 먼저 이전 Office Communications Server 2007 R2 배포의 개체를 **Get-csexumcontact** 및 **Move-csexumcontact** cmdlet을 사용 하 여 Lync Server 2013 배포로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="4303b-105">Exchange 서버에서 **Exchucutil.ps1** Windows PowerShell 스크립트를 실행 하 여 새로 배포 된 Lync 풀에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="4303b-106">Unified Messaging IP 게이트웨이에 개체 추가</span><span class="sxs-lookup"><span data-stu-id="4303b-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="4303b-107">Unified Messaging 헌트 그룹에 개체 추가</span><span class="sxs-lookup"><span data-stu-id="4303b-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4303b-p102"><STRONG>Get-CsExUmContact</STRONG> 및 <STRONG>Move-CsExUmContact</STRONG> cmdlet을 사용하려면 RTCUniversalUserAdmins 그룹의 구성원이어야 하며 대화 상대 개체가 저장된 OU에 대한 OU(조직 구성 단위) 권한이 있어야 합니다. OU 권한은 <STRONG>Grant-OUPermission</STRONG> cmdlet을 사용하여 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-p102">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="4303b-110">Lync Server 관리 셸을 사용하여 대화 상대 개체를 이동하려면</span><span class="sxs-lookup"><span data-stu-id="4303b-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="4303b-111">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="4303b-112">Exchange UM에 등록 된 각 풀 (여기서 pool1.contoso.net은 Office Communications Server 2007 R2 배포의 풀이 고 pool2.contoso.net는 Lync Server 2013 배포의 풀)에 명령줄에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="4303b-113">대화 상대 개체가 이동되었는지 확인하려면 **Get-CsExumContact** cmdlet을 실행하고 **RegistrarPool**이 이제 새 풀을 가리키는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="4303b-114">ExchUCUtil Windows PowerShell 스크립트를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="4303b-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="4303b-115">Exchange 조직 관리자 권한이 있는 사용자로 Exchange UM 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="4303b-116">Exchucutil.ps1 Windows PowerShell 스크립트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="4303b-117">Exchange 2007에서 Exchucutil.ps1는 **%\\Program Files%\\Microsoft Exchange Server\\스크립트\\exchucutil.ps1** 에 있습니다. ps1</span><span class="sxs-lookup"><span data-stu-id="4303b-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="4303b-118">Exchange 2010에서 Exchucutil.ps1는 **%\\Program Files% Microsoft\\Exchange Server\\v 14\\Scripts\\exchucutil.ps1. ps1** 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="4303b-119">Exchange가 단일 포리스트에 배포된 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="4303b-120">또는 Exchange가 여러 포리스트에 배포된 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="4303b-121">여기서 포리스트 FQDN은 Lync Server 2013이 배포 되는 포리스트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4303b-122">exchucutil.ps1을 실행한 <EM>후</EM><STRONG>Lync Server 프런트 엔드</STRONG> 서비스(rtcsrv.exe)를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="4303b-123">그렇지 않으면 Lync Server 2013이 토폴로지에서 통합 메시징을 검색 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4303b-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

