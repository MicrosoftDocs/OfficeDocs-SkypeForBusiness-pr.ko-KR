---
title: 'Lync Server 2013: 공통 영역 전화 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 900beb4f96fd71e0e6a4ded40d776f1e7d356529
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="84bf0-102">Lync Server 2013에서 공통 영역 전화 정보 보기</span><span class="sxs-lookup"><span data-stu-id="84bf0-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84bf0-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="84bf0-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="84bf0-104">**CsCommonAreaPhone** cmdlet을 사용 하 여 조직에서 사용 하도록 구성 된 공통 영역 전화에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bf0-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="84bf0-105">매개 변수 없이 사용 하면이 cmdlet은 모든 공통 지역 전화에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="84bf0-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="84bf0-106">선택적 매개 변수는 다양 한 방법으로 정보를 필터링 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="84bf0-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="84bf0-107">예를 들어 지정 된 조직 구성 단위 (OU) 또는 지정 된 건물에 위치한 모든 연락처 개체에 연락처 개체가 있는 공통 영역 전화기를 모두 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bf0-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="84bf0-108">**Get-CsCommonAreaPhone** 매개 변수에 대 한 자세한 내용은 [get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84bf0-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="84bf0-109">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 **CsCommonAreaPhone** 를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84bf0-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="84bf0-110">모든 공통 지역 전화에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="84bf0-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="84bf0-111">모든 공통 지역 전화에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="84bf0-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="84bf0-112">다음과 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84bf0-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="84bf0-113">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목을 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="84bf0-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

