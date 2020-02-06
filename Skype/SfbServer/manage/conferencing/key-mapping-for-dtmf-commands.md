---
title: 비즈니스용 Skype 서버의 DTMF 명령에 대 한 키 매핑 관리
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
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: '요약: 비즈니스용 Skype 서버에서 DTMF 멀티 주파수) 명령의 키 매핑을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: fdb9846da81c4029fa67df606fa021397a46b3ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818539"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="7f422-103">비즈니스용 Skype 서버의 DTMF 명령에 대 한 키 매핑 관리</span><span class="sxs-lookup"><span data-stu-id="7f422-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="7f422-104">**요약:** 비즈니스용 Skype 서버의 DTMF (듀얼 톤 다중 주파수) 명령의 키 매핑을 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="7f422-105">전화 접속 회의 사용자는 전화 키패드의 키를 눌러 이중 톤 다중 주파수 (DTMF) 명령을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="7f422-106">DTMF 명령을 사용 하면 전화 회의에 전화를 거는 사용자가 전화기에서 키패드를 사용 하 여 전화를 걸고 음소거 해제 하거나, 전화를 잠그거나 잠금 취소 하는 등의 회의 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="7f422-107">DTMF 명령에 사용 되는 키를 관리 하려면 **CsDialinConferencingDtmfConfiguration**, **CsDialinConferencingDtmfConfiguration**및 **CsDialinConferencingDtmfConfiguration** Cmdlet을 사용 하 여 비즈니스용 Skype Server Management Shell을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f422-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="7f422-108">사이트에 대 한 새 DTMF 설정을 만들면 사이트 설정이 전역 설정 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="7f422-109">DTMF 명령의 키 매핑 관리</span><span class="sxs-lookup"><span data-stu-id="7f422-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="7f422-110">RTCUniversalServerAdmins 그룹의 구성원 또는 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="7f422-111">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7f422-112">전화 접속 회의에 사용 되는 DTMF 설정을 보려면 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="7f422-113">전화 접속 회의에 사용 되는 DTMF 설정을 수정 하려면 다음 cmdlet을 실행 하 고 변경 하려는 각 옵션에 대해 누를 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="7f422-114">) 특정 사이트에 대 한 추가 DTMF 명령 집합을 만들려면 사이트 id와 함께 **CsDialinConferencingDtmfConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="7f422-115">다음 예에서는 알림을 사용 하거나 사용 하지 않도록 누른 키와 모든 참가자를 음소거 및 음소거 해제 하기 위해 누른 키를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="7f422-116">Id가 지정 되지 않았으므로 이러한 변경 내용은 전역 DTMF 설정에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f422-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="7f422-117">자세한 내용은 [get-help, CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)및 [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f422-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

