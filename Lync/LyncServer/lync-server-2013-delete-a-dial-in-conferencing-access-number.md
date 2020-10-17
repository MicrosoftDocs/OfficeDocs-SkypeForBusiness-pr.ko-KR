---
title: 'Lync Server 2013: 전화 접속 회의 액세스 번호 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50f9bd0929fff858a6e76cc41eccaf2930f0d0c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525675"
---
# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="dc37f-102">Lync Server 2013에서 전화 접속 회의 액세스 번호 삭제</span><span class="sxs-lookup"><span data-stu-id="dc37f-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc37f-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dc37f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dc37f-104">다음 단계에 따라 전화 접속 회의 액세스 번호를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="dc37f-105">전화 접속 회의 액세스 번호를 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="dc37f-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="dc37f-106">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="dc37f-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc37f-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc37f-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc37f-109">왼쪽 탐색 모음에서 **회의**를 클릭한 다음 **전화 접속 액세스 번호**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="dc37f-110">페이지의 목록에서 삭제할 전화 접속 번호를 클릭하고 **편집**을 클릭한 후에 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="dc37f-111">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc37f-112">Windows PowerShell Cmdlet을 사용 하 여 전화 접속 회의 액세스 번호 제거</span><span class="sxs-lookup"><span data-stu-id="dc37f-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dc37f-113">전화 접속 회의 액세스 번호는 Windows PowerShell 및 **get-csdialinconferencingaccessnumber** cmdlet을 사용 하 여 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="dc37f-114">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dc37f-115">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc37f-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="dc37f-116">특정 전화 접속 회의 액세스 번호를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dc37f-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="dc37f-117">다음 명령은 ID가 sip:RedmondDialInAccess@litwareinc.com인 전화 접속 회의 액세스 번호를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="dc37f-118">특정 지역에 할당 된 모든 전화 접속 회의 액세스 번호를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dc37f-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="dc37f-119">다음 명령은 Northwest 지역과 연결된 모든 전화 접속 회의 액세스 번호를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="dc37f-120">기본 언어에 따라 전화 접속 회의 액세스 번호를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="dc37f-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="dc37f-121">이 명령은 이탈리아어가 기본 언어인 모든 전화 접속 회의 액세스 번호를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc37f-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="dc37f-122">자세한 내용은 [get-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc37f-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

