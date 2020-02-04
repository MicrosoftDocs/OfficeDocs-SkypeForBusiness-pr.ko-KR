---
title: 'Lync Server 2013: 사용 권한 부여'
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
ms.openlocfilehash: ccfdf804fc9052ac69b383d0f8cd3321222e79a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="42068-102">Lync Server 2013에서 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="42068-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42068-103">_**마지막으로 수정한 주제:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="42068-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="42068-104">설치의 경우 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 대 한 사용 권한을 부여 하 여 해당 OU의 RTCUniversalServerAdmins 그룹 구성원이 지정 된 도메인에 Lync Server 2013을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42068-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="42068-105">OU에 대 한 사용 권한을 부여 하면 다음 사용 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42068-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="42068-106">자세한</span><span class="sxs-lookup"><span data-stu-id="42068-106">Read</span></span>

  - <span data-ttu-id="42068-107">작성</span><span class="sxs-lookup"><span data-stu-id="42068-107">Write</span></span>

  - <span data-ttu-id="42068-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="42068-108">ReadSPN</span></span>

  - <span data-ttu-id="42068-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="42068-109">WriteSPN</span></span>

<span data-ttu-id="42068-110">관리의 경우 포리스트 준비를 통해 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원 일 필요 없이 Ou에 액세스할 수 있도록 지정 된 Ou에 대 한 사용 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42068-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="42068-111">지정 된 OU에 추가 되는 권한은 **CsAdDomain** cmdlet이 컴퓨터 및 사용자 OU 컨테이너에 추가 하는 권한과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="42068-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42068-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="42068-112">In This Section</span></span>

  - [<span data-ttu-id="42068-113">Lync Server 2013에서 설치 권한 부여</span><span class="sxs-lookup"><span data-stu-id="42068-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="42068-114">Lync Server 2013에서 조직 구성 단위 권한 부여</span><span class="sxs-lookup"><span data-stu-id="42068-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

