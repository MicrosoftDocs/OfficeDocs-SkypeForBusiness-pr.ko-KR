---
title: 레거시 풀에서 모든 Exchange UM 대화 상대 개체가 제거 되었는지 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7815f78dfa5f2b4aab3f09102a9948498c20cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="e3bf2-102">레거시 풀에서 모든 Exchange UM 대화 상대 개체가 제거 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="e3bf2-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3bf2-103">_**마지막으로 수정 된 항목:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="e3bf2-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="e3bf2-104">**Ocsumutil** 도구 또는 **get-help** cmdlet을 사용 하 여 Exchange UM 대화 상대 개체가 레거시 Office Communications Server 2007 R2 풀에서 제거 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="e3bf2-105">**OCSUmUtil**은 다음 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="e3bf2-106">% Program Files%\\Common Files\\Lync Server 2013\\지원\\ocsumutil</span><span class="sxs-lookup"><span data-stu-id="e3bf2-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="e3bf2-107">**OCSUmUtil**은 다음을 포함하는 사용자 계정으로부터 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="e3bf2-108">RTCUniversalServerAdmins 및 RTCUniversalUserAdmins 그룹의 구성원(Exchange Server 통합 메시징 설정을 읽을 수 있는 권한 포함)</span><span class="sxs-lookup"><span data-stu-id="e3bf2-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="e3bf2-109">지정된 OU(조직 구성 단위) 컨테이너에 대화 상대 개체를 만드는 도메인 권한</span><span class="sxs-lookup"><span data-stu-id="e3bf2-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="e3bf2-110">**Get-help** cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서에서 [get-help-csexumcontact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3bf2-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

