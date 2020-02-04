---
title: Microsoft Lync Phone Edition 장치에서 서비스 품질 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8068b69afa3e02a5634041c61be6f7711e8f30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Lync Server 2013에서 Microsoft Lync Phone Edition 장치에 대 한 서비스 품질 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

QoS (서비스 품질)는 Iphone와 같은 디바이스에 대해 기본적으로 사용 되지 않지만, Lync Phone Edition을 실행 하는 디바이스에 대해 기본적으로 QoS를 사용할 수 있습니다. (이러한 장치는 일반적으로 UC 또는 통합 통신 전화 라고 합니다.) 이를 확인 하려면 Lync Server Management Shell 내에서 다음 Windows PowerShell 명령을 실행 합니다.

    Get-CsUCPhoneConfiguration

UC 전화 구성 설정을 변경 하지 않은 경우에는 다음과 같은 정보를 얻을 수 있습니다.

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

서비스 품질을 위해 다음 속성 중 하나에만 관심이 있습니다. VoiceDiffServTag. VoiceDiffServTag는 Lync Phone Edition 장치에서 음성 트래픽 emanating에 할당 된 DSCP 값을 나타냅니다.

<div>


> [!NOTE]
> Voice8021p 매개 변수는 Lync Server 2013에서 더 이상 지원 되지 않습니다. 이 매개 변수는 여전히 Microsoft Lync Server 2010의 이전 버전과의 호환성을 위해 유효 합니다. 그러나 Lync Server 2013에 사용 되는 장치에는 영향을 주지 않습니다.



</div>

대부분의 네트워크에서 40의 VoiceDiffServTag으로 Lync Phone Edition 패킷을 표시 하면 문제가 발생 하지 않습니다. 그러나 40는 일반적으로 오디오 트래픽에 사용 되는 값이 아닙니다. 대신 오디오 트래픽은 거의 항상 DSCP 코드 46으로 표시 됩니다. 네트워크 전체에서 일관성을 유지 하기 위해 UC 휴대폰의 VoiceDiffServTag 속성을 46으로 변경 하는 것이 좋습니다.

이렇게 하려면 Windows PowerShell 또는 Lync Server 제어판을 사용할 수 있습니다. Windows PowerShell을 사용 하 여 VoiceDiffServTag 값을 수정 하려면 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

앞의 명령은 UC 전화 구성 설정의 전역 컬렉션을 수정 합니다. 그러나 통합 커뮤니케이션 설정은 사이트 범위에 할당할 수도 있습니다. 사이트 범위에서 UC 전화 구성 설정을 수정 하려면 사이트 Id를 지정 해야 합니다. 예를 들면 다음과 같습니다.

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

다음 명령을 사용 하 여 모든 UC 전화 구성 설정을 동시에 수정할 수도 있습니다.

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Lync Server 제어판을 사용 하 여이 변경 작업을 수행 하려면 제어판을 시작 하 고 다음 절차를 완료 합니다.

1.  **클라이언트** 를 클릭 한 다음 **장치 구성을**클릭 합니다.

2.  **장치 구성** 탭에서 수정 하려는 설정 모음을 두 번 클릭 합니다 (예: **전역**).

3.  **장치 구성 편집** 대화 상자에서 **Voice QoS (서비스 품질)** 상자의 값을 **46** 로 설정한 다음 **커밋을**클릭 합니다.

여러 컬렉션이 있는 경우 UC 전화 설정의 각 컬렉션에 대해이 프로세스를 반복 해야 합니다. Lync Server 제어판을 사용 하 여 여러 설정 모음을 동시에 수정할 수는 없습니다.

조직의 Windows 운영 체제 (예: Iphone)를 기반으로 하지 않는 장치를 사용 하는 경우에는 VoiceDiffServTag 설정을 변경 해도 이러한 장치가 영향을 받지 않습니다. 이러한 장치에서 DSCP 값을 변경 하려는 경우 각 디바이스 유형에 대 한 관리 매뉴얼을 참조 해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

