---
title: 비즈니스용 Skype 서버에서 회의 정책 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 보는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: afe86f0a77e73c3fa7bf96339c4865598a7bc609
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119407"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="50946-103">비즈니스용 Skype 서버에서 회의 정책 보기</span><span class="sxs-lookup"><span data-stu-id="50946-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="50946-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 보는 방법을 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="50946-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="50946-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50946-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="50946-106">비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 보기</span><span class="sxs-lookup"><span data-stu-id="50946-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="50946-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="50946-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="50946-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="50946-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="50946-109">왼쪽 탐색 모음에서 회의 를 클릭한 다음 회의 정책을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="50946-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="50946-110">회의 **정책** 페이지에서 보게 될 회의 정책을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50946-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="50946-111">파일 **필터 편집에서** 자세한 정보 **표시 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="50946-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="50946-112">**회의 정책 편집 - \<policy\>** 를 열면 선택한 정책에 대한 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50946-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="50946-113">설정을 구성하는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 회의 정책 [만들기를 참조하세요.](create-policies.md)</span><span class="sxs-lookup"><span data-stu-id="50946-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="50946-114">비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 보기</span><span class="sxs-lookup"><span data-stu-id="50946-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="50946-115">회의 정책을 보기 위해 **Get-CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="50946-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="50946-116">이 cmdlet은 다음과 같은 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="50946-116">The cmdlet returns information such as the following:</span></span>
  
<pre>
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
</pre>

<span data-ttu-id="50946-117">전체 구문 설명 및 매개 변수 목록을 포함하여 자세한 내용은 [Get-CsConferencingPolicy 를 참조하십시오.](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="50946-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
