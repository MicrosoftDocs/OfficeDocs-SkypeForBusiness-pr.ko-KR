---
title: 'Lync Server 2013: (선택 사항) DTMF 명령에 대 한 키 매핑 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcf6f6b2dd65d9429bf23397baff5bbe072800f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="29bf4-102">반드시 Lync Server 2013의 DTMF 명령에 대 한 키 매핑 수정</span><span class="sxs-lookup"><span data-stu-id="29bf4-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29bf4-103">_**마지막으로 수정 된 항목:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="29bf4-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="29bf4-p101">전화 접속 회의 사용자는 전화기 키패드의 키를 눌러 DTMF(Dual-tone Multi-frequency) 명령을 수행할 수 있습니다. DTMF 명령을 사용하면 회의에 전화 접속한 사용자가 전화기의 키패드를 사용하여 음소거 설정 및 해제 또는 회의 잠금 설정 및 해제와 같은 회의 설정을 제어할 수 있습니다. cmdlet를 사용하여 DTMF 명령에 사용되는 키를 수정할 수 있습니다. 이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. You can use cmdlets to modify the keys used for the DTMF commands. This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29bf4-108">이러한 cmdlet 및 가능한 DTMF 옵션에 대 한 자세한 내용은 Lync Server Management Shell 설명서 또는 Lync Server 관리 셸 명령줄 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29bf4-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="29bf4-109">DTMF 명령의 키 매핑을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="29bf4-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="29bf4-110">**RTCUniversalServerAdmins** 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="29bf4-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="29bf4-112">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="29bf4-113">이 cmdlet는 전화 접속 회의에 사용되는 DTMF 설정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="29bf4-114">다음 cmdlet를 실행하고 변경할 각 옵션에 대해 누를 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="29bf4-115">이 cmdlet는 전화 접속 회의에 사용되는 DTMF 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="29bf4-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="29bf4-p102">이 예에서는 알림을 사용하거나 사용하지 않도록 설정하기 위해 누르는 키와 모든 참가자에 대해 음소거를 설정 및 해제하기 위해 누르는 키를 바꿉니다. Identity가 지정되지 않았으므로 이 변경은 전역 DTMF 설정에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-p102">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="29bf4-119">(선택 사항) 특정 사이트에 대해 DTMF 명령 집합을 추가로 만들려면 사이트 ID와 함께 **New-CsDialinConferencingDtmfConfiguration** cmdlet를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="29bf4-120">사이트에 대해 새 DTMF 설정을 만들면 이 사이트 설정이 전역 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="29bf4-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="29bf4-121">자세한 내용은 Lync Server 관리 셸 설명서 또는 Lync Server 관리 셸 명령줄 도움말을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29bf4-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

