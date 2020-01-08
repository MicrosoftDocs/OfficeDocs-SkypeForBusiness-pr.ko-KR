---
title: 'Lync Server 2013: 사용자 단위 호스팅 음성 메일 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="3b676-102">Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3b676-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b676-103">_**마지막으로 수정한 주제:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="3b676-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="3b676-104">사용자별 *정책은 개별* 사용자, 그룹 및 연락처 개체에만 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="3b676-105">사용자별 정책을 배포 하려면 하나 이상의 사용자, 그룹 또는 연락처 개체에 정책을 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="3b676-106">자세한 내용은 [Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 할당](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b676-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="3b676-107">사용자 단위 호스팅 음성 메일 정책을 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b676-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="3b676-108">새로운 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3b676-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="3b676-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3b676-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="3b676-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="3b676-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="3b676-111">사용자 단위 호스팅 음성 메일 정책을 만들려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="3b676-112">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3b676-113">새 CsHostedVoicemailPolicy cmdlet을 실행 하 여 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="3b676-114">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="3b676-115">앞의 예제에서는 사용자별 범위를 사용 하 여 호스트 된 음성 메일 정책을 만들고 다음 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="3b676-116">**Id** 는 범위를 포함 하는 정책에 대 한 고유 식별자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="3b676-117">사용자별 범위가 있는 정책의 경우이 매개 변수 값은 ExRedmond와 같은 간단한 문자열로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="3b676-118">**대상** 호스트 된 Exchange UM 서비스의 FQDN (정규화 된 도메인 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="3b676-119">이 매개 변수는 선택 사항 이지만, 사용자가 호스트 된 음성 메일을 사용 하도록 설정 하려고 하면 사용자의 할당 된 정책에 대상 값이 없는 경우에는 enable이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="3b676-120">**설명은** 정책에 대 한 선택적 설명 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="3b676-121">**조직** 홈 Lync Server 2013 사용자에 해당 하는 Exchange 테 넌 트의 쉼표로 구분 된 목록을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="3b676-122">각 테 넌 트는 호스팅된 Exchange UM 서비스에서 해당 테 넌 트의 FQDN으로 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b676-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b676-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b676-123">See Also</span></span>


[<span data-ttu-id="3b676-124">Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="3b676-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

