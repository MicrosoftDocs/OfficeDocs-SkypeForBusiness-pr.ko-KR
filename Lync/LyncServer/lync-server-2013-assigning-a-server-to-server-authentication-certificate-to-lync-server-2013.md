---
title: Lync Server 2013에 서버 간 인증 인증서 할당
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fbead49c200ab1b679ef9b4ffa3d9b03bb72cd5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013에 서버 간 인증 인증서 할당

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-24_

서버 간 인증 인증서가 Microsoft Lync Server 2013에 이미 할당 되어 있는지 여부를 확인 하려면 Lync Server 2013 관리 셸에서 다음 명령을 실행 합니다.

    Get-CsCertificate -Type OAuthTokenIssuer

반환되는 인증서 정보가 없으면 토큰 발급자 인증서를 먼저 할당해야 서버 간 인증을 사용할 수 있습니다. 일반적으로 모든 Lync Server 2013 인증서는 OAuthTokenIssuer 인증서로 사용할 수 있습니다. 예를 들어 Lync Server 2013 기본 인증서는 OAuthTokenIssuer 인증서로도 사용할 수 있습니다. (OAUthTokenIssuer 인증서는 주체 필드에 SIP 도메인 이름을 포함 하는 모든 웹 서버 인증서 일 수도 있습니다.) 서버 간 인증에 사용 되는 인증서에 대 한 주요 두 가지 요구 사항은 다음과 같습니다. 1) 모든 프런트 엔드 서버에서 동일한 인증서를 OAuthTokenIssuer 인증서로 구성 해야 합니다. 2) 인증서는 최소 2048 비트 이상 이어야 합니다.

서버 간 인증에 사용할 수 있는 인증서가 없는 경우 새로운 인증서를 받아 가져온 다음 서버 간 인증의 인증서로 사용해야 합니다. 새 인증서를 요청하여 받으면 새 인증서로 프런트 엔드 서버 중 하나에 로그온할 수 있으며, 다음과 유사한 Windows PowerShell 명령을 사용하여 인증서를 가져오고 할당할 수 있습니다.

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

이전 명령에서 Path 매개 변수는 인증서 파일의 전체 경로를 나타내고 Password 매개 변수는 인증서에 할당된 암호를 나타냅니다. 이러한 절차는 단 한 번만 실행해야 합니다. Lync Server의 복제 서비스를 통해 인증서를 모든 프런트 엔드 서버에 배포하고 해독하는 예약 작업이 자동으로 만들어지기 때문입니다.

또는, 기존 인증서를 서버 간 인증 인증서로 사용할 수 있습니다. 앞에서 언급한 것과 같이 기본 인증서도 서버 간 인증 인증서로 사용할 수 있습니다. 다음 Windows PowerShell 명령 쌍을 실행하면 기본 인증서의 Thumbprint 속성 값을 검색한 후 해당 값을 사용하여 기본 인증서를 서버 간 인증 인증서로 만들 수 있습니다.

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

이전 명령에서 검색된 인증서는 전역 서버 간 인증 인증서 역할을 하도록 구성됩니다. 즉, 인증서가 모든 프런트 엔드 서버에 복제되어 사용된다는 의미입니다. 다시 강조하자면 이 명령은 프런트 엔드 서버 중 하나에서 단 한 번만 실행해야 합니다. 모든 프런트 엔드 서버에서 동일한 인증서를 사용해야 하지만 각 프런트 엔드 서버에서 OAuthTokenIssuer 인증서를 구성해서는 안 됩니다. 대신, 인증서 하나를 구성하고 Lync Server의 복제 서버를 통해 각 서버로 해당 인증서가 자동 복사되도록 해야 합니다.

Set-cscertificate cmdlet은 해당 인증서를 즉시 가져와서 현재 OAuthTokenIssuer 인증서로 작동 하도록 구성 합니다. (Lync Server 2013에서는 현재 인증서와 이전 인증서의 두 복사본을 유지 합니다.) 새 인증서가 OAuthTokenIssuer 인증서 역할을 즉시 시작 해야 하는 경우 Set-cscertificate cmdlet을 사용 해야 합니다.

또한 Set-CsCertificate cmdlet을 사용하여 새 인증서를 "롤링"할 수 있습니다. 인증서를 "롤링"한다는 것은 단순히, 지정된 시점에 새 인증서를 현재 OAuthTokenIssuer 인증서로 사용하도록 구성한다는 의미입니다. 예를 들어 다음 명령을 실행하면 기본 인증서가 검색된 후 해당 인증서가 2012년 7월 1일을 기준으로 현재 OAuthTokenIssuer 인증서로 사용되도록 구성됩니다.

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

2012년 7월 1일에 새 인증서는 현재 OAuthTokenIssuer 인증서로 구성되고 "기존" OAuthTokenIssuer 인증서는 이전 인증서로 구성됩니다.

Windows PowerShell을 사용하지 않으려는 경우 인증서 MMC 콘솔을 사용하여 인증서를 단일 프런트 엔드 서버에서 내보내어 동일한 인증서를 다른 모든 프런트 엔드 서버로 가져올 수도 있습니다. 이를 수행하는 경우 반드시 인증서 자체와 함께 개인 키를 내보내야 합니다.

<div>


> [!WARNING]
> 이러한 경우 절차는 각 프런트 엔드 서버에서 수행해야 합니다. 이 방식으로 인증서를 내보내고 가져올 때 Lync Server 2013에서는 해당 인증서를 각 프런트 엔드 서버로 복제 하지 않습니다.



</div>

모든 프런트 엔드 서버로 인증서를 가져온 후에는 Windows PowerShell 대신 Lync Server 배포 마법사를 사용 하 여 해당 인증서를 할당할 수 있습니다. 배포 마법사를 사용하여 인증서를 할당하려면 배포 마법사가 설치된 컴퓨터에서 다음 단계를 완료하십시오.

1.  시작, 모든 프로그램, **Microsoft Lync server 2013**, **Lync server 배포 마법사**를 차례로 클릭 합니다.

2.  배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭합니다.

3.  Microsoft Lync Server 2013 페이지에서 제목 **3 단계: 인증서 요청, 설치 또는 할당**에서 **실행** 단추를 클릭 합니다. 참고: 이 컴퓨터에서 인증서를 이미 설치한 경우 **실행** 단추 대신 **다시 실행**이 나타납니다.

4.  인증서 마법사에서 **OAuthTokenIssuer** 인증서를 선택한 후 **지정**을 클릭합니다.

5.  인증서 할당 마법사의 **인증서 할당** 페이지에서 **다음**을 클릭합니다.

6.  **인증서 저장소** 페이지에서 서버 간 인증에 사용할 인증서를 선택한 후 **다음**을 클릭합니다.

7.  인증서 할당 요약 페이지에서 **다음**을 클릭합니다.

8.  명령 실행 페이지에서 **마침**을 클릭합니다.

9.  인증서 마법사와 배포 마법사를 닫습니다.

</div>

<span> </span>

</div>

</div>

</div>

