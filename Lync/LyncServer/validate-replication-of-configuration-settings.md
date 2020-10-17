---
title: 구성 설정 복제 유효성 검사
description: 구성 설정의 복제 유효성을 검사 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26d8e9326da8b865f4e2ca3181975fb899300636
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552604"
---
# <a name="validate-replication-of-configuration-settings"></a>구성 설정 복제 유효성 검사

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

중앙 관리 저장소가 있는 내부 컴퓨터 또는 Lync Server 2013 핵심 구성 요소가 설치 된 도메인에 가입 된 컴퓨터에서 Lync Server 2013 **get-csmanagementstorereplicationstatus** cmdlet을 실행 하 여에 지 서버에 대 한 구성 정보 복제의 유효성을 검사할 수 있습니다.

초기 결과에서는 복제 상태가 "True"가 아닌 "False"로 표시될 수 있습니다. 이 경우 **invoke-csmanagementstorereplication** cmdlet을 실행 하 고 **get-csmanagementstorereplicationstatus** cmdlet을 다시 실행 하기 전에 복제가 완료 될 때까지 기다립니다.

</div>

<span> </span>

</div>

</div>

</div>

