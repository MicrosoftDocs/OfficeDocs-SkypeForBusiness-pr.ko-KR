---
title: 'Lync Server 2013: cmdlet을 사용하여 도메인 준비 되돌리기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b03ab3218a1568613731efe60eaa95b05a91ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="d8216-102">Lync Server 2013에 대해 cmdlet을 사용하여 도메인 준비 되돌리기</span><span class="sxs-lookup"><span data-stu-id="d8216-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8216-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="d8216-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="d8216-104">도메인 준비 단계를 취소 하려면 **CsAdDomain** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="d8216-105">Cmdlet을 사용 하 여 도메인 준비를 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="d8216-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="d8216-106">도메인 관리자 그룹의 구성원으로 서 도메인의 모든 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="d8216-107">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d8216-108">런</span><span class="sxs-lookup"><span data-stu-id="d8216-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="d8216-109">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="d8216-110">Force 매개 변수가 있는 경우 도메인에 있는 하나 이상의 프런트 엔드 서버 또는 A/V 회의 서버가 활성화 된 경우에도 도메인 준비를 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="d8216-111">Force 매개 변수가 없는 경우 도메인의 프런트 엔드 서버 또는 A/V 회의 서버가 활성화 되 면 도메인 준비 롤백이 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d8216-112">GlobalSettingsDomainController 매개 변수를 사용 하면 전역 설정이 저장 되는 위치를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="d8216-113">설정이 시스템 컨테이너에 저장 된 경우 (구성 컨테이너에 전역 설정이 마이그레이션되지 않은 업그레이드 배포의 경우), Active Directory 포리스트의 루트에 도메인 컨트롤러를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="d8216-114">전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="d8216-115">이 매개 변수를 지정 하지 않으면 cmdlet은 설정이 구성 컨테이너에 저장 되어 있고 AD&nbsp;DS의 모든 도메인 컨트롤러를 참조 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8216-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d8216-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8216-116">See Also</span></span>


[<span data-ttu-id="d8216-117">Lync Server 2013에 대한 도메인 준비 실행</span><span class="sxs-lookup"><span data-stu-id="d8216-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="d8216-118">Lync Server 2013에 대한 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="d8216-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

