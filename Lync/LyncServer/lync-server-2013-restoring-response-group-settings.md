---
title: 'Lync Server 2013: 응답 그룹 설정 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d2b257fe2a77faacca588f2df5632d6476c673b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511411"
---
# <a name="restoring-response-group-settings-in-lync-server-2013"></a>Lync Server 2013에서 응답 그룹 설정 복원

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-18_

응답 그룹 응용 프로그램을 배포한 경우 백 엔드 서버 또는 Standard Edition 서버를 복원 해야 하는 경우에도 응답 그룹 구성 설정을 복원 해야 합니다.

<div>

## <a name="to-restore-response-group-configuration-settings"></a>응답 그룹 구성 설정을 복원하려면

1.  명령줄에 다음을 입력합니다.
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    예를 들면 다음과 같습니다.
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

