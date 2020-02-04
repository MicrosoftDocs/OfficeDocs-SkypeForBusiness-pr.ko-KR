---
title: 'Lync Server 2013: 위치 데이터베이스 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e42d73a5b7ac36439aca673ff68c03cc13f50f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="7f505-102">Lync Server 2013에서 위치 데이터베이스 게시</span><span class="sxs-lookup"><span data-stu-id="7f505-102">Publish the location database from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f505-103">_**마지막으로 수정한 주제:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="7f505-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="7f505-104">위치 데이터베이스에 추가한 새 위치는 게시 될 때까지 클라이언트에서 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f505-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="7f505-105">자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f505-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="7f505-106">**게시-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="7f505-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="7f505-107">비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우에도 ELIN을 PSTN (공개 통신 네트워크)의 ALI (자동 위치 확인) 데이터베이스에 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f505-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="7f505-108">PSTN 통신 회사에서는 레코드의 ELIN 특정 형식을 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f505-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="7f505-109">자세한 내용은 PSTN 캐리어에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f505-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="7f505-110">위치 정보 서비스 데이터베이스에서 레코드를 내보내고 필요에 따라 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f505-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="7f505-111">위치 데이터베이스를 게시 하려면</span><span class="sxs-lookup"><span data-stu-id="7f505-111">To publish the location database</span></span>

  - <span data-ttu-id="7f505-112">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f505-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="7f505-113">다음 cmdlet을 실행 하 여 위치 데이터베이스를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f505-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

