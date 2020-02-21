---
title: 'Lync Server 2013: Lync Phone Edition에 대 한 보안 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e91ef78b2aedb3985ef1ab350de43261e4885d87
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="291c4-102">Lync Server 2013에서 Lync Phone Edition에 대 한 보안 설정 구성</span><span class="sxs-lookup"><span data-stu-id="291c4-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="291c4-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="291c4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="291c4-104">SIP 보안 설정 및 전화 잠금 설정을 통해 Lync Phone Edition을 실행 하는 장치의 보안을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="291c4-105">Lync Phone Edition에 대 한 보안 설정을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="291c4-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="291c4-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="291c4-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="291c4-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="291c4-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="291c4-109">왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **장치 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="291c4-110">**장치 구성** 페이지의 장치 구성 목록에서 보안 설정을 변경 하려는 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="291c4-111">**장치 구성 편집**의 **SIP 보안**에서 sip 보안 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="291c4-112">기본 수준은 **높음**이며 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="291c4-113">**장치 구성 편집**의 **전화 잠금**에서 기본적으로 선택 되어 있는 **장치 잠금 적용** 확인란을 선택 하거나 선택을 취소 하 고 최소 PIN 길이 (기본적으로 6 자)와 제한 시간 (기본값은 10 분)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="291c4-114">이러한 기본값을 사용 하거나 PIN 길이를 늘리거나 제한 시간을 줄이는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="291c4-115">자세한 내용은 <A href="lync-server-2013-enforce-phone-locking.md">Lync Server 2013에서 전화 잠금 적용</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="291c4-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="291c4-116">Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 전화에 대 한 보안 설정 구성</span><span class="sxs-lookup"><span data-stu-id="291c4-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="291c4-117">Lync Server 관리 셸 및 **set-csucphoneconfiguration** cmdlet을 사용 하 여 보안 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="291c4-118">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="291c4-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="291c4-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="291c4-120">SIP 보안 모드를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="291c4-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="291c4-121">이 명령은 UC 전화 설정의 전역 컬렉션에 대 한 SIPSecurityMode를 Medium으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="291c4-122">또한 SIP 보안을 낮음 또는 높음으로 설정할 수도 있습니다 (기본값).</span><span class="sxs-lookup"><span data-stu-id="291c4-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="291c4-123">최소 PIN 길이를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="291c4-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="291c4-124">이 예에서는 모든 UC 전화 설정이 최소 7 자리의 PIN 길이를 요구 하도록 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="291c4-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="291c4-125">자세한 내용은 [set-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="291c4-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="291c4-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="291c4-126">See Also</span></span>


[<span data-ttu-id="291c4-127">Lync Server 2013 인증 관리</span><span class="sxs-lookup"><span data-stu-id="291c4-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="291c4-128">Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="291c4-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

