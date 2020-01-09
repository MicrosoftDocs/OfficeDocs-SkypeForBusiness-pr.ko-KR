---
title: 비즈니스용 Skype 서버에서 회의 정책 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 보는 방법에 대해 알아보세요.'
ms.openlocfilehash: 7ea7b5cb9ba54fcf26e5f37b79320466c19d1050
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992193"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="7cc4b-103">비즈니스용 Skype 서버에서 회의 정책 보기</span><span class="sxs-lookup"><span data-stu-id="7cc4b-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="7cc4b-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 보는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="7cc4b-105">Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype 서버 관리 셸을 사용 하 여 회의 정책을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7cc4b-106">비즈니스용 Skype 서버 제어판을 사용 하 여 회의 정책 보기</span><span class="sxs-lookup"><span data-stu-id="7cc4b-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7cc4b-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7cc4b-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7cc4b-109">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="7cc4b-110">**회의 정책** 페이지에서 보려는 회의 정책을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="7cc4b-111">**파일 편집 필터**에서 **세부 정보 표시** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="7cc4b-112">\*\*회의 정책 편집- \<정책\> \*\* 열림 선택한 정책에 대 한 설정을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="7cc4b-113">설정을 구성 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 회의 정책 만들기](create-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7cc4b-114">비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 보기</span><span class="sxs-lookup"><span data-stu-id="7cc4b-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7cc4b-115">회의 정책을 보려면 **Get-CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="7cc4b-116">Cmdlet은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="7cc4b-117">전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cc4b-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

