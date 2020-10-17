---
title: 'Lync Server 2013: 주소 유효성 검사'
description: 'Lync Server 2013: 주소 유효성 검사'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547274"
---
# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="288f0-103">Lync Server 2013에서 주소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="288f0-103">Validate addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="288f0-104">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="288f0-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="288f0-105">위치 데이터베이스를 게시 하기 전에 SIP 트렁크 또는 PSTN (공중 전화망) E9-1-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 주소 가이드)에 대해 새 위치를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="288f0-105">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="288f0-106">SIP 트렁크 E9-1-1 서비스 공급자에 대 한 자세한 내용은 [E9-1-1 서비스 공급자 선택에서 Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="288f0-106">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="288f0-107">주소 유효성 검사에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="288f0-107">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="288f0-108">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="288f0-108">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="288f0-109">**CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="288f0-109">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="288f0-110">**CsLisServiceProvider을 제거 합니다.**</span><span class="sxs-lookup"><span data-stu-id="288f0-110">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="288f0-111">**Test-csliscivicaddress**</span><span class="sxs-lookup"><span data-stu-id="288f0-111">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="288f0-112">**Test-csliscivicaddress**</span><span class="sxs-lookup"><span data-stu-id="288f0-112">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="288f0-113">위치 데이터베이스에 있는 주소를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="288f0-113">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="288f0-114">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="288f0-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="288f0-115">다음 cmdlet를 실행 하 여 응급 서비스 공급자 연결을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="288f0-115">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="288f0-116">다음 cmdlet를 실행 하 여 위치 데이터베이스의 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="288f0-116">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="288f0-117">**Test-csliscivicaddress** cmdlet을 사용 하 여 개별 주소를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="288f0-117">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

