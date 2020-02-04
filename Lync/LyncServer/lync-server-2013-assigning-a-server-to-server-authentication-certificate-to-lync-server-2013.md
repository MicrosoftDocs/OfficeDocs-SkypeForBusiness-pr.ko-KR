---
title: 서버 간 인증 인증서를 Lync Server 2013에 할당
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
ms.openlocfilehash: 06372be3808f3855bc0172cc408308a0c9c9cab2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>서버 간 인증 인증서를 Microsoft Lync Server 2013에 할당

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-24_

서버 간 인증 인증서가 Microsoft Lync Server 2013에 이미 할당 되어 있는지 여부를 확인 하려면 Lync Server 2013 관리 셸에서 다음 명령을 실행 합니다.

    Get-CsCertificate -Type OAuthTokenIssuer

인증서 정보가 반환 되지 않으면 서버 간 인증을 사용할 수 있으려면 먼저 토큰 발급자 인증서를 할당 해야 합니다. 일반적으로 Lync Server 2013 인증서는 OAuthTokenIssuer 인증서로 사용할 수 있습니다. 예를 들어 Lync Server 2013 기본 인증서는 OAuthTokenIssuer 인증서로 사용할 수도 있습니다. OAUthTokenIssuer 인증서는 제목 필드에 SIP 도메인의 이름을 포함 하는 웹 서버 인증서 일 수도 있습니다. 서버 간 인증에 사용 되는 인증서에 대 한 기본 두 가지 요구 사항은 다음과 같습니다. 1) 모든 프런트 엔드 서버에서 동일한 인증서를 OAuthTokenIssuer 인증서로 구성 해야 합니다. and, 2) 인증서는 최소 2048 비트 여야 합니다.

서버 간 인증에 사용할 수 있는 인증서가 없는 경우 새 인증서를 얻고 새 인증서를 가져온 다음이 인증서를 서버 간 인증에 사용할 수 있습니다. 새 인증서를 요청 하 고 얻은 후에는 프런트 엔드 서버 중 하나에 로그온 하 여이 인증서와 유사한 Windows PowerShell 명령을 사용 하 여 해당 인증서를 가져오고 할당할 수 있습니다.

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

위의 명령에서 Path 매개 변수는 인증서 파일의 전체 경로를 나타내고 Password 매개 변수는 인증서에 할당 된 암호를 나타냅니다. 이 절차는 한 번만 실행 해야 합니다. Lync Server의 복제 서비스는 모든 프런트 엔드 서버에 대 한 인증서를 해독 하 고 배포 하는 예약 된 작업 집합을 자동으로 만듭니다.

또는 기존 인증서를 서버 대 서버 인증 인증서로 사용할 수 있습니다. 참고로, 기본 인증서는 서버 간 인증 인증서로 사용할 수 있습니다. 다음 쌍의 Windows PowerShell 명령은 기본 인증서의 손도장 속성 값을 검색 한 다음 해당 값을 사용 하 여 기본 인증서를 서버 간 인증 인증서로 만듭니다.

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

앞의 명령에서 검색 된 인증서는 전역 서버 대 서버 인증 인증서로 작동 하도록 구성 됩니다. 즉, 인증서가 모든 프런트 엔드 서버에 복제 되 고 사용 됩니다. 이 명령은 프런트 엔드 서버 중 하나 에서만 한 번만 실행 해야 합니다. 모든 프런트 엔드 서버는 동일한 인증서를 사용 해야 하지만 각 프런트 엔드 서버에서 OAuthTokenIssuer 인증서를 구성 하지 않아야 합니다. 대신, 인증서를 한 번 구성 하면 Lync Server의 복제 서버가 각 서버에 해당 인증서를 복사 하도록 할 수 있습니다.

CsCertificate cmdlet은 해당 인증서를 가져와 즉시 해당 인증서를 현재 OAuthTokenIssuer 인증서로 작동 하도록 구성 합니다. (Lync Server 2013는 인증서 유형의 복사본 두 개 (현재 인증서와 이전 인증서)를 계속 유지 합니다. 새 인증서가 OAuthTokenIssuer 인증서로 바로 작동 하기 시작 해야 하는 경우 CsCertificate cmdlet을 사용 해야 합니다.

Set-CsCertificate cmdlet을 사용 하 여 새 인증서를 "롤 포워드" 할 수도 있습니다. "롤링"은 사용자가 지정 된 시점에 현재 OAuthTokenIssuer 인증서가 되도록 새 인증서를 구성 한다는 의미입니다. 예를 들어이 명령은 기본 인증서를 검색 한 다음 해당 인증서를 현재 OAuthTokenIssuer 인증서로 구성 하 여 7 월 1 일 (2012)로 사용 합니다.

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

2012 년 7 월 1 일에 새 인증서가 현재 OAuthTokenIssuer 인증서로 구성 되 고 "old" OAuthTokenIssuer 발급자 인증서가 이전 인증서로 구성 됩니다.

Windows PowerShell을 사용 하지 않으려는 경우 인증서 MMC 콘솔을 사용 하 여 한 프런트 엔드 서버에서 인증서를 내보낸 다음 다른 모든 프런트 엔드 서버에서 동일한 인증서를 가져올 수도 있습니다. 이 작업을 수행 하는 경우 인증서 자체와 함께 개인 키 내보내기를 확인 합니다.

<div>


> [!WARNING]
> 이 경우 각 프런트 엔드 서버에서 절차를 수행 해야 합니다. 이 방법으로 인증서를 내보내고 가져오면 Lync Server 2013이 해당 인증서를 각 프런트 엔드 서버로 복제 하지 않습니다.



</div>

모든 프런트 엔드 서버로 인증서를 가져온 후에는 Windows PowerShell 대신 Lync Server 배포 마법사를 사용 하 여 해당 인증서를 할당할 수 있습니다. 배포 마법사를 사용 하 여 인증서를 할당 하려면 배포 마법사가 설치 된 컴퓨터에서 다음 단계를 완료 합니다.

1.  시작을 클릭 하 고 모든 프로그램, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 배포 마법사**를 클릭 합니다.

2.  배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 합니다.

3.  Microsoft Lync Server 2013 페이지에서 제목 **3 단계: 요청, 인증서 설치 또는 할당**에서 **실행** 단추를 클릭 합니다. (참고:이 컴퓨터에 이미 인증서를 설치한 경우 **실행** 단추에는 레이블이 **다시 실행**됩니다.)

4.  인증서 마법사에서 **Oauthtokenissuer** 인증서를 선택 하 고 **할당**을 클릭 합니다.

5.  인증서 할당 마법사의 **인증서 할당** 페이지에서 **다음**을 클릭 합니다.

6.  **인증서 저장소** 페이지에서 서버와 서버 간 인증에 사용할 인증서를 선택 하 고 **다음**을 클릭 합니다.

7.  인증서 할당 요약 페이지에서 **다음**을 클릭 합니다.

8.  명령 실행 페이지에서 **마침을**클릭 합니다.

9.  인증서 마법사 및 배포 마법사를 닫습니다.

</div>

<span> </span>

</div>

</div>

</div>

