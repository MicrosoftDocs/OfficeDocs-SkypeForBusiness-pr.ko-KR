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
ms.openlocfilehash: f7c6c3b7c3b5d78324fe9c674650dd94338baea4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Lync Server 2013의 재해 복구 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-01-26_

Lync Server 2013 풀 서버에 대 한 시스템 복구를 수행 하 여 문서화 된 재난 복구 프로세스를 테스트 합니다. 이 테스트를 통해 단일 서버에 대한 전체 하드웨어 오류를 시뮬레이트하고 리소스, 계획, 데이터를 복구에 사용할 수 있습니다. 조직에서 매번 다른 서버나 장비의 다른 부분에 발생한 오류를 테스트하도록 매월 다른 부분에 중점을 두어 테스트해 보세요.

조직에서 재해 복구 테스트를 수행하는 일정은 경우에 따라 다릅니다. 재해 복구 테스트가 무시되거나 중단될 수는 없습니다.

<div>


Lync Server 2013 토폴로지, 정책 및 구성 설정을 파일로 내보냅니다. 특히 이 파일은 업그레이드, 하드웨어 오류 또는 다른 일부 문제로 인해 데이터가 손실된 후 이 정보를 중앙 관리 저장소에 복원하는 데 사용될 수 있습니다.

다음 명령에 표시 된 대로 Lync Server 2013 토폴로지, 정책 및 구성 설정을 중앙 관리 저장소 또는 로컬 컴퓨터로 가져옵니다.

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

프로덕션 Lync Server 2013 데이터를 백업 하려면 다음을 수행 합니다.

  - 표준 SQL Server 백업 프로세스를 사용 하 여 데이터베이스를 파일 또는 테이프 덤프 장치에 덤프 하 여 RTC 및 LCSLog 데이터베이스를 백업 합니다.

  - 타사 백업 응용 프로그램을 사용하여 데이터를 파일이나 테이프에 백업합니다.

  - Export-CsUserData cmdlet을 사용하여 전체 RTC 데이터베이스의 XML 내보내기를 만듭니다.

  - 파일 시스템 백업 또는 타사를 통해 모임 콘텐츠 및 준수 로그를 백업합니다.

  - 내보내기-CsConfiguration 명령줄 도구를 사용 하 여 Lync Server 2013 설정을 백업 합니다.

장애 조치(failover) 절차의 첫 번째 단계에는 사용자를 프로덕션 풀에서 재해 복구 풀로 강제 이동하는 작업이 포함되어 있습니다.

프로덕션 풀은 사용자 재배치를 수락하는 데 사용할 수 없으므로 강제 이동이 적용됩니다.

Lync Server 2013 이동 사용자 프로세스는 RTC SQL 데이터베이스의 레코드 업데이트 외에 사용자 계정 개체의 특성을 효과적으로 변경 하는 것입니다.

이 데이터는 다음 두 가지 프로세스를 통해 복원될 수 있습니다.

  - RTC 데이터베이스는 표준 SQL Server 복원 프로세스를 사용 하거나 타사 백업/복원 유틸리티를 사용 하 여 원본 백업 덤프 장치에서 복원할 수 있습니다.

  - 사용자 연락처 데이터는 프로덕션 SQL Server 내보내기를 통해 만들어진 XML 파일을 사용하여 DBIMPEXP.exe 유틸리티로 복원될 수 있습니다.

이 데이터를 복원한 후에는 사용자가 재해 복구 Lync Server 2013 풀에 효과적으로 연결 하 고 평소 대로 작동할 수 있습니다.

사용자가 재해 복구 Lync Server 2013 풀에 연결할 수 있도록 하려면 DNS 레코드 변경이 필요 합니다.

프로덕션 Lync Server 2013 풀은 다음의 자동 구성 및 DNS SRV 레코드를 사용 하는 클라이언트에서 참조 합니다.

  - SRV: \_sip. \_tls. \<도메인\> /CNAME: SIP. \<도메인\>

  - CNAME: SIP. \<도메인\> /cvc-pool-1. \<도메인\>

장애 조치(failover)를 원활하게 하려면 DROCSPool FQDN을 참조하도록 이 CNAME 레코드를 업데이트해야 합니다.

  - CNAME: SIP. \<도메인\> /DROCSPool. \<도메인\>

  - Sip. \<도메인\>

  - AV.\<도메인\>

  - webconf. \<도메인\>

  - OCSServices. \<도메인\>

<div>


> [!IMPORTANT]  
> 자세한 관리 및 관리 절차는 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Lync Server 2013 백업 및 복원</A>을 참조 하세요.



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

