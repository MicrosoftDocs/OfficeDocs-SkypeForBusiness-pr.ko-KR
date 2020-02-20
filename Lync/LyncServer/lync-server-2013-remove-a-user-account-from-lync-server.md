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
ms.openlocfilehash: 11a02be3dc013ff385adfe9e0437bb5b430b905c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a><span data-ttu-id="330a2-102">Lync Server 2013에서 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="330a2-102">Remove a user account from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="330a2-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="330a2-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="330a2-104">다음 절차에 따라 Lync Server 2013에서 이전에 추가 된 사용자 계정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-104">You can use the following procedure to remove a previously added user account in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="330a2-105">사용자를 제거하면 사용자 계정에 대해 구성한 모든 설정이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-105">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="330a2-106">대신 사용자 계정을 일시적으로 사용 하지 않도록 설정 하려면 <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013에 대해 사용 안 함 또는 다시 사용 사용자 계정</A>항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="330a2-106">If you would like to temporarily disable a user account instead, see the topic <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a><span data-ttu-id="330a2-107">Lync Server 관리 셸을 사용 하 여 사용자 계정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="330a2-107">To remove a user account by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="330a2-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="330a2-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="330a2-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="330a2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="330a2-111">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-111">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="330a2-112">**사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="330a2-113">표에서 제거할 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-113">In the table, click the user account that you want to remove.</span></span>

6.  <span data-ttu-id="330a2-114">**동작** 메뉴에서 **Lync Server에서 제거**를 선택하면 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-114">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7.  <span data-ttu-id="330a2-115">대화 상자에서 **확인**을 선택하여 사용자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-115">From the dialog box, select **OK** to remove the user.</span></span>

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="330a2-116">Windows PowerShell Cmdlet을 사용 하 여 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="330a2-116">Removing User Accounts by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="330a2-117">사용 안 함-CsUser cmdlet을 사용 하 여 사용자 계정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-117">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="330a2-118">이 cmdlet은 Lync Server 2013 관리 셸 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="330a2-119">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="330a2-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-user-account"></a><span data-ttu-id="330a2-120">사용자 계정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="330a2-120">To remove a user account</span></span>

  - <span data-ttu-id="330a2-p104">사용자 계정을 제거하려면 Disable-CsUser cmdlet을 사용합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-p104">To remove a user account, use the Disable-CsUser cmdlet. For example:</span></span>
    
        Disable-CsUser -Identity "Ken Myer"
    
    <span data-ttu-id="330a2-p105">이 명령을 실행한 후에는 계정 및 이전 설정을 다시 사용하도록 설정할 수 없습니다. 대신 Enable-CsUser cmdlet을 사용하여 Ken Myer에 대해 새 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="330a2-p105">After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.</span></span>

</div>

<span data-ttu-id="330a2-125">자세한 내용은 [CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="330a2-125">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="330a2-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="330a2-126">See Also</span></span>


[<span data-ttu-id="330a2-127">Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="330a2-127">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[<span data-ttu-id="330a2-128">Lync Server 2013에 대 한 사용자 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="330a2-128">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

