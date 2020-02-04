---
title: 'Lync Server 2013: Lync Phone Edition 구성 설정 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a58450b1d69ce757f40194d179606f332e152d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="7935a-102">Lync Server 2013에서 Lync Phone Edition 구성 설정 정보 보기</span><span class="sxs-lookup"><span data-stu-id="7935a-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7935a-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7935a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7935a-104">Lync Phone Edition을 실행 하는 장치에 대 한 구성 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="7935a-105">정보는 모음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-105">The information is organized into collections.</span></span> <span data-ttu-id="7935a-106">Lync Server를 설치할 때 배포에서 Lync Phone Edition을 실행 하는 모든 장치에 적용 되는 Lync Phone Edition 설정의 모음을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="7935a-107">특정 사이트에 대 한 새 설정 모음을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="7935a-108">전역 설정 보다 사이트 설정이 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="7935a-109">각 설정 모음에는 이름, 범위 (전역 또는 사이트), SIP 보안 설정, 로깅 수준, 보이스 서비스 품질 (QoS) 수준, 전화 잠금 설정, 전화 잠금 세부 정보, 즉 잠금 해제 개인 식별의 최소 길이가 지정 됩니다. 전화 번호 (PIN) 및 휴대폰 자체를 잠그는 시간</span><span class="sxs-lookup"><span data-stu-id="7935a-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="7935a-110">Lync Phone Edition을 실행 하는 장치에 대 한 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="7935a-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="7935a-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7935a-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7935a-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7935a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7935a-114">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="7935a-115">**장치 구성** 페이지에서 정보를 볼 설정 모음을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="7935a-116">이름, 범위, SIP 보안 설정, 음성 음질 수준 및 전화 잠금 설정이 기본 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="7935a-117">로깅 수준 및 전화 잠금 세부 정보를 보려면 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7935a-118">Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="7935a-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7935a-119">Lync Server Management Shell 및 **CsUCPhoneConfiguration** cmdlet을 사용 하 여 Lync Phone Edition 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="7935a-120">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7935a-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7935a-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="7935a-122">Lync Phone Edition 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="7935a-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="7935a-123">모든 Lync Phone Edition 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="7935a-124">명령은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-124">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="7935a-125">자세한 내용은 [Get-help CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7935a-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7935a-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7935a-126">See Also</span></span>


[<span data-ttu-id="7935a-127">Lync Server 2013에서 Lync Phone Edition 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="7935a-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="7935a-128">Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="7935a-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="7935a-129">Lync Server 2013에서 Lync Phone 에디션에 대 한 보안 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7935a-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="7935a-130">Lync Server 2013에서 전화 잠금 적용</span><span class="sxs-lookup"><span data-stu-id="7935a-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

