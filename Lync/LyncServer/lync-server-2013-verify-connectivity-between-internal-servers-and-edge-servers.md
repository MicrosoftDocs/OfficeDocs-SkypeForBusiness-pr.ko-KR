---
title: 내부 서버와에 지 서버 간의 연결 확인
description: 내부 서버와에 지 서버 간의 연결을 확인 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f86f87428d7eaf91b8f70422cfee712584252fad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547134"
---
# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="1bd43-103">Lync Server 2013에서 내부 서버와에 지 서버 간의 연결 확인</span><span class="sxs-lookup"><span data-stu-id="1bd43-103">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bd43-104">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1bd43-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1bd43-105">Lync Server 2013에서는 Edge 서버와 내부 서버 간의 연결 유효성을 검사 하는 데 도움이 되는 별도의 유효성 검사 마법사를 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd43-105">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="1bd43-106">Lync Server 2013에서는에 지 서버를 설치할 때 연결 유효성 검사가 자동으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bd43-106">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="1bd43-107">중앙 관리 저장소가 있는 내부 컴퓨터에서 Windows PowerShell **get-csmanagementstorereplicationstatus** cmdlet을 실행 하 여 (또는 Lync Server 2013 Core Components (OcsCore.msi)가 설치 된 도메인에 가입 된 컴퓨터에 있는 경우에는 edge로의 구성 정보 복제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd43-107">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="1bd43-108">초기 결과에서는 복제 상태가 "True"가 아닌 "False"로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd43-108">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="1bd43-109">이 경우 **Invoke-CsManagementStoreReplication** cmdlet을 실행하고 복제가 완료될 때까지 기다린 후에 **Get-CsManagementStoreReplicationStatus**를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1bd43-109">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="1bd43-110">외부 사용자 연결은 별도로 확인할 수 있으며, Office Communications Server 원격 연결 분석기를 사용하여 원격 사용자 연결을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd43-110">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="1bd43-111">자세한 내용은 [Lync Server 2013에서 외부 사용자에 대 한 연결 확인](lync-server-2013-verify-connectivity-for-external-users.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1bd43-111">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

