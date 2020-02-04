---
title: 'Lync Server 2013: (선택 사항) DTMF 명령에 대한 키 매핑 수정'
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
ms.openlocfilehash: 036092f1199ad0e361f8509b36930410685ece21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="6ab47-102">(선택 사항) Lync Server 2013에서 DTMF 명령에 대한 키 매핑 수정</span><span class="sxs-lookup"><span data-stu-id="6ab47-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ab47-103">_**마지막으로 수정한 주제:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6ab47-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6ab47-104">전화 접속 회의 사용자는 전화 키패드의 키를 눌러 이중 톤 다중 주파수 (DTMF) 명령을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="6ab47-105">DTMF 명령을 사용 하면 전화 회의에 전화를 거는 사용자가 전화기에서 키패드를 사용 하 여 전화를 걸고 음소거 해제 하거나, 전화를 잠그거나 잠금 취소 하는 등의 회의 설정을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="6ab47-106">Cmdlet을 사용 하 여 DTMF 명령에 사용 되는 키를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="6ab47-107">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ab47-108">이러한 cmdlet 및 가능 DTMF 옵션에 대 한 자세한 내용은 Lync Server 관리 셸 설명서 또는 Lync Server 관리 셸 명령줄 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ab47-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="6ab47-109">DTMF 명령의 키 매핑을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="6ab47-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="6ab47-110">**RTCUniversalServerAdmins** 그룹의 구성원 또는 **Cs-Serveradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="6ab47-111">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6ab47-112">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="6ab47-113">이 cmdlet은 전화 접속 회의에 사용 되는 DTMF 설정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="6ab47-114">다음 cmdlet을 실행 하 고 변경 하려는 각 옵션에 대해 누를 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="6ab47-115">이 cmdlet은 전화 접속 회의에 사용 되는 DTMF 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="6ab47-116">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="6ab47-117">이 예제에서는 알림을 사용 하거나 사용 하지 않도록 누른 키와 모든 참가자를 음소거 및 음소거 해제 하기 위해 누른 키를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="6ab47-118">Id가 지정 되지 않았으므로 이러한 변경 내용은 전역 DTMF 설정에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="6ab47-119">) 특정 사이트에 대 한 추가 DTMF 명령 집합을 만들려면 사이트 id와 함께 **CsDialinConferencingDtmfConfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="6ab47-120">사이트에 대 한 새 DTMF 설정을 만들면 사이트 설정이 전역 설정 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ab47-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="6ab47-121">자세한 내용은 Lync Server 관리 셸 설명서 또는 Lync Server 관리 셸 명령줄 도움말을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ab47-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

