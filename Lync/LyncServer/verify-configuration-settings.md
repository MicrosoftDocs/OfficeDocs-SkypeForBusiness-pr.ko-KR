---
title: 구성 설정 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c98ec6387353e60890653a0369107c126f8eeb4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>구성 설정 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-06_

중앙 관리 저장소가 있는 내부 컴퓨터 또는 Lync Server 2013 핵심 구성 요소 (OcsCore.msi)가 설치 된 도메인에 가입 된 컴퓨터에서 Lync Server 2013 **get-csmanagementstorereplicationstatus** cmdlet을 실행 하 여에 지 서버에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다.

초기 결과에서는 복제 상태가 "True"가 아닌 "False"로 표시될 수 있습니다. 이 경우 **Invoke-CsManagementStoreReplication** cmdlet을 실행하고 복제가 완료될 때까지 기다린 후에 **Get-CsManagementStoreReplicationStatus**를 다시 실행합니다.

</div>

<span> </span>

</div>

</div>

</div>

