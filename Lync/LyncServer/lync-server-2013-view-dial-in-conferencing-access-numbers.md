---
title: 'Lync Server 2013: 전화 접속 회의 액세스 번호 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e86127c2a945bcd9154df0456545f5783fd1a34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="a4bf6-102">Lync Server 2013에서 전화 접속 회의 액세스 번호 보기</span><span class="sxs-lookup"><span data-stu-id="a4bf6-102">View dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4bf6-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a4bf6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a4bf6-104">Lync Server 2013 제어판에서 사용자에 게 전화 접속 액세스 번호를 제공 하 여 외부에서 모임에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-104">In Lync Server 2013 Control Panel, you provide dial-in access numbers to users so that they can join a meeting externally.</span></span>

<div>

## <a name="to-view-dial-in-access-numbers"></a><span data-ttu-id="a4bf6-105">전화 접속 액세스 번호를 보려면</span><span class="sxs-lookup"><span data-stu-id="a4bf6-105">To view dial-in access numbers</span></span>

1.  <span data-ttu-id="a4bf6-106">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a4bf6-107">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a4bf6-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a4bf6-109">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **전화 접속 액세스 번호**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-109">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="a4bf6-110">**전화 접속 액세스 번호** 페이지에서 보려는 액세스 번호를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-110">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>

5.  <span data-ttu-id="a4bf6-111">**편집**에서 **세부 정보 표시 ...** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-111">In **Edit**, select the **Show Details…**</span></span> <span data-ttu-id="a4bf6-112">확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-112">check box.</span></span>

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a4bf6-113">Windows PowerShell Cmdlet을 사용 하 여 전화 접속 회의 액세스 번호 보기</span><span class="sxs-lookup"><span data-stu-id="a4bf6-113">Viewing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a4bf6-114">전화 접속 회의 액세스 번호는 Windows PowerShell 및 CsDialInConferencingAccessNumber cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-114">Dial-in conferencing access numbers can be viewed by using Windows PowerShell and the Get-CsDialInConferencingAccessNumber cmdlet.</span></span> <span data-ttu-id="a4bf6-115">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a4bf6-116">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="a4bf6-117">전화 접속 회의 액세스 번호를 보려면</span><span class="sxs-lookup"><span data-stu-id="a4bf6-117">To view dial-in conferencing access numbers</span></span>

  - <span data-ttu-id="a4bf6-118">모든 전화 접속 회의 액세스 번호에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-118">To view information about all your dial-in conferencing access numbers, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsDialInConferencingAccessNumber
    
    <span data-ttu-id="a4bf6-119">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-119">That will return information similar to this:</span></span>
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

<span data-ttu-id="a4bf6-120">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4bf6-120">For more information, see the help topic for the [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

