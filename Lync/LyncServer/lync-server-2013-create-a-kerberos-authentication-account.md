---
title: 'Lync Server 2013: Kerberos 인증 계정 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e59703328fad7c8763bc1a6cc018c2cbc585c3ed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Lync Server 2013에서 Kerberos 인증 계정 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-01-02_

이 절차를 성공적으로 완료하려면 최소한 Domain Admins 그룹 구성원으로 서버나 도메인에 로그온해야 합니다.

각 사이트에 대해 Kerberos 인증 계정을 만들 수도 있고, 단일 Kerberos 인증 계정을 만들어 모든 사이트에 사용할 수도 있습니다. Windows PowerShell cmdlet을 사용 하 여 각 사이트에 할당 된 계정을 식별 하는 등의 계정을 만들고 관리 합니다. 토폴로지 작성기 및 Lync Server 2013 제어판은 Kerberos 인증 계정을 표시 하지 않습니다. 다음 절차에 따라 Kerberos 인증에 사용할 하나 이상의 사용자 계정을 만듭니다.

<div>

## <a name="to-create-a-kerberos-account"></a>Kerberos 계정을 만들려면

1.  Domain Admins 그룹의 구성원으로 서 Lync Server 2013를 실행 하는 도메인의 컴퓨터 또는 관리 도구가 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에서 다음 명령을 실행합니다.
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    예:
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  컴퓨터 개체가 만들어졌는지 확인합니다. 이렇게 하려면 Active Directory 사용자 및 컴퓨터를 열고 **사용자** 컨테이너를 확장한 다음 사용자 계정의 컴퓨터 개체가 컨테이너에 있는지 확인합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

