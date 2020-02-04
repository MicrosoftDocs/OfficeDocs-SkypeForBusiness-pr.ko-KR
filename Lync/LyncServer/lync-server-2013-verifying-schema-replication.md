---
title: 'Lync Server 2013: 스키마 복제 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ea90012c116bb66caf16313d930c6f05db4413
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory 스키마 복제 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

포리스트 준비를 실행 하기 전에 스키마 파티션이 복제 되었는지 수동으로 확인 합니다.

<div>

## <a name="to-manually-verify-schema-replication"></a>수동으로 스키마 복제를 확인 하려면

1.  엔터프라이즈 관리자 그룹의 구성원으로 도메인 컨트롤러에 로그온 합니다.

2.  **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **adsi 편집**을 클릭 하 여 adsi 편집을 엽니다.
    
    <div>
    

    > [!TIP]  
    > 또는 명령줄에서 <STRONG>adsiedit</STRONG> 를 실행할 수 있습니다.

    
    </div>

3.  MMC (Microsoft Management Console) 트리에서 아직 선택 하지 않은 경우 **ADSI 편집**을 클릭 합니다.

4.  **작업** 메뉴에서 **연결 대상**을 클릭 합니다.

5.  **연결 설정** 대화 상자의 **잘 알려진 명명 컨텍스트 선택**에서 **스키마**를 선택한 다음 **확인**을 클릭 합니다.

6.  스키마 컨테이너 아래에서 CN = ms-RTC-SIP-SchemaVersion을 검색 합니다. 이 개체가 존재 하 고, **Range upper** 특성의 값이 1150이 고, **range lower** 특성의 값이 3 이면 스키마가 성공적으로 업데이트 되 고 복제 된 것입니다. 이 개체가 없거나 **Range upper** 및 **range lower** 특성 값이 지정 되지 않은 경우 스키마는 수정 되거나 복제 되지 않은 것입니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Active Directory 스키마 준비 실행](lync-server-2013-running-schema-preparation.md)  


[Lync Server 2013에서 Active Directory 스키마 준비](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

