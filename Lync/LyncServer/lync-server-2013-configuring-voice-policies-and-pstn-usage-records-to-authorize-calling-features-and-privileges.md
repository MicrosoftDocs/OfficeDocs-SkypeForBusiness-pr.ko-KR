---
title: 'Lync Server 2013: 호출 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드 구성'
description: 'Lync Server 2013: 통화 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies and PSTN usage records to authorize calling features and privileges
ms:assetid: 63f22010-a3d7-4cbd-86e8-6fc0e13c2b84
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398450(v=OCS.15)
ms:contentKeyID: 48184307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a12c9c64c3f02effba7c7709321eda91350ebb75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542284"
---
# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="75556-103">Lync Server 2013에서 호출 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="75556-103">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75556-104">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="75556-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="75556-105">*음성 정책*은 정책이 지정되는 사용자의 통화 기능 및 사용 권한을 정의하기 위해 하나 이상의 PSTN 사용 레코드를 연결하며 일련의 통화 기능을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="75556-105">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="75556-p101">음성 정책 범위는 *사이트*(네트워크 사이트에 대한 기본 기능 및 사용 권한 정의) 또는 *사용자*(사용자별 또는 그룹 기준으로 지정할 기능 및 사용 권한 정의)일 수 있습니다. 음성 정책에 지정되지 않은 사용자는 자동으로 글로벌 정책(제품과 함께 설치되는 기본 음성 정책)에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="75556-p101">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis). Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75556-108">자세한 내용은 계획 설명서에서 <A href="lync-server-2013-voice-policies.md">Lync Server 2013의 음성 정책</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="75556-108">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="75556-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="75556-109">In This Section</span></span>

  - [<span data-ttu-id="75556-110">Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="75556-110">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="75556-111">Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="75556-111">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="75556-112">Lync Server 2013에서 음성 메일 이스케이프 구성</span><span class="sxs-lookup"><span data-stu-id="75556-112">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

