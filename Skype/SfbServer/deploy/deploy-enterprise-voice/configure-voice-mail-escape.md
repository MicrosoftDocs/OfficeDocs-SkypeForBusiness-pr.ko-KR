---
title: 비즈니스용 Skype에서 음성 메일 esc 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '요약: 비즈니스용 skype 서버 관리 셸을 사용 하 여 비즈니스용 Skype 서버에서 음성 메일 esc를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 89c449f538fee2f5230cb66a664317cada723220
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191355"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="0394d-103">비즈니스용 Skype에서 음성 메일 esc 구성</span><span class="sxs-lookup"><span data-stu-id="0394d-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="0394d-104">**요약:** 비즈니스용 skype 서버 관리 셸을 사용 하 여 비즈니스용 Skype 서버에서 음성 메일 esc를 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="0394d-105">사용자가 휴대폰으로 동시 신호음을 구성 하는 경우, 휴대 전화를 끄거나, 배터리 전원이 꺼져 있거나, 범위를 벗어나면 일반적으로 발신자가 사용자의 개인 음성 메일로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="0394d-106">비즈니스용 Skype 서버를 사용 하는 경우 사용자는 회사 음성 메일 시스템으로 라우팅되는 비즈니스 관련 통화를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="0394d-107">특히 타이머를 구성할 수 있으며, 통화를 지정 된 시간 범위 내에서 통신 회사의 음성 메일로 수신 하는 경우 비즈니스용 Skype 서버는 해당 통신 회사의 음성 메일 시스템과 사용자의 개인 음성 메일을 연결 해제 합니다. 회사 시스템의 나머지 끝점은 계속 해 서 울립니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="0394d-108">이 방법으로 발신자는 자동으로 사용자의 회사 음성 메일로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="0394d-109">이 구성은 다음 매개 변수를 사용 하 여 음성 정책 수준에서 비즈니스용 Skype 서버 관리 셸 cmdlet **CsVoicePolicy**를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="0394d-110">음성 메일 esc를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="0394d-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="0394d-111">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="0394d-112">다음 매개 변수를 **CsVoicePolicy**로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="0394d-113">**EnableVoicemailEscapeTimer** -이탈 타이머를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="0394d-114">**PSTNVoicemailEscapeTimer** -제한 시간 값 (밀리초)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-114">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="0394d-115">기본값은 1500 밀리초 이며, 값의 범위는 0 밀리초 ~ 8000 밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="0394d-115">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="0394d-116">예</span><span class="sxs-lookup"><span data-stu-id="0394d-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="0394d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0394d-117">See also</span></span>

[<span data-ttu-id="0394d-118">음성 정책 및 PSTN 사용 레코드를 구성 하 여 통화 기능 및 사용 권한 승인</span><span class="sxs-lookup"><span data-stu-id="0394d-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

