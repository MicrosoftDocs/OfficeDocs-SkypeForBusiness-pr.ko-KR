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
ms.openlocfilehash: 5ff565c1d884fe2af9a49da6798e8c3e52cb38da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="2a91e-102">Lync Server 2013에서 위치 데이터베이스 구성</span><span class="sxs-lookup"><span data-stu-id="2a91e-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a91e-103">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2a91e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2a91e-p101">클라이언트가 네트워크 내에서 자신의 위치를 자동으로 감지하도록 하려면 먼저 위치 데이터베이스를 구성해야 합니다. 위치 데이터베이스를 구성하지 않은 상태에서 위치 정책의 **위치 필요**가 **예** 또는 **고지 사항**으로 설정되어 있으면 수동으로 위치를 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a91e-p101">To enable clients to automatically detect their location within a network, you first need to configure the location database. If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="2a91e-106">위치 데이터베이스를 구성하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a91e-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="2a91e-107">데이터베이스를 위치에 대한 네트워크 요소 매핑으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="2a91e-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="2a91e-108">ELIN (비상 위치 식별 번호) 게이트웨이를 사용 하는 경우 \<CompanyName\> 필드에 elin을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a91e-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="2a91e-109">E9-1-1 서비스 공급자가 유지 관리하는 MSAG(마스터 주소 가이드)에 대해 주소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2a91e-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="2a91e-110">업데이트된 데이터베이스를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2a91e-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a91e-111">또는 위치 데이터베이스 대신 사용할 수 있는 보조 위치 원본 데이터베이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a91e-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="2a91e-112">자세한 내용은 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013에서 보조 위치 정보 서비스 구성을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2a91e-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2a91e-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="2a91e-113">In This Section</span></span>

  - [<span data-ttu-id="2a91e-114">Lync Server 2013에서 위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="2a91e-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="2a91e-115">Lync Server 2013에서 주소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2a91e-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="2a91e-116">Lync Server 2013에서 위치 데이터베이스 게시</span><span class="sxs-lookup"><span data-stu-id="2a91e-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

