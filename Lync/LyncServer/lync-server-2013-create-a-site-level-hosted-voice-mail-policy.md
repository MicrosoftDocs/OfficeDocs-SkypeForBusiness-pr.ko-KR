---
title: 'Lync Server 2013: 사이트 수준 호스팅 음성 메일 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="6ac97-102">Lync Server 2013에서 사이트 수준의 호스팅 음성 메일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="6ac97-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ac97-103">_**마지막으로 수정한 주제:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="6ac97-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="6ac97-104">*사이트* 정책은 정책이 정의 된 사이트에 속한 모든 사용자에 게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="6ac97-105">사용자가 호스트 된 Exchange UM 액세스에 대해 구성 되어 있고 사용자 단위 정책이 할당 되지 않은 경우 사이트 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="6ac97-106">사이트 정책을 배포 하지 않은 경우에는 전역 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="6ac97-107">사이트 정책을 구성 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ac97-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="6ac97-108">새로운 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6ac97-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="6ac97-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6ac97-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="6ac97-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6ac97-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="6ac97-111">사이트 호스팅 음성 메일 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6ac97-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="6ac97-112">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6ac97-113">새 CsHostedVoicemailPolicy cmdlet을 실행 하 여 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="6ac97-114">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="6ac97-115">이 예제에서는 사이트 범위를 사용 하 여 호스트 된 음성 메일 정책을 만들고 다음 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="6ac97-116">**Id** 는 범위를 포함 하는 정책에 대 한 고유 식별자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="6ac97-117">사이트 범위 정책에 대해 id 매개 변수 값을 형식 `site:` \* \<이름\>\*(예:)으로 지정 해야 합니다. `site:Redmond`</span><span class="sxs-lookup"><span data-stu-id="6ac97-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="6ac97-118">**대상** 호스트 된 Exchange UM 서비스의 FQDN (정규화 된 도메인 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="6ac97-119">이 매개 변수는 선택 사항 이지만, 사용자가 호스트 된 음성 메일을 사용 하도록 설정 하려고 하면 사용자의 할당 된 정책에 대상 값이 없는 경우에는 enable이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="6ac97-120">**설명은** 정책에 대 한 선택적 설명 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="6ac97-121">**조직** 홈 Lync Server 2013 사용자에 해당 하는 Exchange 테 넌 트의 쉼표로 구분 된 목록을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="6ac97-122">각 테 넌 트는 호스팅된 Exchange UM 서비스에서 해당 테 넌 트의 FQDN으로 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac97-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

