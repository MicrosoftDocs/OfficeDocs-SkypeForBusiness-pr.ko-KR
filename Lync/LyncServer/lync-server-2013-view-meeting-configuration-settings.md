---
title: 'Lync Server 2013: 모임 구성 설정 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac2af6e82546e44e0d10084e5878cef0e1a6b6f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="06beb-102">Lync Server 2013에서 모임 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="06beb-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06beb-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="06beb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="06beb-104">Lync Server 2013 제어판에서는 모임 구성 설정을 사용 하 여 배포에서 모임이 구현 되는 방식을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="06beb-105">여기에는 다음 모임 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="06beb-106">Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="06beb-107">특정 사이트 또는 사용자에 대해 모임이 구현 되는 방식을 지정 하는 데 사용할 수 있는 사이트 수준 및 사용자 수준 구성 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="06beb-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="06beb-108">모임 구성 설정을 보려면</span><span class="sxs-lookup"><span data-stu-id="06beb-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="06beb-109">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="06beb-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="06beb-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="06beb-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="06beb-112">왼쪽 탐색 표시줄에서 **회의**, **모임 구성**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="06beb-113">**모임 구성** 페이지에서 보려는 모임 구성을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="06beb-114">**파일 필터 편집**에서 **세부 정보 표시** ...를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="06beb-115">확인란.</span><span class="sxs-lookup"><span data-stu-id="06beb-115">check box.</span></span>
    
    <span data-ttu-id="06beb-116">\*\*모임 구성 편집- \<선택한\> \*\* 정책에 대 한 설정을 표시 하는 정책이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="06beb-117">설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 모임 구성 설정 컬렉션 만들기 또는 수정을](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="06beb-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="06beb-118">Windows PowerShell Cmdlet을 사용 하 여 모임 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="06beb-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="06beb-119">모임 구성 설정은 Windows PowerShell 및 Get-csmeetingconfiguration cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="06beb-120">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="06beb-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06beb-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="06beb-122">모임 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="06beb-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="06beb-123">모든 모임 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="06beb-124">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="06beb-124">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="06beb-125">자세한 내용은 [get-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="06beb-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

