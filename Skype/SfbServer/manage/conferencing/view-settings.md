---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 보는 방법에 대해 알아보세요.'
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818459"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="dec56-103">비즈니스용 Skype 서버에서 모임 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="dec56-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="dec56-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 보는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dec56-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="dec56-105">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dec56-106">비즈니스용 Skype 서버 제어판을 사용 하 여 모임 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="dec56-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="dec56-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="dec56-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="dec56-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="dec56-109">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="dec56-110">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="dec56-111">**모임 구성** 페이지에서 보려는 모임 구성을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="dec56-112">**파일 편집 필터**에서 **세부 정보 표시** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="dec56-113">\*\*모임 구성 편집- \<정책이\> \*\* 열리고 선택한 정책에 대 한 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="dec56-114">설정을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 모임 구성 설정 만들기](create-settings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dec56-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="dec56-115">비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="dec56-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="dec56-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="dec56-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="dec56-117">모든 모임 구성 설정에 대 한 정보를 보려면 **Get-CsMeetingConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="dec56-118">이 명령은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec56-118">This command will return information similar to the following:</span></span>
  
<pre>
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
</pre>

<span data-ttu-id="dec56-119">전체 매개 변수 목록을 비롯 한 자세한 내용은 [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dec56-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

