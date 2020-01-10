---
title: 비즈니스용 Skype에서 통화 공원 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 공원 설정을 수정 하세요.
ms.openlocfilehash: 5ce9d15c4d233e620c5eb12c18688b5df958defb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001368"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="3a9b1-103">비즈니스용 Skype에서 통화 공원 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3a9b1-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="3a9b1-104">비즈니스용 Skype Server Enterprise Voice에서 통화 공원 설정을 수정 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="3a9b1-105">기본 통화 공원 설정을 사용 하지 않으려는 경우에는 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="3a9b1-106">통화 공원 응용 프로그램을 설치할 때 전역 설정이 기본적으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="3a9b1-107">전역 설정을 수정할 수 있으며 사이트 관련 설정을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="3a9b1-108">새 사이트 관련 설정을 만들려면 **CsCpsConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="3a9b1-109">**Set-CsCpsConfiguration** cmdlet을 사용 하 여 기존 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="3a9b1-110">최소한 파킹 된 통화가 시간 초과 되 고 ringback 실패할 경우 사용할 대체 대상에 대 한 **Ontimeouturi** 옵션을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="3a9b1-111">**CsCpsConfiguration** Cmdlet 또는 **Set-CsCpsConfiguration** cmdlet을 사용 하 여 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="3a9b1-112">**이 옵션:**</span><span class="sxs-lookup"><span data-stu-id="3a9b1-112">**This option:**</span></span>                     | <span data-ttu-id="3a9b1-113">**다음을 지정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3a9b1-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3a9b1-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="3a9b1-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="3a9b1-115">통화에 응답 한 전화기로 전화를 걸기 전에 대기 하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="3a9b1-116">값은 hh: mm: ss 형식으로 입력 해야 시, 분, 초를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-116">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds.</span></span> <span data-ttu-id="3a9b1-117">최 솟 값은 10 초 이며 최대값은 10 분입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-117">The minimum value is 10 seconds, and the maximum value is 10 minutes.</span></span> <span data-ttu-id="3a9b1-118">기본값은 00:01:30입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-118">The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="3a9b1-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="3a9b1-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="3a9b1-120">통화가 파킹 되는 동안 호출자가 음악을 재생할 것인지 여부</span><span class="sxs-lookup"><span data-stu-id="3a9b1-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="3a9b1-121">값은 True 또는 False입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-121">Values are True or False.</span></span> <span data-ttu-id="3a9b1-122">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-122">The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="3a9b1-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="3a9b1-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="3a9b1-124">파킹 된 통화가 **Ontimeouturi**에 대해 지정 된 대체 uri (Fallback Uniform resource Identifier)로 착신 전환 되기 전에 응답 하는 전화의 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-124">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**.</span></span> <span data-ttu-id="3a9b1-125">기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-125">The default is 1.</span></span>  <br/>                                                                                                                         |
| <span data-ttu-id="3a9b1-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="3a9b1-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="3a9b1-127">**MaxCallPickupAttempts** 를 초과 했을 때 응답 하지 않는 파킹 통화가 라우팅되는 사용자 또는 응답 그룹의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="3a9b1-128">값은 sip: 라는 문자열로 시작 하는 SIP URI 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-128">Value must be a SIP URI beginning with the string sip:.</span></span> <span data-ttu-id="3a9b1-129">예를 sip:bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-129">For example, sip:bob@contoso.com.</span></span> <span data-ttu-id="3a9b1-130">기본적으로 전달 주소가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-130">The default is no forwarding address.</span></span>  <br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="3a9b1-131">통화 공원 설정을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="3a9b1-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="3a9b1-132">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="3a9b1-133">런</span><span class="sxs-lookup"><span data-stu-id="3a9b1-133">Run:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="3a9b1-134">사이트를 식별 하려면 **Get-cssite** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="3a9b1-135">자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="3a9b1-136">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a9b1-136">For example:</span></span>

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="3a9b1-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a9b1-137">See also</span></span>

[<span data-ttu-id="3a9b1-138">통화 대기 음악 사용자 지정 (비즈니스용 Skype 2015)</span><span class="sxs-lookup"><span data-stu-id="3a9b1-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="3a9b1-139">새로운 CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a9b1-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="3a9b1-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3a9b1-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="3a9b1-141">가져오기-CsSite</span><span class="sxs-lookup"><span data-stu-id="3a9b1-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
