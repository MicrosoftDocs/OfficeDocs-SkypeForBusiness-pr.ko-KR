---
title: 'Lync Server 2013: PIN 정책 정보 보기 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ab1705d7af62b6a44d278b666e619fae119540c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a><span data-ttu-id="7bf66-102">Lync Server 2013에서 PIN 정책 정보 보기 보기</span><span class="sxs-lookup"><span data-stu-id="7bf66-102">View PIN policy inforrmation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bf66-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7bf66-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7bf66-104">**Pin 정책** 탭을 사용 하 여 IP 전화와 함께 Lync 2013에 연결 하는 사용자의 PIN (개인 식별 번호) 인증을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-104">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="7bf66-105">PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용**이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="7bf66-106">자세한 내용은 [Modify 기존 웹 서비스 구성 설정에서 Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7bf66-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="7bf66-107">사용자 수준 또는 사이트 수준 PIN 정책을 수정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a><span data-ttu-id="7bf66-108">Lync Server 제어판의 PIN 정책에 대 한 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="7bf66-108">To view information about a PIN policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7bf66-109">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7bf66-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7bf66-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bf66-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7bf66-112">왼쪽 탐색 모음에서 **보안**을 클릭하고 **PIN 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="7bf66-113">**PIN 정책** 페이지에서 정책을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7bf66-114">Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 보기</span><span class="sxs-lookup"><span data-stu-id="7bf66-114">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7bf66-115">또한 Windows PowerShell 및 Get-cspinpolicy cmdlet을 사용 하 여 PIN 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-115">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="7bf66-116">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7bf66-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7bf66-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pin-policies"></a><span data-ttu-id="7bf66-118">PIN 정책을 보려면</span><span class="sxs-lookup"><span data-stu-id="7bf66-118">To view PIN policies</span></span>

  - <span data-ttu-id="7bf66-119">모든 PIN 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-119">To view information about all your PIN policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPinPolicy
    
    <span data-ttu-id="7bf66-120">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bf66-120">That will return information similar to this:</span></span>
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

<span data-ttu-id="7bf66-121">자세한 내용은 [get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bf66-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7bf66-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bf66-122">See Also</span></span>


[<span data-ttu-id="7bf66-123">Lync Server 2013에서 기존 웹 서비스 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="7bf66-123">Modify existing Web Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[<span data-ttu-id="7bf66-124">Lync Server 2013에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7bf66-124">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

