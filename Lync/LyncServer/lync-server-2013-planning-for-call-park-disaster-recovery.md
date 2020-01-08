---
title: 'Lync Server 2013: 통화 대기 재해 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7da940f55574e1c6d50aeb06c0c80710bdbaad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013의 통화 대기 재해 복구 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-30_

이 섹션에서는 재난 복구를 위해 통화 공원 응용 프로그램을 준비 하는 방법과 재해 복구 프로세스의 몇 가지 고려 사항에 대해 설명 합니다.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>통화 파킹 재해 복구 준비

재해 복구 절차를 준비 하 고 수행할 때 다음 사항에 유의 하세요.

  - 용량 계획을 수립할 때 재해 복구 계획을 수립 합니다. 재해 복구 용량을 위해 쌍으로 된 풀의 각 풀은 두 풀에서 모두 통화 대기 서비스의 작업량을 처리할 수 있습니다. 통화 공원 용량 계획에 대 한 자세한 내용은 [Lync Server 2013에서 통화 파킹에 대 한 용량 계획](lync-server-2013-capacity-planning-for-call-park.md)을 참조 하세요.

  - 재해 복구 중 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션되는 사용자는 백업 풀에서 실행 되는 통화 대기 서비스를 사용 합니다. 따라서 재해 복구 중에 통화 대기를 지원 하려면 기본 풀과 백업 풀 모두에서 통화 공원 응용 프로그램을 배포 하 고 사용 하도록 설정 해야 합니다.

  - 각 풀에는 파킹 통화에 사용 하기 위해 해당 풀에 속한 사용자를 위한 유효한 궤도 번호 범위가 있어야 합니다.

  - 통화 공원에 업로드 된 보류 중인 사용자 지정 음악의 별도의 백업 복사본을 항상 보관 하세요. 이러한 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>통화 파킹 재해 복구 고려 사항

하나의 통화 공원 응용 프로그램 구성 설정과 사용자 지정 음악/보류 오디오 파일을 풀 당 하나만 정의할 수 있습니다. 이러한 설정에는 시간 제한 임계값, 보류 중인 음악, 최대 통화 픽업 시도 횟수, 시간 초과 URI 등이 포함 됩니다. 이러한 구성 설정을 보려면 **Get-CsCpsConfiguration** cmdlet을 실행 합니다. **CsCpsConfiguration** cmdlet에 대 한 자세한 내용은 [get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)를 참조 하세요.

재난 복구 중에 통화 공원은 백업 풀의 통화 공원 응용 프로그램을 사용 하므로 기본 풀의 설정이 백업 되지 않습니다. 주 풀을 복구할 수 없고 기본 풀을 대체 하는 새 풀을 배포 하는 경우 기본 풀의 설정이 손실 되며, 통화 대기 설정 및 사용자 지정 된 모든 음악 온 오디오 파일을 새 풀에 다시 구성 해야 합니다.

다른 FQDN (정규화 된 도메인 이름)으로 새 풀을 배포 하 여 기본 풀을 바꾸려면 기본 풀과 연결 된 모든 통화 공원 궤도 범위를 새 풀의 FQDN으로 다시 할당 해야 합니다. 궤도 범위를 새 풀에 다시 할당 하려면 Lync Server 제어판 또는 **CsCallParkOrbit** cmdlet을 사용 하면 됩니다. **Set-CsCallParkOrbit** cmdlet에 대 한 자세한 내용은 [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

