---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 전역 정책 다시 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fe4be9f75e6e66d7b7b90e422ccd3ee6f5d2725
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="0799e-102">Lync Server 2013에서 외부 사용자 액세스에 대 한 전역 정책 다시 설정</span><span class="sxs-lookup"><span data-stu-id="0799e-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0799e-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0799e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0799e-p101">글로벌 정책은 완전히 삭제할 수 없습니다. 글로벌 정책에 대해 **삭제** 옵션을 사용하면 글로벌 정책이 기본 설정으로 다시 설정되기만 하여 외부 사용자 액세스 옵션에 대한 지원을 포함하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-p101">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="0799e-106">글로벌 정책을 기본 설정으로 다시 설정하려면</span><span class="sxs-lookup"><span data-stu-id="0799e-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="0799e-107">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0799e-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0799e-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0799e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0799e-110">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭한 다음 **외부 액세스 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="0799e-111">**외부 액세스 정책** 탭에서 글로벌 정책, **편집**을 차례로 클릭한 다음 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="0799e-p103">삭제를 확인하는 메시지가 표시되면 **확인**을 클릭합니다. 글로벌 정책이 다시 설정되었음을 알리는 메시지가 페이지 상단에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-p103">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0799e-114">Windows PowerShell Cmdlet을 사용 하 여 전역 외부 액세스 정책 다시 설정</span><span class="sxs-lookup"><span data-stu-id="0799e-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0799e-115">Windows PowerShell 및 Get-csexternalaccesspolicy cmdlet을 사용 하 여 전역 외부 액세스 정책을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="0799e-116">이 cmdlet은 Lync Server 2013 관리 셸 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="0799e-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0799e-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="0799e-118">전역 외부 액세스 정책을 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0799e-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="0799e-119">이 명령은 전역 외부 액세스 정책을 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0799e-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="0799e-120">자세한 내용은 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0799e-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

