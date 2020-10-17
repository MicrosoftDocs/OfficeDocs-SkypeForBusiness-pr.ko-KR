---
title: 'Lync Server 2013: 위치 가져오기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e5b3a6f9e781efbc3c8b7672ad28f1753490e17
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529745"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="43ad3-102">Lync Server 2013에서 위치 가져오기</span><span class="sxs-lookup"><span data-stu-id="43ad3-102">Acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43ad3-103">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="43ad3-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="43ad3-104">Lync Server 2013 E9-1-1 배포에서는 내부적으로 연결 된 각 Lync 또는 Lync Phone Edition 클라이언트에서 자체 위치를 적극적으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="43ad3-105">SIP 등록이 완료 되 면 클라이언트는 복제 된 SQL Server 데이터베이스에서 지 원하는 웹 서비스인 위치 정보 서비스에 대 한 위치 요청에 대해 자신에 대해 알고 있는 모든 네트워크 연결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="43ad3-106">각 중앙 사이트 풀에는 네트워크 정보를 사용 하 여 일치 하는 위치에 대 한 레코드를 쿼리 하는 위치 정보 서비스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="43ad3-107">일치 하는 항목이 있으면 위치 정보 서비스가 클라이언트에 대 한 위치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="43ad3-108">일치 하는 항목이 없으면 위치 정책 설정에 따라 사용자에 게 위치를 수동으로 입력 하 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="43ad3-109">위치 데이터는 IETF (인터넷 엔지니어링 작업 포스) 표준화 XML 형식인 현재 상태 정보 데이터 형식 위치 개체 (PIDF-낮음)로 클라이언트에 다시 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="43ad3-110">Lync Server 클라이언트는 비상 통화의 일부로 PIDF-로 데이터를 포함 하며,이 데이터를 E9-1-1 서비스 공급자가 사용 하 여 적절 한 PSAP를 확인 하 고 해당 전화를 올바른 ESQK와 함께 해당 PSAP로 라우트 하 여 해당 통화 위치를 가져올 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="43ad3-111">다음 다이어그램은 Lync Server 클라이언트에서 위치를 가져오는 방법을 보여 줍니다 (타사 클라이언트 MAC 주소 기반 location 방법 제외).</span><span class="sxs-lookup"><span data-stu-id="43ad3-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="43ad3-112">![클라이언트에서 위치 다이어그램을 가져오는 방법](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "클라이언트에서 위치 다이어그램을 가져오는 방법")</span><span class="sxs-lookup"><span data-stu-id="43ad3-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="43ad3-113">클라이언트가 위치를 확보하기 위해서는 다음 단계가 수행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="43ad3-114">관리자가 네트워크 와이어 맵 매핑 (이 경우 다양 한 유형의 네트워크 주소를 해당 긴급 응답 위치 (erls)에 매핑하는 테이블))로 위치 정보 서비스 데이터베이스를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="43ad3-p102">SIP 트렁크 E9-1-1 서비스 공급자를 사용하는 경우 관리자는 E9-1-1 서비스 공급자가 유지 관리하는 MSAG(마스터 주소 가이드) 데이터베이스에 대해 ERL의 주소 부분이 올바른지 확인합니다. ELIN 게이트웨이를 사용하는 경우에는 관리자가 PSTN 통신 회사에서 ELIN을 ALI(Automatic Location Identification) 데이터베이스에 업로드했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="43ad3-117">등록 중 또는 네트워크가 변경 될 때마다 내부 연결 된 클라이언트는 클라이언트에서 검색 한 네트워크 주소를 포함 하는 위치 요청을 위치 정보 서비스에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="43ad3-118">위치 정보 서비스에서 게시 된 레코드에 위치를 쿼리 하 고 일치 하는 항목이 발견 되 면 ERL를 PIDF-로 형식으로 클라이언트에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ad3-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

