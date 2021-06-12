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
ms.openlocfilehash: aa6b08cba7118a5e43f7f2bd3baea7fb3bc7f158
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910060"
---
# <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="af54a-103">조직의 음성메일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="af54a-103">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="af54a-104">비즈니스용 Skype 고객의 경우 전화 통화 정책을 통해 음성 Microsoft Teams 사용하지 않도록 설정하면 사용자에 대한 음성 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-104">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

## <a name="voicemail-organization-defaults-for-all-users"></a><span data-ttu-id="af54a-105">모든 사용자에 대한 Voicemail 조직 기본값</span><span class="sxs-lookup"><span data-stu-id="af54a-105">Voicemail organization defaults for all users</span></span>
- <span data-ttu-id="af54a-106">음성메일 전사가 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-106">Voicemail transcription is enabled.</span></span>
- <span data-ttu-id="af54a-107">Voicemail 전사 불경한 마스킹을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-107">Voicemail transcription profanity masking is disabled.</span></span>
- <span data-ttu-id="af54a-108">최대 녹화 시간은 5분으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-108">The maximum recording duration is set to five minutes.</span></span>

<span data-ttu-id="af54a-109">[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) 및 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet을 사용하여 이러한 기본값을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-109">You can control these defaults by using the [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy) and [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlets.</span></span>

<span data-ttu-id="af54a-110">조직의 사용자가 수신한 음성 메일 메시지는 조직 또는 조직이 호스트되는 Microsoft 365 Office 365 전사됩니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-110">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="af54a-111">테넌트가 호스트되는 지역은 음성 메일 메시지를 받는 사용자가 있는 지역과 같지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-111">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="af54a-112">테넌트가 호스팅되는 지역을 보려면 조직 [](https://go.microsoft.com/fwlink/p/?linkid=2067339) 프로필 페이지로 이동한 다음 데이터 위치 옆의 **세부** 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="af54a-112">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af54a-113">**New-CsOnlineVoiceMailPolicy** cmdlet을 사용하여 전사 및 전사 불경한 마스킹에 대한 새 정책 인스턴스를 만들 수 없습니다. **Remove-CsOnlineVoiceMailPolicy** cmdlet을 사용하여 기존 정책 인스턴스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-113">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="af54a-114">음성메일 정책을 사용하여 사용자에 대한 전사 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-114">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="af54a-115">사용 가능한 모든 음성우선 정책 인스턴스를 표시하기 위해 [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-115">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/Get-CsOnlineVoicemailPolicy) cmdlet.</span></span>

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
  
## <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="af54a-116">조직에 대한 전사 해제</span><span class="sxs-lookup"><span data-stu-id="af54a-116">Turning off transcription for your organization</span></span>

<span data-ttu-id="af54a-117">전사에 대한 기본 설정이 조직에 설정되어 있기 때문에 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-117">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="af54a-118">이렇게 하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-118">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

## <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="af54a-119">조직에 대한 전사 언행 마스킹 켜기</span><span class="sxs-lookup"><span data-stu-id="af54a-119">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="af54a-120">전사 언행 마스킹은 기본적으로 조직에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-120">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="af54a-121">사용하도록 설정해야 하는 비즈니스 요구 사항이 있는 경우 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 전사 비하인드 마스킹을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-121">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="af54a-122">이렇게 하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-122">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

## <a name="changing-the-recording-duration-for-your-organization"></a><span data-ttu-id="af54a-123">조직의 기록 기간 변경</span><span class="sxs-lookup"><span data-stu-id="af54a-123">Changing the recording duration for your organization</span></span>

<span data-ttu-id="af54a-124">최대 기록 길이는 조직에 대해 기본적으로 5분으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-124">The maximum recording length is set to five minutes by default for your organization.</span></span> <span data-ttu-id="af54a-125">최대 기록 길이를 늘리거나 줄이는 비즈니스 요구 사항이 있는 경우 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-125">If there is a business requirement to increase or decrease the maximum recording length, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="af54a-126">예를 들어 최대 기록 시간을 60초로 설정하면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-126">For example, to set the maximum recording time to 60 seconds,  run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

## <a name="dual-language-system-prompts-for-your-organization"></a><span data-ttu-id="af54a-127">조직에 대한 이중 언어 시스템 프롬프트</span><span class="sxs-lookup"><span data-stu-id="af54a-127">Dual language system prompts for your organization</span></span>

<span data-ttu-id="af54a-128">기본적으로 음성 메시지 시스템 프롬프트는 음성 메시지를 설정할 때 사용자가 선택한 언어로 발신자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-128">By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail.</span></span> <span data-ttu-id="af54a-129">음성 메시지 시스템 프롬프트를 두 언어로 표시해야 하는 비즈니스 요구 사항이 있는 경우 [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy)를 사용하여 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-129">If there is a business requirement to have the voicemail system prompts presented in two languages, this can be done by using [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/Set-CsOnlineVoicemailPolicy).</span></span> <span data-ttu-id="af54a-130">기본 언어와 보조 언어를 설정해야 하며 동일하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-130">A primary and secondary language must be set and may not be the same.</span></span> <span data-ttu-id="af54a-131">이렇게 하여 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-131">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

## <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="af54a-132">사용자에 대한 전사 해제</span><span class="sxs-lookup"><span data-stu-id="af54a-132">Turning off transcription for a user</span></span>

<span data-ttu-id="af54a-133">사용자 정책은 조직 기본 설정 전에 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-133">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="af54a-134">예를 들어 모든 사용자에 대해 음성사본 전사가 사용하도록 설정된 경우 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet을 사용하여 특정 사용자에 대한 전사 기능을 사용하지 않도록 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-134">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="af54a-135">단일 사용자에 대한 전사 기능을 사용하지 않도록 설정하면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-135">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

## <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="af54a-136">사용자에 대한 전사 언행 마스킹 켜기</span><span class="sxs-lookup"><span data-stu-id="af54a-136">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="af54a-137">특정 사용자에 대한 전사 불경한 마스킹을 사용하도록 설정하려면 [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet을 사용하여 특정 사용자에 대한 전사 불경한 마스킹을 사용하도록 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-137">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/Grant-CsOnlineVoicemailPolicy) cmdlet.</span></span>

<span data-ttu-id="af54a-138">단일 사용자에 대한 전사 언행 마스킹을 사용하도록 설정하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-138">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

## <a name="changing-the-recording-duration-for-a-user"></a><span data-ttu-id="af54a-139">사용자의 기록 기간 변경</span><span class="sxs-lookup"><span data-stu-id="af54a-139">Changing the recording duration for a user</span></span>

<span data-ttu-id="af54a-140">먼저 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet을 사용하여 사용자 지정 음성메일 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-140">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="af54a-141">아래 표시된 명령은 MaximumRecordingLength가 60초로 설정되고 다른 필드가 테넌트 수준 전역 값으로 설정된 사용자별 온라인 음성우선 정책 OneMinuteVoicemailPolicy를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-141">The command shown below creates a per-user online voicemail policy OneMinuteVoicemailPolicy with MaximumRecordingLength set to 60 seconds and other fields set to tenant level global value.</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "OneMinuteVoicemailPolicy" -MaximumRecordingLength ([TimeSpan]::FromSeconds(60))
```

<span data-ttu-id="af54a-142">사용자에게 이 사용자 지정 정책을 할당하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-142">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName OneMinuteVoicemailPolicy -Identity sip:amosmar@contoso.com
```

## <a name="dual-language-system-prompts-for-a-user"></a><span data-ttu-id="af54a-143">사용자에 대한 이중 언어 시스템 프롬프트</span><span class="sxs-lookup"><span data-stu-id="af54a-143">Dual language system prompts for a user</span></span>

<span data-ttu-id="af54a-144">먼저 [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet을 사용하여 사용자 지정 음성메일 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-144">You must first create a custom voicemail policy using the [New-CsOnlineVoicemailPolicy](/powershell/module/skype/New-CsOnlineVoicemailPolicy) cmdlet.</span></span> <span data-ttu-id="af54a-145">아래 표시된 명령은 PrimarySystemPromptLanguage가 en-US(영어 - 미국)로 설정되어 있으며 SecondarySystemPromptLanguage가 es-SP(스페인어 - 스페인)로 설정된 사용자당 온라인 음성메일 정책 enUS-esSP-VoicemailPolicy를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-145">The command shown below creates a per-user online voicemail policy enUS-esSP-VoicemailPolicy with the PrimarySystemPromptLanguage set to en-US (English - United States) and the SecondarySystemPromptLanguage set to es-SP (Spanish - Spain).</span></span>

```PowerShell
New-CsOnlineVoicemailPolicy -Identity "enUS-esES-VoicemailPolicy" -PrimarySystemPromptLanguage en-US -SecondarySystemPromptLanguage es-ES
```

<span data-ttu-id="af54a-146">사용자에게 이 사용자 지정 정책을 할당하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-146">To assign this custom policy to a user, run:</span></span> 

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName "enUS-esES-VoicemailPolicy" -Identity sip:amosmar@contoso.com
```

> [!NOTE]
> <span data-ttu-id="af54a-147">Get-CsOnlineVoicemailPolicy cmdlet은 현재 PrimarySystemPromptLanguage 및 SecondarySystemPromptLanguage에 대한 값을 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-147">The Get-CsOnlineVoicemailPolicy cmdlet is not currently returning the values for PrimarySystemPromptLanguage and SecondarySystemPromptLanguage.</span></span> <span data-ttu-id="af54a-148">다음 값을 참조하려면 다음과 같이 명령을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-148">To see these values modify the command as follows:</span></span>
>
> >```PowerShell
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).PrimarySystemPromptLanguage or
> > (Get-CsOnlineVoicemailPolicy -Identity PolicyName).SecondarySystemPromptLanguage 
>
> <span data-ttu-id="af54a-149">**PolicyName을** 정책 이름으로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-149">Replace **PolicyName** with the name of the policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="af54a-150">음성 Microsoft 365 및 Office 365 서비스는 음성 Office 365 캐시를 캐시하고 6시간마다 캐시를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-150">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 6 hours.</span></span> <span data-ttu-id="af54a-151">따라서 정책 변경 내용을 적용하는 데 최대 6시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af54a-151">So, policy changes that you make can take up to 6 hours to be applied.</span></span>
