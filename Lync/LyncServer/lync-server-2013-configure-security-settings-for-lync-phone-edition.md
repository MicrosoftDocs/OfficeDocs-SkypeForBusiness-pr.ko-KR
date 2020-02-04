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
ms.openlocfilehash: 6f414eb395025b359d074bb1d5882b20919eb3f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="3b1ba-102">Lync Server 2013에서 Lync Phone 에디션에 대 한 보안 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b1ba-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3b1ba-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3b1ba-104">SIP 보안 설정 및 전화 잠금 설정을 통해 Lync Phone Edition을 실행 하는 디바이스의 보안을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="3b1ba-105">Lync Phone Edition에 대 한 보안 설정을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="3b1ba-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="3b1ba-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b1ba-107">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b1ba-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b1ba-109">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="3b1ba-110">**장치 구성** 페이지의 장치 구성 목록에서 보안 설정을 변경 하려는 구성을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="3b1ba-111">**장치 구성 편집**의 **SIP 보안**에서 sip 보안 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="3b1ba-112">기본 수준은 **높음으로**사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="3b1ba-113">**장치 구성 편집**의 **전화 잠금**에서 **장치 잠금 적용** 확인란 (기본적으로 선택 됨)을 선택 하거나 선택을 취소 하 고 최소 PIN 길이 (기본적으로 6 자) 및 제한 시간 (기본적으로 10 분)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="3b1ba-114">이러한 기본값을 사용 하는 것이 좋으며 PIN 길이 및/또는 제한 시간 간격을 감소 시키는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3b1ba-115">자세한 내용은 <A href="lync-server-2013-enforce-phone-locking.md">Lync Server 2013에서 전화 잠금 적용</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3b1ba-116">Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 전화에 대 한 보안 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3b1ba-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3b1ba-117">Lync Server Management Shell 및 **CsUCPhoneConfiguration** cmdlet을 사용 하 여 보안 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="3b1ba-118">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3b1ba-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="3b1ba-120">SIP 보안 모드를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="3b1ba-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="3b1ba-121">이 명령은 UC 전화 설정의 전역 컬렉션에 대 한 SIPSecurityMode를 Medium으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="3b1ba-122">또한 SIP 보안은 낮음 또는 높음 (기본값)으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="3b1ba-123">최소 PIN 길이를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="3b1ba-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="3b1ba-124">이 예제에서는 모든 UC 전화 설정이 최소 7 자리 PIN 길이를 요구 하도록 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="3b1ba-125">자세한 내용은 [Get-help CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b1ba-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b1ba-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b1ba-126">See Also</span></span>


[<span data-ttu-id="3b1ba-127">Lync Server 2013 인증 관리</span><span class="sxs-lookup"><span data-stu-id="3b1ba-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="3b1ba-128">Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="3b1ba-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

