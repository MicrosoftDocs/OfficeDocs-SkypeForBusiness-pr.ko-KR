---
title: 비즈니스용 Skype 서버에서 모임 구성 설정 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: '요약: 비즈니스용 Skype 서버에서 모임 구성 설정을 만드는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 3d4f986b850b309d50967da9126b8b4eea08a166
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196427"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="aee93-103">비즈니스용 Skype 서버에서 모임 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="aee93-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="aee93-104">**요약:** 비즈니스용 Skype 서버에서 모임 구성 설정을 만드는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="aee93-105">비즈니스용 Skype Server 제어판을 사용 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="aee93-106">비즈니스용 Skype 서버 제어판을 사용 하 여 모임 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="aee93-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="aee93-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="aee93-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="aee93-109">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="aee93-110">**모임 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="aee93-111">사이트 수준 정책을 만들려면 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-111">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="aee93-112">사이트 검색 **선택** 필드에 모임 참가 설정을 정의할 사이트 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-112">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="aee93-113">사이트 결과 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-113">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="aee93-114">풀 수준 정책을 만들려면 **풀 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-114">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="aee93-115">서비스 검색 **선택** 필드에 모임 참가 설정을 정의할 풀 서비스 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-115">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="aee93-116">결과 서비스 목록에서 원하는 풀을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-116">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="aee93-117">대기실를 통해 PSTN (공개 교환 전화 네트워크)에서 전화 접속 하는 참가자를 라우팅하려면 **pstn 발신자의 로비 사용 안 함** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-117">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box.</span></span> <span data-ttu-id="aee93-118">기본적으로 PSTN에서 전화를 거는 참가자는 모임으로 직접 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-118">By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="aee93-119">모임에서 발표자가 될 수 있는 사용자를 구성 하려면 **발표자로 지정**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="aee93-120">이끌이 이외의 사용자가 발표자가 될 수 없도록 하려면 **없음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="aee93-121">조직의 구성원 인 참가자만 발표자로 지정할 수 있도록 하려면 **회사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-121">To allow only participants who are members of your organization to be a presenter, click **Company**.</span></span> <span data-ttu-id="aee93-122">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-122">This is the default setting.</span></span>
    
   - <span data-ttu-id="aee93-123">모든 참가자가 발표자로 지정 하도록 허용 하려면 **모든 사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="aee93-124">모임을 예약할 때 주최자가 회의 유형을 선택 하도록 하려면 **기본적으로 지정 된 회의 유형** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-124">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box.</span></span> <span data-ttu-id="aee93-125">기본적으로 회의 유형은 자동으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-125">By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="aee93-126">익명 (인증 되지 않은) 사용자가 자동으로 허용 되지 않도록 하려면 **기본적으로 익명 사용자** 허용 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-126">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box.</span></span> <span data-ttu-id="aee93-127">기본적으로 익명 사용자는 자동으로 모임에 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-127">By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="aee93-128">참가자에 게 전송 되는 모임 초대를 사용자 지정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="aee93-129">Url 및 사용자 지정 바닥글 텍스트에 대 한 최대 길이는 1KB 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="aee93-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="aee93-130">**도움말 URL**을 제외한 사용자 지정에 대 한 값을 지정 하지 않으면 모임에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="aee93-131">사용자 지정 도움말 URL을 포함 하지 않으면 비즈니스용 Skype에 대 한 기본 도움말 URL이 초대에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="aee93-132">모임 초대에 표시 되는 로고를 사용자 지정 하려면 **로고 URL**에 로고의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="aee93-133">로고는 188 x 30 픽셀 크기의 GIF 또는 JPG 이미지 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="aee93-134">모임 초대에 표시 되는 도움말 텍스트를 사용자 지정 하려면 **도움말 URL**에 도움말 텍스트의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="aee93-135">모임 초대에 표시 되는 법률 텍스트를 사용자 지정 하려면 **legal 텍스트 URL**에 법률 텍스트의 위치를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="aee93-136">모임 초대에 표시 되는 바닥글 텍스트를 사용자 지정 하려면 **사용자 지정 바닥글 텍스트**에 텍스트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="aee93-137">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="aee93-138">비즈니스용 Skype Server Management Shell을 사용 하 여 모임 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="aee93-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="aee93-139">모임 구성 설정을 만들려면 **새 CsMeetingConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="aee93-140">다음 명령은 Redmond 사이트에 대 한 새 모임 구성 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="aee93-141">앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 모임 구성 설정에는 해당 속성에 대 한 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="aee93-142">다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-142">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="aee93-143">예를 들어 기본적으로 모든 사용자가 발표자로 모임에 참가 하도록 허용 하는 모임 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-143">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="aee93-144">여러 매개 변수를 포함 하 여 여러 속성 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="aee93-145">예를 들어 다음 명령은 모든 사람을 발표자로 모임에 입장할, PSTN 사용자가 모임에 공식적으로 참석할 때까지 대기실에서 대기 하도록 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee93-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="aee93-146">전체 매개 변수 목록을 비롯 한 자세한 내용은 [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aee93-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

