---
title: 'Lync Server 2013: 공용 지역 전화에 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b792d6ae14ee13fd1d95761d2a0d6b0af7bbdfae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="ebe7c-102">Lync Server 2013에서 공통 지역 전화로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="ebe7c-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebe7c-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ebe7c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ebe7c-104">공용 지역 전화에 대 한 정책을 만든 후 ( [Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)참조) Windows PowerShell 및 해당 **허용 Cs** cmdlet을 사용 하 여 정책을 공통 영역 전화기에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe7c-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="ebe7c-105">이러한 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe7c-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ebe7c-106">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebe7c-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="ebe7c-107">단일 공통 영역 휴대폰에 정책 지정</span><span class="sxs-lookup"><span data-stu-id="ebe7c-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="ebe7c-108">다음 명령을 사용 하 여 사용자 단위 음성 정책 RedmondVoice를 Id 빌드 14 대기실가 있는 공통 영역 전화로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe7c-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="ebe7c-109">여러 공용 지역 전화에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="ebe7c-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="ebe7c-110">이 예제에서는 사용자 단위 음성 정책 RedmondVoice 조직에서 사용 하도록 구성 된 모든 공통 영역 전화에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebe7c-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="ebe7c-111">자세한 내용은 [허용-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebe7c-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ebe7c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebe7c-112">See Also</span></span>


[<span data-ttu-id="ebe7c-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="ebe7c-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

