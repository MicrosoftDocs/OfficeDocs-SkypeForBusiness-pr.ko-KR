---
title: 'Lync Server 2013: 클라이언트 버전 정책 규칙 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4bf9d60d9f99addffed25a87b05ea91650294
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="07128-102">Lync Server 2013에서 클라이언트 버전 정책 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="07128-102">View client version policy rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07128-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="07128-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="07128-104">클라이언트 버전 정책은 클라이언트 버전 정책 규칙 집합으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07128-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="07128-105">이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전을 사용하여 로그온을 시도할 때 수행할 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="07128-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="07128-106">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 정책 규칙을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07128-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="07128-107">Lync Server 제어판을 사용 하 여 클라이언트 버전 정책 규칙을 보려면</span><span class="sxs-lookup"><span data-stu-id="07128-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="07128-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="07128-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07128-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="07128-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="07128-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07128-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="07128-111">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **클라이언트 버전 정책** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07128-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="07128-112">**클라이언트 버전 정책** 페이지에서 보려는 클라이언트 버전 정책을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07128-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="07128-113">**클라이언트 버전 정책 편집** 페이지에 규칙이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07128-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="07128-114">규칙에 대 한 세부 정보를 보려면 규칙을 선택한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="07128-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="07128-115">Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 정책 규칙 보기</span><span class="sxs-lookup"><span data-stu-id="07128-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="07128-116">Lync Server Management Shell 및 **Get CsClientVersionPolicyRule** cmdlet을 사용 하 여 클라이언트 버전 정책 규칙을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07128-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="07128-117">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07128-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="07128-118">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07128-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="07128-119">클라이언트 버전 정책 규칙을 보려면</span><span class="sxs-lookup"><span data-stu-id="07128-119">To view client version policy rules</span></span>

  - <span data-ttu-id="07128-120">클라이언트 버전 정책 규칙을 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="07128-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="07128-121">이렇게 하면 구성 된 각 규칙에 대해 다음과 유사한 정보가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07128-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="07128-122">자세한 내용은 [Get CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07128-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

