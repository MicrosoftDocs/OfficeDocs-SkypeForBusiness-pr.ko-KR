---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 보기
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 보는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827928"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="66044-103">비즈니스용 Skype 서버에서 모임 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="66044-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="66044-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 보는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="66044-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="66044-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66044-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="66044-106">비즈니스용 Skype 서버 제어판을 사용하여 모임 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="66044-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="66044-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="66044-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="66044-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="66044-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="66044-109">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="66044-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="66044-110">왼쪽 탐색 모음에서 회의를 클릭한 다음 모임 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66044-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="66044-111">모임 구성 **페이지에서** 보게 될 모임 구성을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66044-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="66044-112">파일 **필터 편집에서** 세부 정보 **표시 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66044-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="66044-113">**모임 구성 \<policy\> 편집 -** 선택한 정책에 대한 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66044-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="66044-114">설정을 구성하는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 모임 구성 설정 [만들기를 참조하세요.](create-settings.md)</span><span class="sxs-lookup"><span data-stu-id="66044-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="66044-115">비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="66044-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="66044-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="66044-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="66044-117">모든 모임 구성 설정에 대한 정보를 확인하려면 **Get-CsMeetingConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66044-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="66044-118">이 명령은 다음과 같은 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="66044-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="66044-119">전체 매개 변수 목록을 포함하여 자세한 내용은 [Get-CsMeetingConfiguration을 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="66044-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

