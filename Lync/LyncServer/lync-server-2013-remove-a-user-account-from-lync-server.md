---
title: 'Lync Server 2013: Lync Server에서 사용자 계정 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ee26fd15eb9df9174fd33cf9a45a6fe49411af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="48042-102">Lync Server 2013에서 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="48042-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48042-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="48042-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="48042-104">다음 절차를 사용 하 여 Lync Server 2013에서 이전에 추가 된 사용자 계정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48042-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48042-105">사용자를 제거 하면 사용자 계정에 대해 구성한 모든 설정이 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48042-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="48042-106">대신 사용자 계정을 일시적으로 사용 하지 않으려면 <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013에서 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</A>하는 방법 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48042-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="48042-107">Lync Server Management Shell을 사용 하 여 사용자 계정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="48042-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="48042-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="48042-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="48042-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="48042-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="48042-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48042-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="48042-111">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="48042-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="48042-112">**사용자 검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하지 않도록 설정 하려는 사용자 계정의 URI (Uniform resource identifier)를 모두 또는 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="48042-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="48042-113">표에서 제거 하려는 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="48042-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="48042-114">**작업** 메뉴에서 **Lync Server에서 제거**를 선택 하면 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="48042-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="48042-115">대화 상자에서 **확인** 을 선택 하 여 사용자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="48042-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="48042-116">Windows PowerShell Cmdlet을 사용 하 여 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="48042-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="48042-117">CsUser cmdlet을 사용 하 여 사용자 계정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48042-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="48042-118">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48042-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="48042-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48042-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="48042-120">사용자 계정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="48042-120">To remove a user account</span></span>

  - <span data-ttu-id="48042-121">사용자 계정을 제거 하려면 Disable-CsUser cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48042-121">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="48042-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48042-122">For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="48042-123">이 명령이 실행 된 후에는 계정과 이전 설정을 다시 사용 하도록 설정할 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48042-123">After this command has run there is no way to re-enable the account and its previous settings.</span></span> <span data-ttu-id="48042-124">대신: 진구 Myer에 대 한 새 계정을 만들려면 Enable-CsUser cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48042-124">Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="48042-125">자세한 내용은 [-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48042-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48042-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48042-126">See Also</span></span>


[<span data-ttu-id="48042-127">Lync Server 2013의 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="48042-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="48042-128">Lync Server 2013에 대 한 사용자 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="48042-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

