---
title: 'Lync Server 2013: 전화 잠금 적용'
description: 'Lync Server 2013: 전화 잠금을 적용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575604"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a><span data-ttu-id="8ea2c-103">Lync Server 2013에서 전화 잠금 적용</span><span class="sxs-lookup"><span data-stu-id="8ea2c-103">Enforce phone locking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ea2c-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8ea2c-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8ea2c-105">Lync Phone Edition 장치는 보안상의 이유로 잠길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-105">Lync Phone Edition devices can be locked for security purposes.</span></span> <span data-ttu-id="8ea2c-106">전화 잠금을 적용 하면 사용자가 구성한 일정 기간이 지난 후 Lync Phone Edition을 실행 하는 장치가 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-106">If you enforce phone lock, the device running Lync Phone Edition locks after a period of time that you configure.</span></span> <span data-ttu-id="8ea2c-107">전화가 잠기면 사용자가 전화를 걸 수 있지만 일정 및 연락처 정보, 음성 메일 또는 통화 로그에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-107">When a phone is locked, a user can make calls but cannot access calendar and contact information, voice mail, or call logs or use search.</span></span> <span data-ttu-id="8ea2c-108">전화 잠금을 해제 하기 위해 사용자는 PIN을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-108">To unlock the phone, the user enters a PIN.</span></span>

<span data-ttu-id="8ea2c-109">전화 잠금을 적용 하려면 Lync Server 제어판 또는 Lync Server PowerShell cmdlet을 사용 하 여 사용 하도록 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-109">To enforce phone lock, enable and configure it by using Lync Server Control Panel or Lync Server PowerShell cmdlets.</span></span> <span data-ttu-id="8ea2c-110">전화 잠금은 전역적으로 또는이를 구성 하는 사이트 내 에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-110">You can enforce phone lock globally or only within the site for which it is configured.</span></span>

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a><span data-ttu-id="8ea2c-111">전화 잠금을 구성 하 고 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="8ea2c-111">To configure and enforce the phone lock</span></span>

1.  <span data-ttu-id="8ea2c-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8ea2c-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8ea2c-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8ea2c-115">**클라이언트**를 클릭 하 고 **장치 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-115">Click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="8ea2c-116">**장치 구성** 탭의 장치 구성 목록에서 전화 잠금 설정을 변경할 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-116">On the **Device Configuration** tab, in the list of device configurations, double-click the configuration for which you want to change the phone lock settings.</span></span>

5.  <span data-ttu-id="8ea2c-117">**장치 구성 편집** 대화 상자에서 **장치 잠금 적용** 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-117">In the **Edit Device Configuration** dialog box, verify that the **Enforce device locking** check box is selected.</span></span>

6.  <span data-ttu-id="8ea2c-118">**최소 PIN 길이**에서 잠금 해제 PIN에 포함 해야 하는 최소 자릿수의 기본값을 적용 하거나 새 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-118">In **Minimum PIN length**, accept the default value for the minimum number of digits that the unlock PIN must contain or specify a new value.</span></span> <span data-ttu-id="8ea2c-119">PIN 길이의 범위는 4에서 15 사이의 숫자이 고 기본값은 6입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-119">The range for the PIN length is four to 15 digits, and the default is six.</span></span>

7.  <span data-ttu-id="8ea2c-120">**전화 잠금 시간 제한**에서 전화를 잠그기 전 까지의 최소 기간에 대해 기본값을 적용 하거나 새 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-120">In **Phone lock time-out**, accept the default value for the minimum length of time before the phone locks itself or specify a new value.</span></span> <span data-ttu-id="8ea2c-121">시간 제한 범위는 0 ~ 60 분 이며 기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-121">The range for the timeout is 0 to 60 minutes, and the default is 10.</span></span> <span data-ttu-id="8ea2c-122">HH: MM: SS 형식으로 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-122">Enter the value in the format HH:MM:SS.</span></span>

8.  <span data-ttu-id="8ea2c-123">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8ea2c-124">Windows PowerShell Cmdlet을 사용 하 여 전화 잠금 적용</span><span class="sxs-lookup"><span data-stu-id="8ea2c-124">Enforcing Phone Locking by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8ea2c-125">전화 잠금은 Set-CsUCPhoneConfiguration cmdlet을 사용 하 여 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-125">Phone locking can be enforced by using the Set-CsUCPhoneConfiguration cmdlet.</span></span> <span data-ttu-id="8ea2c-126">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-126">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8ea2c-127">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-phone-locking"></a><span data-ttu-id="8ea2c-128">전화 잠금을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8ea2c-128">To enable phone locking</span></span>

  - <span data-ttu-id="8ea2c-129">다음 명령은 Redmond 사이트에 대 한 전화 잠금을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-129">The following command enables phone locking for the Redmond site.</span></span> <span data-ttu-id="8ea2c-130">전화 잠금을 사용 하지 않으려면 EnforcePhoneLock 속성을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-130">To disable phone locking, set the EnforcePhoneLock property to False ($False).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a><span data-ttu-id="8ea2c-131">전화 잠금을 사용 하도록 설정 하 고 전화 잠금 제한 시간을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="8ea2c-131">To enable phone locking and modify the phone lock timeout</span></span>

  - <span data-ttu-id="8ea2c-132">이 명령은 전화 잠금을 사용 하도록 설정 하 고 전화 잠금 제한 시간을 30 분으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-132">This command enables phone locking and also sets the phone lock timeout to 30 minutes.</span></span>
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a><span data-ttu-id="8ea2c-133">조직 전체에서 전화 잠금을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="8ea2c-133">To enable phone locking throughout the organization</span></span>

  - <span data-ttu-id="8ea2c-134">이 예에서는 조직에서 사용 중인 모든 UC 전화 구성 설정에 대해 전화 잠금이 사용 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-134">In this example, phone locking is enabled on all the UC phone configuration settings in use in the organization.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

<span data-ttu-id="8ea2c-135">자세한 내용은 [set-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8ea2c-135">For more information, see the help topic for the [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ea2c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ea2c-136">See Also</span></span>


[<span data-ttu-id="8ea2c-137">Lync Server 2013 인증 관리</span><span class="sxs-lookup"><span data-stu-id="8ea2c-137">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="8ea2c-138">Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="8ea2c-138">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

