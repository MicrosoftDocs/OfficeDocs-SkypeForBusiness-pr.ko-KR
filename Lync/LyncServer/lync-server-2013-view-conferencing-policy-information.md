---
title: 'Lync Server 2013: 회의 정책 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664078db23ecba5d26852c2e1348935a3e4c60b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="53485-102">Lync Server 2013에서 회의 정책 정보 보기</span><span class="sxs-lookup"><span data-stu-id="53485-102">View conferencing policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53485-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="53485-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="53485-104">Lync Server 2013 제어판에서는 회의 정책을 사용 하 여 배포에서 회의가 구현 되는 방식을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="53485-104">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="53485-105">여기에는 다음과 같은 회의 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53485-105">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="53485-106">Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="53485-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="53485-107">특정 사이트나 사용자에 대해 회의가 어떻게 구현 되는지를 지정 하기 위해 만들고 사용할 수 있는 선택적 사이트 수준 및 사용자 수준 정책</span><span class="sxs-lookup"><span data-stu-id="53485-107">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="53485-108">회의 정책 설정을 보려면</span><span class="sxs-lookup"><span data-stu-id="53485-108">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="53485-109">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="53485-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="53485-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="53485-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53485-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="53485-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53485-112">왼쪽 탐색 모음에서 **회의**를 클릭하고 **회의 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53485-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="53485-113">**회의 정책** 페이지에서 보려는 회의 정책을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="53485-113">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="53485-114">**파일 필터 편집**에서 **세부 정보 표시** ...를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="53485-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="53485-115">확인란.</span><span class="sxs-lookup"><span data-stu-id="53485-115">check box.</span></span>
    
    <span data-ttu-id="53485-116">\*\*회의 정책 편집- \<선택한\> \*\* 정책에 대 한 설정을 표시 하는 정책이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="53485-116">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="53485-117">설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 회의 정책 만들기 또는 수정을](lync-server-2013-create-or-modify-a-conferencing-policy.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="53485-117">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="53485-118">Windows PowerShell Cmdlet을 사용 하 여 회의 정책 보기</span><span class="sxs-lookup"><span data-stu-id="53485-118">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="53485-119">전화 회의 정책은 Windows PowerShell 및 Get-csconferencingpolicy cmdlet을 사용 하 여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53485-119">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="53485-120">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53485-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="53485-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53485-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="53485-122">회의 정책을 보려면</span><span class="sxs-lookup"><span data-stu-id="53485-122">To view conferencing policies</span></span>

  - <span data-ttu-id="53485-123">모든 회의 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="53485-123">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="53485-124">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="53485-124">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

<span data-ttu-id="53485-125">자세한 내용은 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="53485-125">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

