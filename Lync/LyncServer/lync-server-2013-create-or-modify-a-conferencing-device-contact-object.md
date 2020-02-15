---
title: 'Lync Server 2013: 회의 장치 연락처 개체 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bd3cfa6099d45cbad2d15ed164652756f50f5e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="1af09-102">Lync Server 2013에서 회의 장치 연락처 개체 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="1af09-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1af09-103">_**마지막으로 수정 된 항목:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="1af09-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="1af09-104">회의 대화방 개체를 만들려면 먼저 장치를 나타내는 Active Directory 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1af09-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="1af09-105">그런 다음 **enable-csmeetingroom** cmdlet을 사용 하 여 해당 계정이 회의 장치로 작동 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af09-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="1af09-106">기존 회의 장치의 속성을 변경 해야 하는 경우 **enable-csmeetingroom** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af09-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="1af09-107">이러한 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1af09-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1af09-108">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1af09-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="1af09-109">회의 장치 만들기</span><span class="sxs-lookup"><span data-stu-id="1af09-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="1af09-110">새 회의 장치를 나타내는 Active Directory 사용자 계정을 만든 후에는 **enable-csmeetingroom** cmdlet을 사용 하 여 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af09-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="1af09-111">회의 장치 id, b) 대화방 계정이 있는 등록자 풀 및 c) 해당 계정에 할당할 SIP 주소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af09-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="1af09-112">예:</span><span class="sxs-lookup"><span data-stu-id="1af09-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="1af09-113">회의 장치 수정</span><span class="sxs-lookup"><span data-stu-id="1af09-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="1af09-114">기존 회의 장치의 속성 값을 수정 하려면 **enable-csmeetingroom** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af09-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="1af09-115">예를 들어 다음 명령은 회의 장치와 연결 된 전화 번호 (LineUri)를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1af09-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="1af09-116">자세한 내용은 [enable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 및 [enable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) Cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1af09-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

