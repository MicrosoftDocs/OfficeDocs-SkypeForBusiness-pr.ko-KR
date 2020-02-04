---
title: 응답 그룹 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>응답 그룹 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-09-23_

사용자를 Lync Server 2013 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹을 마이그레이션하면 레거시 배포에서 Lync Server 2013 풀로 에이전트 그룹, 큐, 워크플로, 오디오 파일, 응답 그룹 연락처 개체를 복사 하는 작업이 포함 됩니다. 레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 호출이 Lync Server 2013 풀의 응답 그룹 응용 프로그램에 의해 처리 됩니다. 응답 그룹에 대 한 호출은 더 이상 레거시 풀에서 처리 되지 않습니다.

<div>


> [!NOTE]  
> 모든 사용자를 Lync Server 2013 풀로 이동 하기 전에 응답 그룹을 마이그레이션할 수 있지만 모든 사용자를 먼저 이동 하는 것이 좋습니다. 특히 응답 그룹 에이전트를 사용 하는 사용자는 Lync Server 2013 풀로 이동할 때까지 새로운 기능을 완전히 사용할 수 없습니다.



</div>

응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램이 포함 된 Lync Server 2013 풀을 배포 해야 합니다. 엔터프라이즈 음성을 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 되 고 활성화 됩니다. **Get-CsService – ApplicationServer** cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 설치 되어 있는지 확인할 수 있습니다.

<div>


> [!NOTE]  
> 이전 응답 그룹을 마이그레이션하기 전에 Lync Server 2013 풀에서 새 Lync Server 2013 응답 그룹을 만들 수 있습니다.



</div>

응답 그룹을 레거시 풀에서 Lync Server 2013로 마이그레이션하려면 **CsRgsConfiguration** cmdlet을 실행 합니다.

<div>


> [!IMPORTANT]  
> 응답 그룹 마이그레이션 cmdlet은 전체 풀에 대 한 응답 그룹 구성을 이동 합니다. 마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다.



</div>

응답 그룹을 마이그레이션한 후에는 Lync Server 제어판 또는 Lync Server Management Shell cmdlet을 사용 하 여 모든 에이전트 그룹, 큐 및 워크플로가 성공적으로 이동 되었는지 확인 해야 합니다.

응답 그룹을 마이그레이션하면 Lync Server 2010 응답 그룹이 제거 되지 않습니다. Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 마이그레이션한 후 응답 그룹을 관리 하는 경우 Lync Server 2010 응답 그룹과 Lync Server 2013 응답 그룹을 둘 다 볼 수 있습니다. Lync Server 2013 응답 그룹에만 업데이트를 적용 해야 합니다. Lync Server 2010 응답 그룹은 롤백 용도로만 유지 됩니다.

<div>


> [!WARNING]  
> 마이그레이션이 완료 되 고 새 응답 그룹이 만들어졌으면 lync server 제어판 및 Lync Server 관리 셸에서는 각 응답 그룹의 Lync Server 2010 및 Lync Server 2013 버전을 표시 합니다. Lync server 2010 응답 그룹을 제거 하는 데 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하지 마세요. 제거 하는 경우 마이그레이션 중에 만든 해당 응답 그룹의 작동이 중지 됩니다. Lync server 2010 응답 그룹을 해제 하면 lync server 2010 풀이 제거 됩니다.



</div>

<div>


> [!IMPORTANT]  
> 풀을 해제할 때까지 이전 배포에서 데이터를 제거 하지 않는 것이 좋습니다. 또한 마이그레이션한 후 즉시 응답 그룹을 내보낼 것을 적극 권장 합니다. Lync Server 2010 응답 그룹을 제거 해야 하는 경우 백업에서 응답 그룹을 복원 하 여 Lync Server 2013 응답 그룹을 다시 실행할 수 있습니다.



</div>

Lync Server 2013는 **워크플로 형식**이라는 새 응답 그룹 기능을 소개 합니다. **워크플로 유형은** **관리** 또는 **비관리형**일 수 있습니다. 모든 응답 그룹은 **워크플로 유형이** **비관리형** 으로 설정 되 고 빈 관리자 목록이 있는 상태로 마이그레이션됩니다.

**CsRgsConfiguration** cmdlet을 실행 하는 경우 롤백 목적으로 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 레거시 풀에 남아 있습니다. 그러나 레거시 풀로 롤백해야 하는 경우에는 요청 **이동 Applicationendpoint** cmdlet을 실행 하 여 연락처 개체를 레거시 풀로 다시 이동 해야 합니다.

응답 그룹 구성을 마이그레이션하는 다음 절차는 레거시 풀과 Lync Server 2013 풀 간에 일대일 관계를 사용 하는 것으로 가정 합니다. 마이그레이션 및 배포 중에 풀을 통합 하거나 분할할 계획 이라면 어떤 레거시 풀이 어떤 Lync Server 2013 풀에 매핑되는지 계획 해야 합니다.

<div>

## <a name="to-migrate-response-group-configurations"></a>응답 그룹 구성을 마이그레이션하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 관리자 권한이 있는 계정을 사용 하 여 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  런
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    예를 들면 다음과 같습니다.
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  응답 그룹 및 에이전트를 Lync Server 2013 풀로 마이그레이션한 후에는 에이전트가 로그인 하 고 로그 아웃 하는 데 사용 하는 URL이 Lync Server 2013 URL 이며 **도구** 메뉴에서 사용할 수 있습니다. 상담원에 게 책갈피 등의 모든 참조를 새 URL로 업데이트 하도록 알립니다.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면

1.  RTCUniversalReadOnlyAdmins 그룹의 구성원 이거나 적어도 Csviewis 관리자 역할의 구성원 인 계정으로 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 창에서 **응답 그룹**을 클릭 합니다.

4.  **워크플로** 탭에서 Lync Server 2010 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.

5.  **큐** 탭을 클릭 하 고 Lync Server 2010 환경의 모든 큐가 목록에 포함 되어 있는지 확인 합니다.

6.  **그룹** 탭을 클릭 하 고 Lync Server 2010 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Lync Server Management Shell을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면

1.  RTCUniversalReadOnlyAdmins 그룹의 구성원 이거나 적어도 Csviewis 관리자 역할의 구성원 인 계정으로 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.
    
    다음 cmdlet에 대 한 자세한 내용을 보려면 다음을 실행 합니다.
    
        Get-Help <cmdlet name> -Detailed

3.  런
    
        Get-CsRgsAgentGroup

4.  Lync Server 2010 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.

5.  런
    
        Get-CsRgsQueue

6.  Lync Server 2010 환경의 모든 큐가 목록에 포함 되어 있는지 확인 합니다.

7.  런
    
        Get-CsRgsWorkflow

8.  Lync Server 2010 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

