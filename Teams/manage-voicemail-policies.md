---
title: Voicemail 정책 관리
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 사용자에 대한 Voicemail 정책을 관리합니다.
ms.openlocfilehash: 213908183c0d1dc608626272c0ea8aa5af308aff
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796927"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="808ba-103">조직의 음성메일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="808ba-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="808ba-104">비즈니스용 Skype 고객의 경우 전화 통화 정책을 통해 음성 Microsoft Teams 사용하지 않도록 설정하면 사용자에 대한 음성 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="808ba-105">Voicemail 전사는 기본적으로 사용하도록 설정되어 있으며, 모든 조직 및 사용자에 대해 기본적으로 전사 언행 마스킹을 사용하지 않도록 설정됩니다. 그러나 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 및 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet을 사용하여 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-105">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="808ba-106">조직의 사용자가 수신한 음성 메일 메시지는 조직 또는 조직이 호스트되는 Microsoft 365 Office 365 전사됩니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-106">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="808ba-107">테넌트가 호스트되는 지역은 음성 메일 메시지를 받는 사용자가 있는 지역과 같지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-107">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="808ba-108">테넌트가 호스팅되는 지역을 보려면 조직 [](https://go.microsoft.com/fwlink/p/?linkid=2067339) 프로필 페이지로 이동한 다음 데이터 위치 옆의 **세부** 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="808ba-108">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="808ba-109">**New-CsOnlineVoiceMailPolicy** cmdlet을 사용하여 전사 및 전사 불경한 마스킹에 대한 새 정책 인스턴스를 만들 수 없습니다. **Remove-CsOnlineVoiceMailPolicy** cmdlet을 사용하여 기존 정책 인스턴스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-109">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="808ba-110">음성메일 정책을 사용하여 사용자에 대한 전사 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-110">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="808ba-111">사용 가능한 모든 음성우선 정책 인스턴스를 표시하기 위해 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-111">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

```PowerShell
PS C:\> Get-CsOnlineVoicemailPolicy


Identity                            : Global
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:Default
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionProfanityMaskingEnabled
EnableTranscription                 : True
ShareData                           : Defer
EnableTranscriptionProfanityMasking : True
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True

Identity                            : Tag:TranscriptionDisabled
EnableTranscription                 : False
ShareData                           : Defer
EnableTranscriptionProfanityMasking : False
EnableEditingCallAnswerRulesSetting : True
MaximumRecordingLength              : 00:05:00
EnableTranscriptionTranslation      : True
```
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="808ba-112">조직에 대한 전사 해제</span><span class="sxs-lookup"><span data-stu-id="808ba-112">Turning off transcription for your organization</span></span>

<span data-ttu-id="808ba-113">전사에 대한 기본 설정이 조직에 설정되어 있기 때문에 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-113">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="808ba-114">이렇게 하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-114">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="808ba-115">조직에 대한 전사 언행 마스킹 켜기</span><span class="sxs-lookup"><span data-stu-id="808ba-115">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="808ba-116">전사 언행 마스킹은 기본적으로 조직에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-116">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="808ba-117">사용하도록 설정해야 하는 비즈니스 요구 사항이 있는 경우 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 전사 비하인드 마스킹을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-117">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="808ba-118">이렇게 하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="808ba-119">사용자에 대한 전사 해제</span><span class="sxs-lookup"><span data-stu-id="808ba-119">Turning off transcription for a user</span></span>

<span data-ttu-id="808ba-120">사용자 정책은 조직 기본 설정 전에 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-120">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="808ba-121">예를 들어 모든 사용자에 대해 음성사본 전사가 사용하도록 설정된 경우 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet을 사용하여 특정 사용자에 대한 전사 기능을 사용하지 않도록 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-121">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="808ba-122">단일 사용자에 대한 전사 기능을 사용하지 않도록 설정하면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-122">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="808ba-123">사용자에 대한 전사 언행 마스킹 켜기</span><span class="sxs-lookup"><span data-stu-id="808ba-123">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="808ba-124">특정 사용자에 대한 전사 불경한 마스킹을 사용하도록 설정하려면 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet을 사용하여 특정 사용자에 대한 전사 불경한 마스킹을 사용하도록 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-124">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="808ba-125">단일 사용자에 대한 전사 언행 마스킹을 사용하도록 설정하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-125">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="808ba-126">음성 Microsoft 365 및 Office 365 서비스는 음성 Office 365 캐시를 캐시하고 6시간마다 캐시를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-126">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="808ba-127">따라서 정책 변경 내용을 적용하는 데 최대 6시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="808ba-127">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
