---
title: 전화 접속 액세스 번호 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6654c084be4915d48c4148c90b3888295c887f08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>전화 접속 액세스 번호 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-26_

전화 접속 액세스 번호를 마이그레이션하려면 두 단계가 필요 합니다 (가져오기 [정책 및 설정](import-policies-and-settings.md)앞에서 완료) **import-cslegacyconfiguration** cmdlet을 실행 하 여 다이얼 플랜 및 기타 전화 접속 액세스 번호 설정을 마이그레이션하고, **csapplicationendpoint** cmdlet을 실행 하 여 연락처 개체를 마이그레이션합니다.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>전화 접속 액세스 번호를 마이그레이션하려면

1.  Office Communications Server 2007 R2 관리 도구를 엽니다.

2.  콘솔 트리에서 포리스트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭한 후 **회의 전화 교환 속성**을 클릭합니다.

3.  **액세스 전화 번호** 탭에서 **풀별로 서비스됨**을 클릭하여 연결된 풀별로 액세스 전화 번호를 정렬하고 마이그레이션하려는 풀에 대한 모든 액세스 번호를 식별합니다.

4.  각 액세스 번호에 대한 SIP URI를 식별하려면 액세스 번호를 두 번 클릭하여 **회의 전화 교환 번호 편집** 대화 상자를 열고 **SIP URI** 아래를 확인합니다.

5.  Lync Server 관리 셸을 엽니다.

6.  각 전화 접속 액세스 번호를 Lync Server 2013에 호스트 된 풀로 이동 하려면 다음을 실행 합니다.
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Office Communications Server 2007 R2 관리 도구의 **액세스 전화 번호** 탭에서 마이그레이션할 Office Communications Server 2007 R2 풀에 대 한 전화 접속 액세스 번호가 남아 있지 않은지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

