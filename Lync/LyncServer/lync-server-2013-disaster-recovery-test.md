---
title: 'Lync Server 2013: 재해 복구 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2d36ec6ad1afb8c41c7c5f614e90e03ce4d9282
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528955"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a>Lync Server 2013의 재해 복구 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-01-26_

Lync Server 2013 풀 서버에 대 한 시스템 복구를 수행 하 여 문서화 된 재해 복구 프로세스를 테스트 합니다. 이 테스트에서는 한 서버에 대 한 전체 하드웨어 오류를 시뮬레이션 하며, 리소스, 계획 및 데이터를 복구에 사용할 수 있도록 보장 합니다. 조직에서 매번 다른 서버나 기타 장비의 오류를 테스트할 수 있도록 매월 테스트 초점을 회전 해 봅니다.

조직에서 재해 복구 테스트를 수행 하는 일정은 다를 수 있습니다. 재해 복구 테스트는 무시 되거나 연락이 중단 되지 않도록 하는 것이 매우 중요 합니다.

<div>


Lync Server 2013 토폴로지, 정책 및 구성 설정을 파일로 내보냅니다. 즉, 업그레이드, 하드웨어 오류 또는 다른 문제로 인해 데이터가 손실 된 후에이 파일을 중앙 관리 저장소로 복원 하는 데 사용할 수 있습니다.

다음 명령과 같이 Lync Server 2013 토폴로지, 정책 및 구성 설정을 중앙 관리 저장소나 로컬 컴퓨터로 가져옵니다.

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

프로덕션 Lync Server 2013 데이터를 백업 하려면 다음을 수행 합니다.

  - 표준 SQL Server 백업 프로세스를 사용 하 여 데이터베이스를 파일 또는 테이프 덤프 장치로 덤프 하 여 RTC 및 LCSLog 데이터베이스를 백업 합니다.

  - 타사 백업 응용 프로그램을 사용 하 여 데이터를 파일 또는 테이프에 백업 합니다.

  - Export-CsUserData cmdlet을 사용 하 여 전체 RTC 데이터베이스의 XML 내보내기를 만들 수 있습니다.

  - 파일 시스템 백업 또는 타사를 사용 하 여 모임 콘텐츠 및 준수 로그를 백업 합니다.

  - Export-CsConfiguration 명령줄 도구를 사용 하 여 Lync Server 2013 설정을 백업 합니다.

장애 조치 (failover) 절차의 첫 번째 단계에는 프로덕션 풀에서 재해 복구 풀로 사용자를 강제로 이동 하는 작업이 포함 됩니다.

이는 프로덕션 풀을 사용 하 여 사용자의 재배치가 허용 되지 않으므로 강제 이동이 됩니다.

Lync Server 2013 move user 프로세스는 RTC SQL 데이터베이스의 레코드 업데이트 외에 사용자 계정 개체의 특성을 실제로 변경 하는 작업입니다.

이 데이터는 다음의 두 프로세스를 통해 복원할 수 있습니다.

  - RTC 데이터베이스는 표준 SQL Server 복원 프로세스를 사용 하 여 프로덕션 SQL Server에서 원본 백업 덤프 장치 로부터 복원 하거나 타사 백업/복원 유틸리티를 사용 하 여 복원할 수 있습니다.

  - 프로덕션 SQL Server 내보내기에서 만든 XML 파일을 사용 하 여 DBIMPEXP.exe 유틸리티로 사용자 연락처 데이터를 복원할 수 있습니다.

이 데이터를 복원한 후에는 사용자가 재해 복구 Lync Server 2013 풀에 효과적으로 연결 하 고 평소와 같이 작동할 수 있습니다.

사용자가 재해 복구 Lync Server 2013 풀에 연결할 수 있도록 하려면 DNS 레코드를 변경 해야 합니다.

프로덕션 Lync Server 2013 풀은 다음의 자동 구성 및 DNS SRV 레코드를 사용 하는 클라이언트에서 참조 됩니다.

  - SRV: \_ sip. \_ ls.\<domain\> /CNAME: SIP\<domain\>

  - CNAME: SIP\<domain\> /cvc-pool-1.\<domain\>

장애 조치 (failover)를 촉진 하기 위해이 CNAME 레코드를 업데이트 하 여 DROCSPool FQDN을 참조 해야 합니다.

  - CNAME: SIP\<domain\> /DROCSPool.\<domain\>

  - 호흡.\<domain\>

  - AV.\<domain\>

  - fea-webconf-service.\<domain\>

  - OCSServices\<domain\>

<div>


> [!IMPORTANT]  
> 관리 절차에 대 한 자세한 내용은 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">백업 및 복원 Lync Server 2013</A>을 참조 하십시오.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Lync Server 2013의 백업 및 고가용성 cmdlet](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[가져오기-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Lync Server 2013 백업 및 복원](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Lync Server 2013 재해 복구, 고가용성 및 백업 서비스 관리](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

