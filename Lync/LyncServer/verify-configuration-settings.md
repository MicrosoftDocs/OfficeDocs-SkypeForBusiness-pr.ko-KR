---
title: 구성 설정 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b84d2c11fee62b0912cc43317ed6716dd33f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="9fe47-102">구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="9fe47-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fe47-103">_**마지막으로 수정 된 항목:** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="9fe47-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="9fe47-104">중앙 관리 저장소가 있는 내부 컴퓨터 또는 Lync Server 2013 핵심 구성 요소 (OcsCore)가 설치 된 도메인에 가입 된 컴퓨터에서 Lync Server 2013 **-** cmdlet을 실행 하 여에 지 서버에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe47-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="9fe47-105">초기 결과에서는 복제 상태가 "True"가 아닌 "False"로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe47-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="9fe47-106">이 경우 **Invoke-CsManagementStoreReplication** cmdlet을 실행하고 복제가 완료될 때까지 기다린 후에 **Get-CsManagementStoreReplicationStatus**를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe47-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

