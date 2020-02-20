---
title: 'Lync Server 2013: 서버에서 Kerberos 인증 계정 암호 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeef318392540aaa0600a4b61f20a296df25ca5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Lync Server 2013에서 서버에 대해 Kerberos 인증 계정 암호 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-01-16_

이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.

프런트 엔드 서버, Standard Edition 서버 및 디렉터를 포함 하는 각 사이트의 Kerberos 계정에 대해 암호를 설정 해야 합니다. 사이트의 한 서버 (예: 프런트 엔드 서버 1 개)에서 **c44er4osaccountpassword** Windows PowerShell cmdlet을 실행 하 여 암호를 설정할 수 있습니다. 각 사이트에 대해 **c44er4osaccountpassword** cmdlet을 실행 해야 합니다. 이 cmdlet은 웹 서비스 서비스에 대 한 IIS (인터넷 정보 서비스)를 구성한 다음 Active Directory 도메인 서비스의 컴퓨터 계정에 대 한 암호를 설정 합니다. Cmdlet에서 사용 되는 매개 변수를 기반으로 하는 대체 방법은 Kerberos 계정 암호의 원본으로 구성 된 다른 서버를 사용 하는 동안 한 서버에서 IIS를 구성 합니다.

**C4eercosaccountpassword** cmdlet을 사용 하 여 암호를 설정 하는 경우 Kerberos는 임의로 생성 된 문자열로 암호를 설정 합니다. 이 cmdlet은이 계정이 할당 된 모든 Lync Server 2013 중앙 사이트의 모든 IIS 인스턴스에 연결 합니다.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Kerberos 인증 계정에 대 한 암호를 설정 하려면

1.  Lync Server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 도메인 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에서 다음의 두 명령을 실행합니다.
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    예:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > 도메인\사용자 형식을 사용하여 UserAccount 매개 변수를 지정해야 합니다. User@Domain 확장명 형식은 Kerberos 인증을 위해 만든 컴퓨터 개체를 참조 하는 데 지원 되지 않습니다.

    
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

