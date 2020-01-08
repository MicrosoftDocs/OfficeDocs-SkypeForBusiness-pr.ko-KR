---
title: 구성 설정 복제의 유효성을 검사 합니다.
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cde1f3a96f249e98bc4e48c2e6d9c40adaad526
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="cd60d-102">구성 설정 복제의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd60d-102">Validate replication of configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd60d-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="cd60d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="cd60d-104">중앙 관리 저장소가 있는 내부 컴퓨터 또는 Lync Server 2013 Core 구성 요소가 설치 된 도메인에 연결 된 컴퓨터에서 Lync Server 2013 **CsManagementStoreReplicationStatus** cmdlet을 실행 하 여 Edge 서버에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd60d-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="cd60d-105">초기 결과에는 복제용으로 "True" 대신 상태가 "False"로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd60d-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="cd60d-106">이 경우 **CsManagementStoreReplication** cmdlet을 실행 하 고 **Get-CsManagementStoreReplicationStatus** cmdlet을 다시 실행 하기 전에 복제를 완료 하는 데 걸리는 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd60d-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

