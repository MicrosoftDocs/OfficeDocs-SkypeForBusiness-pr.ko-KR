---
title: 'Lync Server 2013: 통화 대기 재해 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca9eb8b87d4485fe1cb02aa8663b362d921a4fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013의 통화 대기 재해 복구 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-30_

이 섹션에서는 재해 복구를 위해 통화 대기 응용 프로그램을 준비 하는 몇 가지 방법과 재해 복구 프로세스에 대 한 일부 고려 사항에 대해 설명 합니다.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>통화 대기 재해 복구 준비

재해 복구 절차를 준비하고 수행할 때 다음 사항에 유의하십시오.

  - 용량 계획을 수행할 때 재해 복구를 계획합니다. 재해 복구 용량의 경우 페어링 된 풀의 각 풀은 두 풀에서 통화 대기 서비스의 작업 부하를 처리할 수 있어야 합니다. 통화 대기 용량 계획에 대 한 자세한 내용은 [Lync Server 2013에서 통화 대기에 대 한 용량 계획](lync-server-2013-capacity-planning-for-call-park.md)을 참조 하십시오.

  - 재해 복구 중에 장애 조치(failover) 프로세스의 일부로서 백업 풀로 리디렉션된 사용자는 백업 풀에서 실행 중인 통화 대기 서비스를 사용합니다. 따라서 재해 복구 중 통화 대기를 지원 하려면 기본 풀과 백업 풀에서 모두 통화 대기 응용 프로그램을 배포 하 고 사용 하도록 설정 해야 합니다.

  - 각 풀에는 해당 풀에 있는 사용자에 대해 통화 대기에 사용할 유효한 파킹된 통화 번호 범위가 있어야 합니다.

  - 통화 대기를 위해 업로드 된 보류 중인 사용자 지정 음악의 별도 백업 복사본을 항상 보관 합니다. 이러한 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며, 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>통화 대기 재해 복구 고려 사항

통화 대기 응용 프로그램 구성 설정의 집합과 사용자 지정 된 단일 음악 오디오 파일을 풀 당 하나만 정의할 수 있습니다. 이러한 설정에는 시간 제한 임계값, 대기 음악, 최대 호출 받기 시도 횟수 및 시간 제한 URI가 포함됩니다. 이러한 구성 설정을 보려면 **Get-CsCpsConfiguration** cmdlet을 실행합니다. **New-cscpsconfiguration** cmdlet에 대 한 자세한 내용은 [get-new-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)를 참조 하십시오.

재해 복구 중에 통화 대기는 백업 풀의 통화 대기 응용 프로그램을 사용 하므로 기본 풀의 설정이 백업 되지 않습니다. 기본 풀을 복구할 수 없고 기본 풀을 대체 하기 위해 새 풀을 배포 하는 경우 기본 풀의 설정이 손실 되며, 새 풀에서 통화 대기 설정 및 사용자 지정 된 모든 음악 오디오 파일을 다시 구성 해야 합니다.

기본 풀을 대체 하기 위해 다른 FQDN (정규화 된 도메인 이름)을 사용 하 여 새 풀을 배포 하는 경우 기본 풀과 연결 된 모든 통화 대기 궤도 범위를 새 풀의 FQDN으로 다시 할당 해야 합니다. 궤도 범위를 새 풀에 다시 할당 하려면 Lync Server 제어판 또는 **get-cscallparkorbit** cmdlet 중 하나를 사용할 수 있습니다. **Get-cscallparkorbit** cmdlet에 대 한 자세한 내용은 [get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

