---
title: 'Lync Server 2013: 음성 메일 이스케이프 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 131b36b87a3d930662cdd863dd4ebc1d0d69163e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="7a24a-102">Lync Server 2013에서 음성 메일 이스케이프 구성</span><span class="sxs-lookup"><span data-stu-id="7a24a-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a24a-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7a24a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7a24a-104">사용자가 휴대폰에 대한 동시 전화 신호 울림 기능을 구성한 경우 휴대폰이 꺼져 있거나, 배터리가 방전되었거나, 망 범위를 벗어나 있는 경우 일반적으로 발신자가 사용자의 개인 음성 메일로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="7a24a-105">Lync Server 2013를 사용 하는 경우 사용자는 회사 음성 메일 시스템으로 라우팅되는 비즈니스 관련 통화가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="7a24a-106">특히 타이머를 구성할 수 있으며, 통화를 정의 된 시간 범위 내에 반송파의 음성 메일에서 응답 하는 경우, Lync Server는 반송파의 음성 메일 시스템과 사용자의 개인 음성 사서함에서 연결을 끊습니다. 회사 시스템의 끝점이 계속 해 서 울립니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="7a24a-107">이렇게 해서 발신자가 자동으로 사용자의 회사 음성 메일로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="7a24a-108">다음 매개 변수를 사용 하 여 음성 정책 수준에서 Lync Server 관리 셸 cmdlet **set-csvoicepolicy**을 사용 하 여이 구성을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="7a24a-109">음성 메일 이스케이프를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="7a24a-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="7a24a-110">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7a24a-111">**Set-CsVoicePolicy**에 다음 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="7a24a-112">**EnableVoicemailEscapeTimer** - 이스케이프 타이머를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="7a24a-p102">**PSTNVoicemailEscapeTimer** - 시간 제한 값을 밀리초 단위로 지정합니다. 기본값은 1500밀리초이며 0~8000밀리초 범위에서 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a24a-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="7a24a-115">예제</span><span class="sxs-lookup"><span data-stu-id="7a24a-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a24a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a24a-116">See Also</span></span>


[<span data-ttu-id="7a24a-117">Lync Server 2013에서 호출 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="7a24a-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

