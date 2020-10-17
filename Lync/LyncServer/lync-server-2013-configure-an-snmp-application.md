---
title: 'Lync Server 2013: SNMP 응용 프로그램 구성'
description: 'Lync Server 2013: SNMP 응용 프로그램을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7374b61ad85d7ddcb40ef1db535e17f86dea58f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546704"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="06fff-103">Lync Server 2013에서 SNMP 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="06fff-103">Configure an SNMP application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06fff-104">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="06fff-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="06fff-105">Lync Server 2013에는 위치 정보 서비스를 포트 및 스위치 정보와 MAC 주소와 일치 하는 SNMP (Simple Network Management Protocol) 응용 프로그램에 연결 하는 데 사용할 수 있는 표준 웹 서비스 인터페이스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-105">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="06fff-106">SNMP 응용 프로그램을 설치 하 고 위치 정보 서비스가 위치 데이터베이스에서 일치 하는 항목을 찾지 못하는 경우 위치 정보 서비스는 클라이언트에서 제공 하는 MAC 주소를 사용 하 여 응용 프로그램을 자동으로 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="06fff-107">그런 다음 위치 정보 서비스는 SNMP 응용 프로그램에서 반환 하는 포트 및 스위치 정보를 사용 하 여 위치 데이터베이스를 다시 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="06fff-108">자세한 내용은 [set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="06fff-108">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06fff-109">Windows 8을 실행 하는 컴퓨터에서는 MAC 주소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-109">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="06fff-110">SNMP 응용 프로그램 URL을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="06fff-110">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="06fff-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="06fff-112">다음 cmdlet를 실행하여 SNMP 응용 프로그램에 대한 URL을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="06fff-112">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

