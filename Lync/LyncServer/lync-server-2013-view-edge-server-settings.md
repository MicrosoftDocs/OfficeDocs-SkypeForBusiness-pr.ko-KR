---
title: 'Lync Server 2013: Edge 서버 설정 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972a5861af803dbaf66843883595c446345ac29a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Lync Server 2013의 Edge 서버 설정 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-20_

모든 변경 내용이 정의 된 변경 제어 절차에 따라 문서화 되었는지 확인할 수 있도록 구성 관리 데이터베이스의 데이터에 대해 일반 Edge 서버 구성을 검토 해야 합니다.

추가 검사에는 다음 섹션에서 설명 하는 항목이 포함 될 수 있습니다.

<div>

## <a name="verify-the-allow-and-block-lists"></a>허용 및 차단 목록 확인

페더레이션 도메인의 SIP URI "허용" 및 "차단" 목록을 확인 하 여 나열 된 네임 스페이스가 여전히 유효한 지 여부를 확인 합니다.

Windows PowerShell을 사용 하 여 허용 및 차단 된 목록을 볼 수 있습니다. 허용 된 도메인 목록의 도메인을 검토 하려면 다음 Windows PowerShell 명령을 실행 합니다.

`Get-CsAllowedDomain`

이 명령은 허용 된 도메인 목록의 도메인에 대해 다음과 같은 정보를 반환 합니다.

Id: contoso.com

도메인: contoso.com

ProxyFqdn:

댓글을

MarkForMonitoring: False

댓글을

차단 된 도메인 목록에 있는 도메인을 검토 하려면 다음 명령을 사용 합니다.

`Get-CsBlockedDomain`

그러면 각 차단 된 도메인에 대해 다음과 같은 정보를 받게 됩니다.

Id: tailspintoys.com

도메인: tailspintoys.com

Windows PowerShell을 사용 하 여 허용 된 도메인 목록에 있는 도메인에 연결할 수 있는지 확인할 수도 있습니다. 예를 들어이 명령은 Edge 서버 (TargetFqdn)와 페더레이션된 도메인 contoso.com 간의 연결을 확인 합니다.

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

이 명령은 Edge 서버와 허용 된 도메인 목록에 있는 모든 도메인 간의 연결을 확인 합니다.

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>여러 Edge 서버가 동일한 지 확인

부하 분산 배열에 Edge 서버를 여러 개 배포 하는 경우에는 배열의 모든 Edge 서버가 같은 방식으로 구성 되어 있는지 확인 하는 것이 좋습니다.

컴퓨터 관리 스냅인에 대 한 Lync Server 2013 확장의 세부 정보 창에서 Edge 서버에 대 한 설정을 볼 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[테스트-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

