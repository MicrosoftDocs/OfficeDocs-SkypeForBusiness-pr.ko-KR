---
title: 'Lync Server 2013: Lync Phone Edition 구성 설정 정보 보기'
description: 'Lync Server 2013: Lync Phone Edition 구성 설정 정보를 확인 합니다.'
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
ms.openlocfilehash: 62719b24920ee72a92b2f80498d5ea2a59288c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576434"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="c4d74-103">Lync Server 2013에서 Lync Phone Edition 구성 설정 정보 보기</span><span class="sxs-lookup"><span data-stu-id="c4d74-103">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4d74-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c4d74-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c4d74-105">Lync Phone Edition을 실행 하는 장치에 대 한 구성 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-105">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="c4d74-106">정보는 컬렉션으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-106">The information is organized into collections.</span></span> <span data-ttu-id="c4d74-107">Lync Server를 설치 하는 경우 배포에서 Lync Phone Edition을 실행 하는 모든 장치에 적용 되는 Lync Phone Edition 설정의 모음을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-107">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="c4d74-108">특정 사이트에 대해 새 설정 컬렉션을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-108">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="c4d74-109">사이트 설정은 전역 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-109">Site settings take precedence over global settings.</span></span> <span data-ttu-id="c4d74-110">각 설정 컬렉션은 이름, 범위(전역/사이트), SIP 보안 설정, 로깅 수준, 음성 QoS(서비스 품질) 수준, 전화 잠금 설정 및 전화 잠금 세부 정보(잠금 해제 개인 ID 번호(PIN)의 최소 길이 및 전화가 자동으로 잠길 때까지의 시간)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-110">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="c4d74-111">Lync Phone Edition을 실행 하는 장치에 대 한 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="c4d74-111">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="c4d74-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c4d74-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c4d74-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4d74-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c4d74-115">왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **장치 구성** 탐색 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="c4d74-p103">**장치 구성** 페이지에서 정보를 보려는 설정 컬렉션을 클릭합니다. 기본 페이지에 이름, 범위, SIP 보안 설정, 음성 품질 수준 및 전화 잠금 설정이 나열됩니다. 로깅 수준 및 전화 잠금 세부 정보를 보려면 **편집** 메뉴를 클릭하고 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c4d74-119">Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="c4d74-119">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c4d74-120">Lync Server 관리 셸 및 **set-csucphoneconfiguration** cmdlet을 사용 하 여 Lync Phone Edition 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-120">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="c4d74-121">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-121">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c4d74-122">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4d74-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="c4d74-123">Lync Phone Edition 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="c4d74-123">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="c4d74-124">모든 Lync Phone Edition 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-124">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="c4d74-125">이 명령은 다음과 같은 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d74-125">The command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="c4d74-126">자세한 내용은 [set-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4d74-126">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4d74-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4d74-127">See Also</span></span>


[<span data-ttu-id="c4d74-128">Lync Server 2013에서 Lync Phone Edition 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c4d74-128">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="c4d74-129">Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="c4d74-129">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="c4d74-130">Lync Server 2013에서 Lync Phone Edition에 대 한 보안 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c4d74-130">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="c4d74-131">Lync Server 2013에서 전화 잠금 적용</span><span class="sxs-lookup"><span data-stu-id="c4d74-131">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

