---
title: 'Lync Server 2013: 위치 데이터베이스 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2b15f0c679e9380a1f1a624f00f6c19384878fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="a2acf-102">Lync Server 2013에서 위치 데이터베이스 구성</span><span class="sxs-lookup"><span data-stu-id="a2acf-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2acf-103">_**마지막으로 수정한 주제:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a2acf-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a2acf-104">클라이언트가 네트워크 내에서 해당 위치를 자동으로 검색할 수 있도록 하려면 먼저 위치 데이터베이스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-104">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> <span data-ttu-id="a2acf-105">위치 데이터베이스를 구성 하지 않고 위치 정책에 **필요한 위치가** **예** 또는 **부인**로 설정 된 경우 사용자에 게 위치를 수동으로 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-105">If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="a2acf-106">위치 데이터베이스를 구성 하려면 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="a2acf-107">네트워크 요소를 위치에 매핑하는 방법으로 데이터베이스를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="a2acf-108">비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우 \<CompanyName\> 필드에 elin을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="a2acf-109">E9-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 거리 주소 가이드)에 대해 주소의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="a2acf-110">업데이트 된 데이터베이스를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2acf-111">또는 위치 데이터베이스에 배치할 때 사용할 수 있는 보조 위치 원본 데이터베이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2acf-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="a2acf-112">자세한 내용은 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013에서 보조 위치 정보 서비스 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a2acf-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2acf-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a2acf-113">In This Section</span></span>

  - [<span data-ttu-id="a2acf-114">Lync Server 2013에서 위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="a2acf-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="a2acf-115">Lync Server 2013에서 주소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a2acf-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="a2acf-116">Lync Server 2013에서 위치 데이터베이스 게시</span><span class="sxs-lookup"><span data-stu-id="a2acf-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

