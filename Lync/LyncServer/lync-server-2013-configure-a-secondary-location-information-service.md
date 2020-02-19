---
title: 'Lync Server 2013: 보조 위치 정보 서비스 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8255e23a2478329588a3383d8c3999e60d4aea21
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="3fb67-102">Lync Server 2013에서 보조 위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="3fb67-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fb67-103">_**마지막으로 수정 된 항목:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3fb67-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3fb67-104">Lync Server 2013는 SLS (보조 위치 원본) 데이터베이스를 가리키도록 위치 정보 서비스를 지정 하는 데 사용할 수 있는 웹 서비스 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb67-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="3fb67-105">SLS 데이터베이스에 연결 되는 웹 서비스 인터페이스는 위치 정보 서비스 WSDL을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb67-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="3fb67-106">위치 데이터베이스와 보조 위치 데이터베이스를 모두 구성 하는 경우에는 위치 정보 서비스가 먼저 위치 데이터베이스를 쿼리하고 일치 하는 항목이 없으면 클라이언트의 위치 요청을 SLS 데이터베이스에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb67-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="3fb67-107">SLS에 위치가 있으면 위치 정보 서비스에서 해당 위치를 클라이언트로 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3fb67-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="3fb67-108">자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3fb67-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="3fb67-109">**Set-cswebserviceconfiguration**</span><span class="sxs-lookup"><span data-stu-id="3fb67-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="3fb67-110">보조 위치 데이터베이스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="3fb67-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="3fb67-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb67-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3fb67-112">다음 cmdlet을 실행하여 보조 위치 데이터베이스의 위치에 대해 URL을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3fb67-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

