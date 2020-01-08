---
title: 'Lync Server 2013: 개선 된 현재 상태 개인 정보 모드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="689cb-102">Lync Server 2013에서 향상 된 현재 상태 개인 정보 모드 구성</span><span class="sxs-lookup"><span data-stu-id="689cb-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="689cb-103">_**마지막으로 수정한 주제:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="689cb-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="689cb-104">향상 된 현재 상태 개인 정보 취급 모드가 있으면 사용자는 자신의 현재 상태 정보를 제한 하 여 Lync 2013 대화 상대 목록에 나열 된 연락처에만 표시 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="689cb-105">**CsPrivacyConfiguration** 및 **CsPrivacyConfiguration** cmdlet에는이 옵션을 제어 하는 EnablePrivacyMode 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="689cb-106">EnablePrivacyMode가 True로 설정 되 면 Lync 2013 상태 옵션에서 현재 상태 정보를 연락처로 제한 하는 옵션을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="689cb-107">EnablePrivacyMode가 False로 설정 되 면 사용자는 항상 모든 사용자가 현재 상태 정보를 볼 수 있도록 허용 하거나 관리자가 개인 정보 모드에 대해 변경한 내용을 준수 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="689cb-108">Lync 2013 및 Lync 2010 개인 정보 설정은 이전 버전 (Microsoft Office Communicator 2007 R2 또는 Microsoft Office Communicator 2007)에서 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="689cb-109">이전 버전의 Office Communicator에서 로그인이 허용 된 경우 Lync 2013 사용자의 상태, 연락처 정보 또는 사진을 볼 수 있는 권한이 없는 사용자가 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="689cb-110">또한 나중에 이전 버전의 Communicator를 사용 하 여 로그인 하는 경우 Lync 2013 사용자의 개인 정보 설정이 재설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="689cb-111">이러한 이유로 인해 마이그레이션 시나리오에서 향상 된 현재 상태 개인 정보 모드를 사용 하도록 설정 하기 전에 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="689cb-112">모든 사용자에 게 Lync 2013이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="689cb-113">이전 버전의 Communicator가 로그인 하지 못하도록 클라이언트 버전 정책 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="689cb-114">향상 된 현재 상태 개인 정보 모드 사용</span><span class="sxs-lookup"><span data-stu-id="689cb-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="689cb-115">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="689cb-116">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="689cb-117">이 명령은 조직에서 현재 사용 중인 모든 개인 정보 구성 설정에 대해 개인 정보 모드를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="689cb-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="689cb-118">Lync Server의 향상 된 현재 상태 개인 정보 모드 정책 구성에서 lync 2013 클라이언트에 대 한 대화 상대의 현재 상태를 관리 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료에서 [Lync server의 향상 된 현재 상태 개인 정보 취급 모드를 사용 하도록 설정 하 여 일부 Lync 대화 상대의 현재 상태를 "](http://support.microsoft.com/kb/3020057)</span><span class="sxs-lookup"><span data-stu-id="689cb-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](http://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="689cb-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="689cb-119">See Also</span></span>


[<span data-ttu-id="689cb-120">Get-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="689cb-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="689cb-121">새로운 CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="689cb-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="689cb-122">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="689cb-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

