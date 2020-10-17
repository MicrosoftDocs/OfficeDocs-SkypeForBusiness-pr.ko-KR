---
title: 'Lync Server 2013: 사용 권한 부여'
description: 'Lync Server 2013: 사용 권한 부여'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bdb2b1ef39b85caa89c7597f455e6e4fc08e44e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554504"
---
# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="bf011-103">Lync Server 2013에서 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="bf011-103">Granting permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf011-104">_**마지막으로 수정 된 항목:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="bf011-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="bf011-105">설치를 위해 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 사용 권한을 부여 하 여 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 지정 된 도메인에 Lync Server 2013을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf011-105">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="bf011-106">OU에 대 한 사용 권한을 부여 하면 다음과 같은 사용 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf011-106">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="bf011-107">읽기</span><span class="sxs-lookup"><span data-stu-id="bf011-107">Read</span></span>

  - <span data-ttu-id="bf011-108">쓰기</span><span class="sxs-lookup"><span data-stu-id="bf011-108">Write</span></span>

  - <span data-ttu-id="bf011-109">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="bf011-109">ReadSPN</span></span>

  - <span data-ttu-id="bf011-110">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="bf011-110">WriteSPN</span></span>

<span data-ttu-id="bf011-111">관리의 경우 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원 일 필요 없이 Ou에 액세스할 수 있도록 지정 된 Ou에 사용 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf011-111">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="bf011-112">지정 된 OU에 추가 되는 사용 권한은 컴퓨터 및 사용자 OU 컨테이너에 추가 되는 **CsAdDomain** cmdlet의 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="bf011-112">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf011-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="bf011-113">In This Section</span></span>

  - [<span data-ttu-id="bf011-114">Lync Server 2013에서 설치 권한 부여</span><span class="sxs-lookup"><span data-stu-id="bf011-114">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="bf011-115">Lync Server 2013에서 조직 구성 단위 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="bf011-115">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

