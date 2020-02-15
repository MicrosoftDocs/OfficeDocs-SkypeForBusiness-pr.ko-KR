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
ms.openlocfilehash: 41cb48da1711cfa6eb29a90f19a9b6e42b110c52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory 스키마 복제 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

포리스트 준비를 실행 하기 전에 스키마 파티션이 복제 되었는지 수동으로 확인 합니다.

<div>

## <a name="to-manually-verify-schema-replication"></a>스키마 복제를 수동으로 확인하려면

1.  Enterprise Admins 그룹의 구성원으로 도메인 컨트롤러에 로그온합니다.

2.  **시작**, **관리 도구**를 차례로 클릭한 다음 **ADSI 편집**을 클릭하여 ADSI 편집을 엽니다.
    
    <div>
    

    > [!TIP]  
    > 또는 명령줄에서 <STRONG>adsiedit.msc</STRONG>를 실행할 수도 있습니다.

    
    </div>

3.  아직 선택되지 않은 경우 MMC(Microsoft Management Console) 트리에서 **ADSI 편집**을 클릭합니다.

4.  **동작** 메뉴에서 **연결**을 클릭합니다.

5.  **잘 알려진 명명 컨텍스트를 선택합니다** 아래에 있는 **연결 설정** 대화 상자에서 **스키마**를 선택한 다음 **확인**을 클릭합니다.

6.  스키마 컨테이너 아래에서 CN=ms-RTC-SIP-SchemaVersion을 검색합니다. 이 개체가 있고 **rangeUpper** 특성 값이 1150이고 **rangeLower** 특성 값이 3이면 스키마가 업데이트 및 복제된 것입니다. 이 개체가 존재하지 않거나 **rangeUpper** 및 **rangeLower** 특성 값이 지정된 대로가 아니면 스키마가 수정되지 않았거나 복제되지 않은 것입니다.

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

