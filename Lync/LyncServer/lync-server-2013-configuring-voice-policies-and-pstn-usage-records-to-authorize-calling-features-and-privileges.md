---
title: 'Lync Server 2013: 통화 기능 및 권한을 부여하도록 음성 정책 및 PSTN 사용 레코드 구성'
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
ms.openlocfilehash: 7b9f7da3f8560ae0a897211405d686d9ed35101e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="26a74-102">Lync Server 2013에서 통화 기능 및 권한을 부여하도록 음성 정책 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="26a74-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26a74-103">_**마지막으로 수정한 주제:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="26a74-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="26a74-104">*음성 정책은* 호출 기능 집합을 활성화 하 고 하나 이상의 PSTN 사용 레코드를 연결 하 여 정책에 할당 된 사용자의 호출 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="26a74-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="26a74-105">음성 정책 범위는 *사이트* (네트워크 사이트에 대 한 기본 기능 및 사용 권한을 정의) 또는 *사용자* (사용자 또는 그룹 기준으로 할당할 기능 및 사용 권한을 정의 하는) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26a74-105">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis).</span></span> <span data-ttu-id="26a74-106">음성 정책에 할당 되지 않은 사용자는 해당 제품에 설치 된 기본 음성 정책 인 전역 정책에 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26a74-106">Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26a74-107">자세한 내용은 계획 설명서의 <A href="lync-server-2013-voice-policies.md">Lync Server 2013에서 음성 정책을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26a74-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="26a74-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="26a74-108">In This Section</span></span>

  - [<span data-ttu-id="26a74-109">Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="26a74-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="26a74-110">Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="26a74-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="26a74-111">Lync Server 2013에서 음성 메일 esc 구성</span><span class="sxs-lookup"><span data-stu-id="26a74-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

