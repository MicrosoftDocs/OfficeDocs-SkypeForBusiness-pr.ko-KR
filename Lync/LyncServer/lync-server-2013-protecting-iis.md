---
title: 'Lync Server 2013: IIS 보호'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03d0f3e736284970bf22fe813093e0e54accd29e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Lync Server 2013에서 IIS 보호

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-12-05_

Microsoft Office Communications Server 2007 및 Microsoft Office Communications Server 2007 R2에서 IIS (인터넷 정보 서비스)는 표준 사용자 계정으로 실행 됩니다. 이로 인해 문제가 발생할 수 있습니다. 암호를 만료 한 경우에는 진단 하기 어려운 문제 인 웹 서비스를 잃게 됩니다. 암호 만료 문제를 방지 하기 위해 Microsoft Lync Server 2013에서는 IIS를 실행 하는 사이트의 모든 컴퓨터에 대 한 인증 보안 주체의 역할을 하는 컴퓨터 계정 (실제로 존재 하지 않는 컴퓨터)을 만들 수 있습니다. 이러한 계정은 Kerberos 인증 프로토콜을 사용 하므로 계정이 Kerberos 계정 이라고 하 고 새 인증 프로세스를 Kerberos 웹 인증 이라고 합니다. 이렇게 하면 단일 계정을 사용 하 여 모든 IIS 서버를 관리할 수 있습니다.

이 인증 원칙에 따라 서버를 실행 하려면 먼저 새-Cxeercosaccount cmdlet을 사용 하 여 컴퓨터 계정을 만들어야 합니다. 이 계정은 하나 이상의 사이트에 할당 됩니다. 할당이 완료 되 면 CsTopology cmdlet을 실행 하 여 계정 및 Lync Server 2013 사이트 간의 연결을 사용 하도록 설정 합니다. 그 중에는 AD DS (Active Directory 도메인 서비스)에 필수 SPN (서비스 사용자 이름)이 만들어집니다. Spn은 클라이언트 응용 프로그램에서 특정 서비스를 찾을 수 있는 방법을 제공 합니다. 자세한 내용은 운영 설명서의 [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) 를 참조 하세요.

<div>

## <a name="best-practices"></a>모범 사례

IIS의 보안을 강화 하려면 IIS에 대 한 Kerberos 계정을 구현 하는 것이 좋습니다. Kerberos 계정을 구현 하지 않으면 IIS는 표준 사용자 계정으로 실행 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

