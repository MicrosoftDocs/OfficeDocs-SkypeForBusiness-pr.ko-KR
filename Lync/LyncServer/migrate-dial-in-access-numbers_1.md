---
title: 전화 접속 액세스 번호 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>전화 접속 액세스 번호 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-26_

전화 접속 액세스 번호를 마이그레이션하려면 두 단계가 필요 합니다. 다이얼 플랜 및 기타 전화 접속 액세스 번호 설정을 마이그레이션하고 **CsLegacyConfiguration** Cmdlet ( [가져오기-정책 및 설정](import-policies-and-settings.md)에서 완료 됨)을 실행 하 여 연락처 개체를 마이그레이션하기 위해 **csapplicationendpoint** cmdlet을 실행 합니다.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>전화 접속 액세스 번호를 마이그레이션하려면

1.  Office Communications Server 2007 R2 관리 도구를 엽니다.

2.  콘솔 트리에서 포리스트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 클릭 한 다음 **회의 수행자 속성**을 클릭 합니다.

3.  **Access 전화 번호** 탭에서 **풀로 서비스** 를 클릭 하 여 연결 된 풀을 기준으로 access 전화 번호를 정렬 하 고 마이그레이션하는 풀에 대 한 모든 액세스 번호를 식별 합니다.

4.  각 액세스 번호에 대 한 SIP URI를 식별 하려면 액세스 번호를 두 번 클릭 하 여 **회의 수행자 번호 편집** 대화 상자를 열고 **SIP URI**아래를 확인 합니다.

5.  Lync Server 관리 셸을 엽니다.

6.  각 전화 접속 액세스 번호를 Lync Server 2013에서 호스팅하는 풀로 이동 하려면 다음을 실행 합니다.
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  Office Communications Server 2007 R2 관리 도구의 **Access 전화 번호** 탭에서 마이그레이션할 Office Communications Server 2007 R2 풀에 대 한 전화 접속 액세스 번호가 남아 있지 않은지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

