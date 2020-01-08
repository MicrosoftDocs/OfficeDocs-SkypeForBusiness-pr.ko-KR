---
title: 모든 Exchange UM 연락처 개체가 레거시 풀에서 제거 되었는지 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db8f4c55d863221c9a66d33a21bbe073bbc225a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="29550-102">모든 Exchange UM 연락처 개체가 레거시 풀에서 제거 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="29550-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29550-103">_**마지막으로 수정한 주제:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="29550-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="29550-104">**Ocsumutil** 도구나 **Get-csexumcontact** cmdlet 중 하나를 사용 하 여 Exchange UM Contact 개체가 레거시 Office Communications Server 2007 R2 풀에서 제거 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="29550-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="29550-105">**Ocsumutil** 은 다음 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29550-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="29550-106">% Program Files%\\Common Files\\Lync Server 2013\\에서\\ocsumutil을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="29550-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="29550-107">**Ocsumutil** 은 다음과 같은 사용자 계정에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29550-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="29550-108">RTCUniversalServerAdmins 및 RTCUniversalUserAdmins 그룹의 구성원 (Exchange Server 통합 메시징 설정을 읽을 수 있는 권한 포함)</span><span class="sxs-lookup"><span data-stu-id="29550-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="29550-109">지정 된 OU (조직 구성 단위) 컨테이너에서 연락처 개체를 만들 수 있는 도메인 권한</span><span class="sxs-lookup"><span data-stu-id="29550-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="29550-110">**Get-CsExumContact** cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [get-help (Get-csexumcontact)](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29550-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

