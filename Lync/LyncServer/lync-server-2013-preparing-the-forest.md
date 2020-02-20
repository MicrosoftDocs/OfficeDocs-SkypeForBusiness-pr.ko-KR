---
title: 'Lync Server 2013: 포리스트 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f8ff7bbbdd7e1f941b941e2c9446e5890b97dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="0a4ce-102">Lync Server 2013에 대 한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="0a4ce-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a4ce-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0a4ce-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0a4ce-104">포리스트 준비에서는 Lync Server 2013에서 사용 하기 위한 Active Directory 전역 설정 및 개체 및 Active Directory 유니버설 그룹을 만들고 Active directory 개체에 대 한 적절 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ce-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="0a4ce-105">포리스트 준비에서 만드는 유니버설 그룹 및 전역 설정 및 개체에 대 한 설명은 [Lync Server 2013에서 포리스트 준비로 인 한 변경 사항](lync-server-2013-changes-made-by-forest-preparation.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a4ce-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="0a4ce-106">또한 포리스트 준비에서는 Lync Server 2013에서 사용 되는 속성 집합 및 표시 지정자를 포함 하는 개체를 만들고 구성 컨테이너에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ce-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0a4ce-107">포리스트 준비 절차를 수행 하기 전에 스키마 준비 변경 내용이 모든 도메인 컨트롤러에 복제 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ce-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="0a4ce-108">복제가 완료되지 않은 경우 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ce-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="0a4ce-109">새 Lync Server 배포를 수행 하는 경우에는 구성 컨테이너에 전역 설정을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ce-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="0a4ce-110">이전 버전에서 업그레이드 하는 동안 여전히 System 컨테이너에 전역 설정을 저장 하는 경우에는 System 컨테이너를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ce-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="0a4ce-111">이 절차를 수행하려면 포리스트 루트 도메인의 Enterprise Admins 또는 Domain Admins 그룹 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a4ce-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a4ce-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="0a4ce-112">In This Section</span></span>

  - [<span data-ttu-id="0a4ce-113">Lync Server 2013에 대 한 포리스트 준비 실행</span><span class="sxs-lookup"><span data-stu-id="0a4ce-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="0a4ce-114">Cmdlet을 사용 하 여 Lync Server 2013에 대 한 포리스트 준비 되돌리기</span><span class="sxs-lookup"><span data-stu-id="0a4ce-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

