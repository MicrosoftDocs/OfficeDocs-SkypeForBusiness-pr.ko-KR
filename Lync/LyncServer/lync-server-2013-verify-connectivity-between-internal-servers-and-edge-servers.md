---
title: 내부 서버와 에지 서버 간의 연결 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3868462036312be97484e41c69b51ae022b57c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="2e10c-102">Lync Server 2013에서 내부 서버와 에지 서버 간의 연결 확인</span><span class="sxs-lookup"><span data-stu-id="2e10c-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e10c-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2e10c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2e10c-104">Lync Server 2013에서는 Edge 서버와 내부 서버 간의 연결을 확인 하는 데 도움이 되는 별도의 유효성 검사 마법사가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e10c-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="2e10c-105">Lync Server 2013에 Edge 서버를 설치할 때 연결의 유효성 검사가 자동으로 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e10c-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="2e10c-106">중앙 관리 저장소가 있는 내부 컴퓨터에서 Windows PowerShell **CsManagementStoreReplicationStatus** cmdlet을 실행 하 여 edge에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다 (또는 Lync Server 2013 Core 구성 요소 (ocscore. msi)가 설치 되어 있는 도메인에 가입 된 컴퓨터).</span><span class="sxs-lookup"><span data-stu-id="2e10c-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="2e10c-107">초기 결과에는 복제용으로 "True" 대신 상태가 "False"로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e10c-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="2e10c-108">이 경우 **CsManagementStoreReplication** cmdlet을 실행 하 고 **Get-CsManagementStoreReplicationStatus** 를 다시 실행 하기 전에 복제를 완료 하는 데 걸리는 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e10c-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="2e10c-109">Office Communications Server 원격 연결 분석기를 사용 하 여 원격 사용자 연결을 확인 하는 등 외부 사용자 연결을 개별적으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e10c-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="2e10c-110">자세한 내용은 [Lync Server 2013에서 외부 사용자에 대 한 연결 확인](lync-server-2013-verify-connectivity-for-external-users.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2e10c-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

