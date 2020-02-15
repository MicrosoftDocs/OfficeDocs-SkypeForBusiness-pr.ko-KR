---
title: 'Lync Server 2013: 사용자별 호스팅된 음성 메일 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055d65fe691d99c8b960ebed088ba47cbcb2f988
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="36453-102">Lync Server 2013에서 사용자별 호스팅 음성 메일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="36453-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36453-103">_**마지막으로 수정 된 항목:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="36453-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="36453-104">*사용자별* 정책은 개별 사용자, 그룹 및 연락처 개체에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36453-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="36453-105">사용자별 정책을 배포하려면 하나 이상의 사용자, 그룹 또는 연락처 개체에 해당 정책을 명시적으로 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36453-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="36453-106">자세한 내용은 [Lync Server 2013에서 사용자별 호스팅 음성 메일 정책 할당](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="36453-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="36453-107">사용자별 호스팅 음성 메일 정책을 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="36453-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="36453-108">Set-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="36453-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="36453-109">Set-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="36453-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="36453-110">Set-cshostedvoicemailpolicy</span><span class="sxs-lookup"><span data-stu-id="36453-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="36453-111">사용자별 호스팅된 음성 메일 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="36453-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="36453-112">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="36453-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="36453-p102">New-CsHostedVoicemailPolicy cmdlet을 실행하여 정책을 만듭니다. 예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="36453-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="36453-115">위의 예제에서는 사용자별 범위가 포함된 호스팅된 음성 메일 정책을 만들고 다음 매개 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="36453-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="36453-p103">**Identity**는 정책의 고유한 식별자를 지정합니다(범위 포함). 사용자별 범위가 포함된 정책의 경우 이 매개 변수 값은 ExRedmond와 같은 단순 문자열로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="36453-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="36453-p104">**Destination**은 호스팅된 Exchange UM 서비스의 FQDN(정규화된 도메인 이름)을 지정합니다. 이 매개 변수는 선택 사항이지만 호스팅된 음성 메일에 대해 사용자를 활성화하려는 경우 사용자에게 할당된 정책에 Destination 값이 없으면 활성화가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="36453-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="36453-120">**Description**은 옵션 매개 변수로, 정책에 대한 설명 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36453-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="36453-121">**조직** 홈 Lync Server 2013 사용자에 해당 하는 쉼표로 구분 된 Exchange 테 넌 트 목록을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36453-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="36453-122">각 테넌트는 호스트된 Exchange UM 서비스에 있는 해당 테넌트의 FQDN으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36453-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36453-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36453-123">See Also</span></span>


[<span data-ttu-id="36453-124">Lync Server 2013에서 사용자별 호스팅 음성 메일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="36453-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

