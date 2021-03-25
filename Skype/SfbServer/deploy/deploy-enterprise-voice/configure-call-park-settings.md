---
title: 비즈니스용 Skype에서 통화 파크 설정 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 비즈니스용 Skype 서버 2013에서 통화 파크 설정을 Enterprise Voice.
ms.openlocfilehash: c1eecd55dac398752915ccb63886bbf85858fe47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111914"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="4d832-103">비즈니스용 Skype에서 통화 파크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4d832-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="4d832-104">비즈니스용 Skype 서버 2013에서 통화 파크 설정을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4d832-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="4d832-105">기본 통화 파크 설정을 사용하지 않는 경우 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="4d832-106">통화 파크 응용 프로그램을 설치하면 전역 설정이 기본적으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="4d832-107">전역 설정을 수정할 수 있으며 사이트별 설정을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="4d832-108">새 사이트별 설정을 만들려면 **New-CsCpsConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="4d832-109">기존 설정을 수정하려면 **Set-CsCpsConfiguration** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="4d832-110">대기된 통화의 시간이 초과되고 되걸기가 실패하는 경우 최소한 대체 대상에서 사용할 **OnTimeoutURI** 옵션을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="4d832-111">**New-CsCpsConfiguration** cmdlet 또는 **Set-CsCpsConfiguration** cmdlet을 사용하여 다음 설정 중 원하는 항목을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="4d832-112">**옵션**</span><span class="sxs-lookup"><span data-stu-id="4d832-112">**This option:**</span></span>                     | <span data-ttu-id="4d832-113">**지정 내용**</span><span class="sxs-lookup"><span data-stu-id="4d832-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="4d832-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="4d832-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="4d832-115">전화를 받았던 전화기에 벨이 다시 울릴 때까지 통화를 대기하고 있는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="4d832-p102">hh:mm:ss 형식으로 시간, 분 및 초를 지정하여 값을 입력해야 합니다. 최소값은 10초이고 최대값은 10분입니다. 기본값은 00:01:30입니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="4d832-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="4d832-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="4d832-120">통화를 대기하는 동안 전화를 건 사람에게 음악이 재생되는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="4d832-p103">값은 True 또는 False이고, 기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="4d832-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="4d832-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="4d832-p104">대기된 통화를 **OnTimeoutURI** 에 대해 지정된 대체 URI(Uniform Resource Identifier)에 전달할 때까지 해당 통화가 전화기에서 다시 울리는 횟수입니다. 기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="4d832-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="4d832-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="4d832-127">**MaxCallPickupAttempts** 가 초과될 때 응답하지 않은 대기된 통화를 경로 지정할 사용자 또는 응답 그룹의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="4d832-p105">값은 문자열 sip:로 시작하는 SIP URI여야 합니다(예: sip:bob@contoso.com). 기본적으로는 전달 주소가 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="4d832-131">통화 파크 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="4d832-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="4d832-132">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4d832-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="4d832-133">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="4d832-134">**Get-CsSite** cmdlet을 사용하여 사이트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4d832-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="4d832-135">자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4d832-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="4d832-136">예:</span><span class="sxs-lookup"><span data-stu-id="4d832-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="4d832-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d832-137">See also</span></span>

[<span data-ttu-id="4d832-138">통화 파킹 음악 사용자 지정 InSkype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="4d832-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="4d832-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="4d832-139">New-CsCpsConfiguration</span></span>](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="4d832-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="4d832-140">Set-CsCpsConfiguration</span></span>](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="4d832-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="4d832-141">Get-CsSite</span></span>](/powershell/module/skype/get-cssite?view=skype-ps)