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
ms.openlocfilehash: 8a485ba2a406fd762d70ba4e8ff621d2d6af3801
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="94a78-102">Lync Server 2013에 대한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="94a78-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94a78-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="94a78-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="94a78-104">포리스트 준비는 Lync Server 2013에서 사용할 Active Directory 전역 설정 및 개체 및 Active Directory 유니버설 그룹을 만들며 Active Directory 개체에 대 한 적절 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a78-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="94a78-105">포리스트 준비로 만든 유니버설 그룹과 전역 설정 및 개체에 대 한 설명은 [Lync Server 2013의 포리스트 준비에서 변경한 내용을](lync-server-2013-changes-made-by-forest-preparation.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="94a78-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="94a78-106">또한 포리스트 준비는 Lync Server 2013에서 사용 되는 속성 집합 및 표시 지정자를 포함 하는 개체를 만들고 구성 컨테이너에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a78-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94a78-107">포리스트 준비 절차를 수행 하기 전에 스키마 준비 변경 내용이 모든 도메인 컨트롤러로 복제 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a78-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="94a78-108">복제가 완료 되지 않은 경우 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a78-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="94a78-109">새 Lync Server 배포를 수행 하는 경우 구성 컨테이너에 전역 설정을 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a78-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="94a78-110">이전 버전에서 업그레이드 하는 경우 여전히 시스템 컨테이너에 전역 설정을 저장 하는 경우 시스템 컨테이너를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a78-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="94a78-111">이 절차를 수행 하려면 포리스트 루트 도메인의 엔터프라이즈 관리자 또는 Domain Admins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a78-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="94a78-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="94a78-112">In This Section</span></span>

  - [<span data-ttu-id="94a78-113">Lync Server 2013에 대한 포리스트 준비 실행</span><span class="sxs-lookup"><span data-stu-id="94a78-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="94a78-114">Lync Server 2013에 대해 Cmdlet을 사용하여 포리스트 준비 되돌리기</span><span class="sxs-lookup"><span data-stu-id="94a78-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

