---
title: 클라이언트 버전 구성 설정의 기존 컬렉션 삭제
description: 클라이언트 버전 구성 설정의 기존 컬렉션을 삭제 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25a7d384bdfd84a1a6e04041988c16788a116626
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572884"
---
# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="42559-103">Lync Server 2013에서 클라이언트 버전 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="42559-103">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42559-104">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="42559-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="42559-105">사이트에 대해 이전에 구성 된 클라이언트 구성 설정을 제거 하려는 경우 Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42559-105">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="42559-106">Lync Server 제어판을 사용 하 여 클라이언트 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="42559-106">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="42559-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="42559-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="42559-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="42559-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42559-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="42559-110">왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-110">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="42559-111">사이트를 선택 하 고 **편집**, **삭제**를 차례로 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-111">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="42559-112">Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="42559-112">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="42559-113">클라이언트 버전 구성 설정은 **Remove-CsClientVersionConfiguration** cmdlet을 사용 하 여 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42559-113">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="42559-114">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42559-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="42559-115">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="42559-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="42559-116">클라이언트 버전 구성 설정의 지정 된 컬렉션을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="42559-116">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="42559-117">다음 명령은 Redmond 사이트에 적용 된 클라이언트 버전 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-117">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="42559-118">사이트 범위에 적용 된 모든 클라이언트 버전 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="42559-118">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="42559-119">이 명령은 사이트 범위에서 구성 된 모든 클라이언트 버전 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-119">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="42559-120">DefaultAction 속성 값을 기반으로 모든 클라이언트 버전 구성 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="42559-120">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="42559-121">그리고이 명령은 기본 동작이 "Block"으로 설정 된 모든 클라이언트 버전 구성 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="42559-121">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="42559-122">자세한 내용은 [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42559-122">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

