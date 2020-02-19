---
title: 정책 및 설정 가져오기
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0249939bd2ba116fe29f28e50292289976080204
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>정책 및 설정 가져오기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

Office Communications Server 2007 R2 토폴로지 정보를 Lync Server 2013 파일럿 풀과 병합 한 후에는 Lync Server 2013 Management Shell cmdlet을 실행 하 여 Office Communications Server 2007 R2 정책 및 구성 설정을 마이그레이션해야 합니다. Lync Server 2013 파일럿 풀로 이동할 수 있습니다.

**Import-cslegacyconfiguration** cmdlet은 정책, 음성 경로, 다이얼 플랜, Communicator Web Access url 및 전화 접속 액세스 번호를 Lync Server 2013로 가져옵니다.

<div>

## <a name="to-migrate-policies-and-settings"></a>정책 및 설정을 마이그레이션하려면

1.  Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 시작 합니다.

2.  명령줄에 다음을 입력합니다.
    
        Import-CsLegacyConfiguration
    
    정책을 가져온 후에는 다음 절차에 따라 Lync Server 제어판에서 가져온 정책을 확인 합니다.

</div>

<div>

## <a name="to-view-imported-policies"></a>가져온 정책을 보려면

1.  Lync Server 2013 제어판을 엽니다.

2.  **음성 라우팅**을 클릭하고 가져온 정책을 봅니다.

3.  **회의**를 클릭하고 가져온 정책을 봅니다.

4.  **페더레이션 및 외부 액세스**를 클릭하고 가져온 정책을 봅니다.

5.  **모니터링 및 보관**을 클릭하고 가져온 정책을 봅니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

