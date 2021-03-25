---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 만들기
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
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 만드는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 862ffc56fd14c446a747a490daa0655e410e01d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119517"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="ae8c6-103">비즈니스용 Skype 서버에서 모임 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="ae8c6-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="ae8c6-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 만드는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="ae8c6-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ae8c6-106">비즈니스용 Skype 서버 제어판을 사용하여 모임 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="ae8c6-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ae8c6-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ae8c6-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ae8c6-109">왼쪽 탐색 모음에서 회의 를 클릭한 다음 모임 구성 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae8c6-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="ae8c6-110">**모임 구성** 페이지에서 **새로 만들기** 를 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="ae8c6-p101">사이트 수준 정책을 만들려면 **사이트 구성** 을 클릭합니다. **사이트 선택** 검색 필드에 모임 참가 설정을 정의할 사이트의 이름 일부나 전체를 입력합니다. 사이트 결과 목록에서 원하는 사이트를 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="ae8c6-p102">풀 수준 정책을 만들려면 **풀 구성** 을 클릭합니다. **서비스 선택** 검색 필드에 모임 참가 설정을 정의할 풀 서비스의 이름 일부나 전체를 입력합니다. 서비스 결과 목록에서 원하는 풀을 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="ae8c6-p103">PSTN(공중 전화망)에서 전화 접속한 참가자를 대기실을 거쳐 라우팅하려면 **PSTN 발신자 바이패스 대기실** 확인란의 선택을 취소합니다. 기본적으로 PSTN에서 전화 접속한 참가자는 모임으로 바로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="ae8c6-119">모임에서 발표자가 될 수 있는 사용자를 구성하려면 **발표자로 지정** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="ae8c6-120">이끌이 이외의 다른 사용자를 발표자로 지정하지 않으려면 **없음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="ae8c6-p104">조직의 구성원인 참가자만 발표자로 지정하려면 **회사** 를 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="ae8c6-123">모든 참가자를 발표자로 지정하려면 **모든 참가자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="ae8c6-p105">모임 예약 시 이끌이가 회의 유형을 선택하도록 하려면 **기본적으로 지정되는 전화 회의 유형** 확인란의 선택을 취소합니다. 회의 유형은 기본적으로 자동으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="ae8c6-p106">인증되지 않은 익명의 사용자를 자동으로 허용되지 않도록 하려면 **기본적으로 익명 사용자 허용** 확인란의 선택을 취소합니다. 기본적으로 익명 사용자는 모임에 자동으로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="ae8c6-128">참가자에게 전송된 모임 초대를 사용자 지정하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="ae8c6-129">URL 및 사용자 지정 발자국 텍스트의 최대 길이는 1KB입니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="ae8c6-130">도움말 **URL을** 제외하고 사용자 지정에 대한 값을 지정하지 않으면 모임에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="ae8c6-131">사용자 지정 도움말 URL을 포함하지 않는 경우 비즈니스용 Skype의 기본 도움말 URL이 초대에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="ae8c6-132">모임 초대에 나타나는 로고를 사용자 지정하기 위해 로고 **URL에** 로고 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="ae8c6-133">로고는 크기가 188 x 30픽셀인 GIF 또는 JPG 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="ae8c6-134">모임 초대에 나타나는 도움말 텍스트를 사용자 지정하기 위해 도움말 **URL에** 도움말 텍스트의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="ae8c6-135">모임 초대에 나타나는 법적 텍스트를 사용자 지정하기 위해 법률 텍스트 **URL에** 법률 텍스트의 위치를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="ae8c6-136">모임 초대에 나타나는 글자 텍스트를 사용자 지정하는 경우 사용자 지정 발자국 **텍스트에** 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="ae8c6-137">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ae8c6-138">비즈니스용 Skype 서버 관리 셸을 사용하여 모임 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="ae8c6-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ae8c6-139">모임 구성 설정을 만들하려면 **New-CsMeetingConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="ae8c6-140">다음 명령은 Redmond 사이트에 대한 새 모임 구성 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="ae8c6-141">이전 명령에 필수 Identity 매개 변수 외의 매개 변수가 지정되지 않은 경우 새 모임 구성 설정은 모든 속성에 대해 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="ae8c6-142">다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-142">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="ae8c6-143">예를 들어 기본적으로 모든 사람을 발표자로 지정하는 모임 구성 설정 컬렉션을 만들 때 다음과 같은 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-143">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="ae8c6-144">여러 매개 변수를 포함하여 여러 속성 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="ae8c6-145">예를 들어 다음 명령은 모든 사용자를 발표자로 인정하고 PSTN 사용자가 모임에 공식적으로 참석할 때까지 대기실에서 대기하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae8c6-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="ae8c6-146">전체 매개 변수 목록을 포함하여 자세한 내용은 [New-CsMeetingConfiguration을 참조하십시오.](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ae8c6-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
