---
title: 'Lync Server 2013: 외부 사용자 액세스에 대한 전역 정책 다시 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 327a658bcd75c05e291798598e53947b23c0c12f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="61ec1-102">Lync Server 2013에서 외부 사용자 액세스에 대한 전역 정책 다시 설정</span><span class="sxs-lookup"><span data-stu-id="61ec1-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61ec1-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="61ec1-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="61ec1-104">전역 정책은 완전히 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-104">You cannot completely delete a global policy.</span></span> <span data-ttu-id="61ec1-105">전역 정책에 대해 **Delete** 옵션을 사용 하면 전역 정책만 기본 설정으로 재설정 되며,이는 외부 사용자 액세스 옵션에 대 한 지원을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-105">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="61ec1-106">전역 정책을 기본 설정으로 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="61ec1-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="61ec1-107">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="61ec1-108">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="61ec1-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61ec1-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="61ec1-110">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="61ec1-111">**외부 액세스 정책** 탭에서 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="61ec1-112">삭제를 확인 하는 메시지가 표시 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-112">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="61ec1-113">전역 정책이 재설정 되었음을 알리는 메시지가 페이지 맨 위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-113">A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="61ec1-114">Windows PowerShell Cmdlet을 사용 하 여 전역 외부 액세스 정책 다시 설정</span><span class="sxs-lookup"><span data-stu-id="61ec1-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="61ec1-115">전역 외부 액세스 정책은 Windows PowerShell 및 CsExternalAccessPolicy cmdlet을 사용 하 여 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="61ec1-116">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="61ec1-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61ec1-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="61ec1-118">전역 외부 액세스 정책을 다시 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="61ec1-119">이 명령은 글로벌 외부 액세스 정책을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ec1-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="61ec1-120">자세한 내용은 [제거 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61ec1-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

