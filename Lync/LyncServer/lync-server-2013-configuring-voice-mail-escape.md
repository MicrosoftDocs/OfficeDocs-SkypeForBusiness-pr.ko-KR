---
title: 'Lync Server 2013: 음성 메일 이스케이프 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f08e12b97c51d68b4b08d10692802cb035ce8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="507d1-102">Lync Server 2013에서 음성 메일 esc 구성</span><span class="sxs-lookup"><span data-stu-id="507d1-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="507d1-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="507d1-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="507d1-104">사용자가 휴대폰으로 동시 신호음을 구성 하는 경우, 휴대 전화를 끄거나, 배터리 전원이 꺼져 있거나, 범위를 벗어나면 일반적으로 발신자가 사용자의 개인 음성 메일로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="507d1-105">Lync Server 2013을 사용 하면 사용자가 회사 음성 메일 시스템으로 라우팅되는 비즈니스 관련 통화를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="507d1-106">특히 타이머를 구성할 수 있으며, 통화를 지정 된 시간 범위 내에서 반송파의 음성 메일을 통해 수신 되는 경우, Lync Server는 해당 통신 회사의 음성 메일 시스템 (및 사용자의 개인 음성 메일)과 사용자의 남은 상태를 연결 해제 합니다. 회사 시스템의 끝점은 계속 해 서 울립니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="507d1-107">이 방법으로 발신자는 자동으로 사용자의 회사 음성 메일로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="507d1-108">이 구성은 다음 매개 변수를 사용 하 여 음성 정책 수준에서 Lync Server 관리 셸 cmdlet, **Set-CsVoicePolicy**를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="507d1-109">음성 메일 esc를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="507d1-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="507d1-110">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="507d1-111">다음 매개 변수를 **CsVoicePolicy**로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="507d1-112">**EnableVoicemailEscapeTimer** -이탈 타이머를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="507d1-113">**PSTNVoicemailEscapeTimer** -제한 시간 값 (밀리초)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-113">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="507d1-114">기본값은 1500 밀리초 이며, 값의 범위는 0 밀리초 ~ 8000 밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="507d1-114">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="507d1-115">예</span><span class="sxs-lookup"><span data-stu-id="507d1-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="507d1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="507d1-116">See Also</span></span>


[<span data-ttu-id="507d1-117">Lync Server 2013에서 통화 기능 및 권한을 부여하도록 음성 정책 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="507d1-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

