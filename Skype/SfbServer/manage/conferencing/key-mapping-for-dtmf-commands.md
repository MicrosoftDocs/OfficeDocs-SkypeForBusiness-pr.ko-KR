---
title: 비즈니스용 Skype 서버에서 DTMF 명령에 대한 키 매핑 관리
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
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: '요약: 비즈니스용 Skype 서버에서 DTMF(복합 주파수 부호) 명령의 키 매핑을 관리하는 방법을 학습합니다.'
ms.openlocfilehash: 6b409ccce10128fdd7776e3ea77d6ee17d4a49f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119447"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="eb590-103">비즈니스용 Skype 서버에서 DTMF 명령에 대한 키 매핑 관리</span><span class="sxs-lookup"><span data-stu-id="eb590-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="eb590-104">**요약:** 비즈니스용 Skype 서버에서 DTMF(복합 주파수 부호) 명령의 키 매핑을 관리하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="eb590-105">전화 접속 회의 사용자는 전화기 키패드의 키를 눌러 DTMF(Dual-tone Multi-frequency) 명령을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="eb590-106">DTMF 명령을 사용하면 회의에 전화 접속한 사용자가 전화기의 키패드를 사용하여 음소거 설정 및 해제 또는 회의 잠금 설정 및 해제와 같은 회의 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="eb590-107">DTMF 명령에 사용되는 키를 관리하기 위해 비즈니스용 Skype 서버 관리 셸을 **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration** 및 **New-CsDialinConferencingDtmfConfiguration** cmdlet과 함께 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="eb590-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="eb590-108">사이트에 대해 새 DTMF 설정을 만들면 이 사이트 설정이 전역 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="eb590-109">DTMF 명령의 키 매핑 관리</span><span class="sxs-lookup"><span data-stu-id="eb590-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="eb590-110">RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="eb590-111">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb590-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="eb590-112">전화 접속 회의에 사용되는 DTMF 설정을 표시하려면 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="eb590-113">전화 접속 회의에 사용되는 DTMF 설정을 수정하려면 다음 cmdlet을 실행하고 변경할 각 옵션에 대해 누를 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="eb590-114">(선택 사항) 특정 사이트에 대해 DTMF 명령 집합을 추가로 만들려면 사이트 ID와 함께 **New-CsDialinConferencingDtmfConfiguration** cmdlet를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="eb590-115">다음은 모든 참가자를 음소거 및 음소거 해제하기 위해 누름 키와 공지 사항을 활성화 또는 비활성화하기 위해 누름 키를 바꾸는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="eb590-116">IDENTITY를 지정하지 않은 경우 이러한 변경 내용은 전역 DTMF 설정에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb590-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="eb590-117">자세한 내용은 [Get-CsDialInConferencingDtmfConfiguration,](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)및 [New-CsDialInConferencingDtmfConfiguration을](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb590-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
