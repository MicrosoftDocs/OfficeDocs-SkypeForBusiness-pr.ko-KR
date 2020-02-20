---
title: IIS에 Kerberos 인증 계정 암호 동기화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 255c1035809b69d5de1bb5e08fc770dc9a6b1c4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Lync Server 2013에서 IIS에 Kerberos 인증 계정 암호 동기화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2010-11-08_

이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.

사이트에서 프런트 엔드 서버, Standard Edition 서버 및 디렉터는 웹 서비스 서비스에 대 한 요청을 인증 하기 위해 Kerberos 인증 계정을 사용할 수 있습니다. 이 절차에서는 Kerberos 계정이 할당 된 사이트에서 웹 서비스를 실행 하는 각 서버를 찾고 Kerberos 계정을 사용 하도록 IIS (인터넷 정보 서비스) 구성 설정을 업데이트 합니다. 자세한 내용은 [Lync server 2013에서 서버에 Kerberos 인증 계정 암호 설정을](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)참조 하십시오.

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Kerberos 인증 계정 암호를 설정 및 구성하려면

1.  fe01.contoso.com 등의 원본 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  Lync Server 관리 셸 명령줄에서 다음의 두 명령을 실행 합니다.
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    예:
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > 원본 컴퓨터 및 대상 컴퓨터의 이름은 서버의 FQDN(정규화된 도메인 이름)이어야 합니다. 풀 이름이 원본 컴퓨터 또는 대상 컴퓨터로 사용하는 컴퓨터의 이름과 같지 않으면 풀 FQDN은 사용할 수 없습니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > 계정 추가 또는 계정 제거와 같은 Kerberos 인증을 변경한 후에는 Lync Server 관리 셸 명령 프롬프트에서 <STRONG>Enable-enable-cstopology</STRONG> 을 실행 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

