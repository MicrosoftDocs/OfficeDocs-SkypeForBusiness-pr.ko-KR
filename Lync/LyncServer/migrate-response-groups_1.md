---
title: 응답 그룹 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de012d0886c51cd70d5003beb24053ff86af05b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>응답 그룹 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

사용자를 Lync Server 2013 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹 마이그레이션에는 에이전트 그룹, 큐, 워크플로 및 오디오 파일을 복사 하 고 레거시 배포에서 Lync Server 2013 풀로 응답 그룹 대화 상대 개체를 이동 하는 작업이 포함 됩니다. 레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 통화가 Lync Server 2013 풀의 응답 그룹 응용 프로그램에 의해 처리 됩니다. 응답 그룹에 대한 호출은 더 이상 레거시 풀에서 처리되지 않습니다.

<div>


> [!NOTE]  
> 모든 사용자를 Lync Server 2013 풀로 이동 하기 전에 응답 그룹을 마이그레이션할 수 있지만 모든 사용자를 먼저 이동 하는 것이 좋습니다. 특히 응답 그룹 에이전트를 실행 하는 사용자는 Lync Server 2013 풀로 이동할 때까지 새 기능의 전체 기능을 사용할 수 없습니다.



</div>

응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램이 포함 된 Lync Server 2013 풀을 배포 해야 합니다. Enterprise Voice를 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 및 활성화 됩니다. **-Csservice** cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 설치 되어 있는지 확인할 수 있습니다.

<div>


> [!NOTE]  
> 레거시 응답 그룹을 마이그레이션하기 전에 Lync Server 2013 풀에서 새 Lync Server 2013 response 그룹을 만들 수 있습니다.



</div>

이전 풀의 응답 그룹을 Lync Server 2013로 마이그레이션하려면 **export-csrgsconfiguration** cmdlet을 실행 합니다. **Move-CsRgsConfiguration**을 실행하려면 먼저 WMI(Windows Management Instrumentation) Backward Compatibility 인터페이스 패키지를 설치해야 합니다. 이 응용 프로그램은 OCSWMIBC.msi를 실행하여 설치합니다. OCSWMIBC.msi는 설치 미디어의 Setup 폴더에 있습니다.

<div>


> [!IMPORTANT]  
> 응답 그룹 마이그레이션 cmdlet은 전체 풀에 대 한 응답 그룹 구성을 이동 합니다. 마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다.



</div>

응답 그룹을 마이그레이션한 후에는 공식 에이전트가 해당 응답 그룹에 로그인 하 여 아웃 하는 데 사용 하는 URL을 업데이트 하 고 Lync Server 제어판 또는 Lync Server 관리 셸 cmdlet을 사용 하 여 모든 에이전트 그룹, 큐 및 워크플로가 성공적으로 이동 되었는지 확인 해야 합니다.

<div>


> [!WARNING]  
> 응답 그룹을 마이그레이션할 때 Office Communications Server 2007 R2 응답 그룹은 제거 되지 않습니다. Office Communications Server 2007 R2 응답 그룹을 제거 하지 않습니다. Office Communications Server 2007 R2 응답 그룹을 제거 하면 Lync Server 2013의 응답 그룹이 작동 하지 않습니다.



</div>

<div>


> [!IMPORTANT]  
> 풀을 해제하기 전까지는 이전 배포에서 어떠한 데이터도 제거하지 않는 것이 좋습니다. 또한 마이그레이션 직후 응답 그룹을 내보내는 것이 좋습니다. Office Communications Server 2007 R2 응답 그룹을 제거한 후에는 응답 그룹을 백업에서 복원 하 여 Lync Server 2013 응답 그룹을 다시 실행 해 볼 수 있습니다.



</div>

**Move-CsRgsConfiguration** cmdlet을 실행하면 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 롤백 목적으로 레거시 풀에 보존됩니다. 하지만 레거시 풀로 롤백해야 하는 경우에는 **Move-CsApplicationEndpoint** cmdlet을 실행해서 연락처 개체를 다시 레거시 풀로 이동해야 합니다.

<div>


> [!IMPORTANT]  
> 풀을 해제하기 전까지는 레거시 풀에서 응답 그룹 데이터를 삭제하지 않는 것이 좋습니다.



</div>

응답 그룹 구성을 마이그레이션하기 위해 수행 하는 절차에서는 레거시 풀과 Lync Server 2013 풀 간에 일대일 관계가 있다고 가정 합니다. 마이그레이션 및 배포 중에 풀을 통합 하거나 분할 하려는 경우에는 Lync Server 2013 풀에 대 한 레거시 풀 맵을 계획 해야 합니다.

<div>

## <a name="to-migrate-response-group-configurations"></a>응답 그룹 구성을 마이그레이션하려면

1.  설치 미디어의 Setup 폴더에서 OCSWMIBC.msi를 찾고 설치합니다.

2.  RTCUniversalServerAdmins 그룹의 구성원이거나 이와 동등한 관리자 권한 및 사용 권한을 가진 계정을 사용하여 컴퓨터에 로그온합니다.

3.  Lync Server 관리 셸을 엽니다.

4.  명령줄에 다음을 입력합니다.
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    예:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Office Communications Server 2007 R2 환경에서 Microsoft Office Communicator 2007 r 2에 대 한 응답 그룹 탭을 배포한 경우 Office Communicator 2007 R2 tabs.xml 파일에서 해당 탭을 제거 합니다.
    
    <div>
    

    > [!NOTE]  
    > 공식 에이전트는 호출을 수신하기 전에 응답 그룹 탭을 사용하여 응답 그룹에 로그인했습니다. 응답 그룹 탭을 배포한 경우 Office Communicator 2007 R2 tabs.xml 파일을 배포할 때 해당 위치를 선택 합니다.

    
    </div>

6.  에이전트가 응답 그룹에서 로그인 및 로그아웃하는 데 필요한 업데이트된 URL을 사용자에게 제공합니다.
    
    <div>
    

    > [!NOTE]  
    > 일반적으로 https://webpoolFQDN/RgsClients/Tab.aspx webpoolFQDN은 Lync Server 2013로 마이그레이션한 풀과 연결 된 웹 풀의 FQDN (정규화 된 도메인 이름)이 됩니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync의 <STRONG>Tools (도구</STRONG> ) 메뉴에서 URL을 사용할 수 있으므로 사용자가 lync 2013로 업그레이드 한 후에는이 단계가 필요 하지 않습니다.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면

1.  Lync Server 제어판을 엽니다.

2.  왼쪽 탐색 창에서 **응답 그룹**을 클릭합니다.

3.  **워크플로** 탭에서 Office Communications Server 2007 R2 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.

4.  **큐** 탭을 클릭 하 고 Office Communications Server 2007 R2 환경의 모든 큐가 목록에 포함 되었는지 확인 합니다.

5.  **그룹** 탭을 클릭 하 고 Office Communications Server 2007 R2 환경의 모든 에이전트 그룹이 목록에 포함 되었는지 확인 합니다.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Cmdlet을 사용하여 응답 그룹 마이그레이션을 확인하려면

1.  Lync Server 관리 셸을 엽니다.
    
    다음 cmdlet에 대한 자세한 내용을 보려면 다음을 실행합니다.
    
        Get-Help <cmdlet name> -Detailed

2.  명령줄에 다음을 입력합니다.
    
        Get-CsRgsAgentGroup

3.  Office Communications Server 2007 R2 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.

4.  명령줄에 다음을 입력합니다.
    
        Get-CsRgsQueue

5.  Office Communications Server 2007 R2 환경의 모든 큐가 목록에 포함 되었는지 확인 합니다.

6.  명령줄에 다음을 입력합니다.
    
        Get-CsRgsWorkflow

7.  Office Communications Server 2007 R2 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

