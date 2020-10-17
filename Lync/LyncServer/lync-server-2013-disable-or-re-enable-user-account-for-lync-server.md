---
title: 'Lync Server 2013: Lync Server에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 합니다.'
description: 'Lync Server 2013: Lync Server에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b30d83d7a7f38b84f8e669ac06947eebf4a8545
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568174"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="b45d1-103">Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="b45d1-103">Disable or re-enable user account for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b45d1-104">_**마지막으로 수정 된 항목:** 2016-04-04_</span><span class="sxs-lookup"><span data-stu-id="b45d1-104">_**Topic Last Modified:** 2016-04-04_</span></span>

<span data-ttu-id="b45d1-105">다음 절차에 따라 사용자 계정에 대해 구성한 Lync Server 설정을 잃지 않고 Lync Server 2013에서 이전에 사용 하도록 설정 된 사용자 계정을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-105">You can use the following procedure to disable a previously enabled user account in Lync Server 2013 without losing the Lync Server settings that you configured for the user account.</span></span> <span data-ttu-id="b45d1-106">Lync Server 사용자 계정 설정이 손실 되지 않으므로 사용자 계정을 다시 구성 하지 않고도 이전에 설정한 사용자 계정을 다시 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-106">Because you do not lose the Lync Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b45d1-107">Active Directory에서 사용자 계정을 사용 하지 않도록 설정 하면 사용자가 Lync Server에 로그인 하거나 사용할 수 없게 <STRONG>됩니다</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b45d1-107">Simply disabling a user account in Active Directory <STRONG>will not</STRONG> stop a user from being able to sign into or use Lync Server.</span></span> <span data-ttu-id="b45d1-108">이는 Lync에서 인증 프로세스를 간소화 하는 인증서 인증을 사용 하기 때문 이며, 이러한 클라이언트 인증서는 180 일 동안 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-108">This is because Lync uses certificate authentication that streamlines the authentication process, and these client certificates are valid for 180 days.</span></span> <span data-ttu-id="b45d1-109">Lync Server에 대 한 액세스 권한을 부여 받은 <STRONG>사용자</STRONG> 에 게 사용 하도록 설정 된 Active Directory 계정을 사용 하지 않도록 설정 하려면이 문서에서 설명 하는 대로 Lync <STRONG>server 제어판</STRONG> 을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-109">If you want to stop disabled Active Directory accounts that had been enabled for Lync from having access to Lync Server, you must use the <STRONG>Disable-CsUser</STRONG> cmdlet, or use the <STRONG>Lync Server Control Panel</STRONG> as laid out in this article.</span></span> <span data-ttu-id="b45d1-110">사용자가 Lync에서 사용 하지 않도록 설정 되 고 중앙 관리 저장소가 환경에 복제 된 후에는 사용자가 더 이상 로그인 할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-110">Once the user is disabled in Lync and the Central Management store has been replicated in the environment the users will no longer be able to sign in.</span></span> <span data-ttu-id="b45d1-111">또한 로그인 한 사용자는 연결 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-111">Also, users that are signed in will get disconnected.</span></span>



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a><span data-ttu-id="b45d1-112">Lync Server에 대해 이전에 사용 하도록 설정 된 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b45d1-112">To disable or re-enable a previously enabled user account for Lync Server</span></span>

1.  <span data-ttu-id="b45d1-113">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b45d1-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b45d1-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b45d1-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b45d1-116">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b45d1-117">**사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="b45d1-118">표에서 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-118">In the table, click the user account that you want to disable or re-enable.</span></span>

6.  <span data-ttu-id="b45d1-119">**동작** 메뉴에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-119">On the **Action** menu, do one of the following:</span></span>
    
      - <span data-ttu-id="b45d1-120">Lync Server 2013에 대 한 사용자 계정을 일시적으로 사용 하지 않도록 설정 하려면 **Lync server에 대해 일시적으로 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-120">To temporarily disable the user account for Lync Server 2013, click **Temporarily disable for Lync Server**.</span></span>
    
      - <span data-ttu-id="b45d1-121">Lync Server 2013에 대 한 사용자 계정을 사용 하도록 설정 하려면 **Lync server에 대해 다시 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-121">To enable the user account for Lync Server 2013, click **Re-enable for Lync Server**.</span></span>

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="b45d1-122">Windows PowerShell을 사용 하 여 사용자 계정 사용/사용 안 함 설정</span><span class="sxs-lookup"><span data-stu-id="b45d1-122">Using Windows PowerShell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="b45d1-123">사용자 계정을 일시적으로 사용 하지 않도록 설정 했다가 나중에 다시 사용할 수 있도록 설정 하려면 **csuser** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-123">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="b45d1-124">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-124">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b45d1-125">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="b45d1-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-disable-a-user-account"></a><span data-ttu-id="b45d1-126">사용자 계정을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b45d1-126">To disable a user account</span></span>

  - <span data-ttu-id="b45d1-127">사용자 계정을 일시적으로 사용하지 않도록 설정하려면 Enabled 속성의 값을 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-127">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="b45d1-128">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-128">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a><span data-ttu-id="b45d1-129">사용자 계정을 다시 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b45d1-129">To re-enable a user account</span></span>

  - <span data-ttu-id="b45d1-130">사용하지 않도록 설정된 사용자 계정을 다시 사용하도록 설정하려면 Enabled 속성의 값을 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-130">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="b45d1-131">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b45d1-131">For example:</span></span>
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

<span data-ttu-id="b45d1-132">자세한 내용은 [CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b45d1-132">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b45d1-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b45d1-133">See Also</span></span>


[<span data-ttu-id="b45d1-134">Lync Server 2013에 대해 사용자 계정 추가 및 사용</span><span class="sxs-lookup"><span data-stu-id="b45d1-134">Add and enable user account for Lync Server 2013</span></span>](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="b45d1-135">Lync Server 2013에 대 한 사용자 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b45d1-135">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

