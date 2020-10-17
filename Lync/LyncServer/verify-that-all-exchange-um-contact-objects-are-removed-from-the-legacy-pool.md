---
title: 레거시 풀에서 모든 Exchange UM 대화 상대 개체가 제거 되었는지 확인
description: 레거시 풀에서 모든 Exchange UM 대화 상대 개체가 제거 되었는지 확인 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af5dea6cf746c55d8fecf074e132f721c380de1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555514"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="015a8-103">레거시 풀에서 모든 Exchange UM 대화 상대 개체가 제거 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="015a8-103">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="015a8-104">_**마지막으로 수정 된 항목:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="015a8-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="015a8-105">**Ocsumutil** 도구 또는 **get-help** cmdlet을 사용 하 여 Exchange UM 대화 상대 개체가 레거시 Office Communications Server 2007 R2 풀에서 제거 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="015a8-105">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="015a8-106">**OCSUmUtil**은 다음 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="015a8-106">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="015a8-107">% Program Files% \\ Common files \\ Lync Server 2013 \\ 지원 \\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="015a8-107">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="015a8-108">**OCSUmUtil**은 다음을 포함하는 사용자 계정으로부터 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="015a8-108">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="015a8-109">RTCUniversalServerAdmins 및 RTCUniversalUserAdmins 그룹의 구성원(Exchange Server 통합 메시징 설정을 읽을 수 있는 권한 포함)</span><span class="sxs-lookup"><span data-stu-id="015a8-109">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="015a8-110">지정된 OU(조직 구성 단위) 컨테이너에 대화 상대 개체를 만드는 도메인 권한</span><span class="sxs-lookup"><span data-stu-id="015a8-110">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="015a8-111">**Get-help** cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서에서 [get-help-csexumcontact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="015a8-111">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

