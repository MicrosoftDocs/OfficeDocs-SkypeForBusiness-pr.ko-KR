---
title: 응답 그룹 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bf7f0fa04f494eb49a0537011d5f9affcc68065
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>응답 그룹 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

사용자를 Lync Server 2013 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다. 응답 그룹 마이그레이션에는 에이전트 그룹, 큐, 워크플로, 오디오 파일 복사, 레거시 배포에서 Lync Server 2013 풀로 응답 그룹 연락처 개체 이동 등이 포함 됩니다. 레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 호출이 Lync Server 2013 풀의 응답 그룹 응용 프로그램에 의해 처리 됩니다. 응답 그룹에 대 한 호출은 더 이상 레거시 풀에서 처리 되지 않습니다.

<div>


> [!NOTE]  
> 모든 사용자를 Lync Server 2013 풀로 이동 하기 전에 응답 그룹을 마이그레이션할 수 있지만 모든 사용자를 먼저 이동 하는 것이 좋습니다. 특히 응답 그룹 에이전트를 사용 하는 사용자는 Lync Server 2013 풀로 이동할 때까지 새로운 기능을 완전히 사용할 수 없습니다.



</div>

응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램이 포함 된 Lync Server 2013 풀을 배포 해야 합니다. 엔터프라이즈 음성을 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 되 고 활성화 됩니다. **Get-CsService – ApplicationServer** cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 설치 되어 있는지 확인할 수 있습니다.

<div>


> [!NOTE]  
> 이전 응답 그룹을 마이그레이션하기 전에 Lync Server 2013 풀에서 새 Lync Server 2013 응답 그룹을 만들 수 있습니다.



</div>

응답 그룹을 레거시 풀에서 Lync Server 2013로 마이그레이션하려면 **CsRgsConfiguration** cmdlet을 실행 합니다. **CsRgsConfiguration**를 실행 하려면 먼저 WMI (Windows Management Instrumentation) 이전 버전과의 호환성 인터페이스 패키지를 설치 해야 합니다. OCSWMIBC. msi를 실행 하 여이 응용 프로그램을 설치 합니다. 설정 폴더의 설치 미디어에서 OCSWMIBC .msi를 찾을 수 있습니다.

<div>


> [!IMPORTANT]  
> 응답 그룹 마이그레이션 cmdlet은 전체 풀에 대 한 응답 그룹 구성을 이동 합니다. 마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다.



</div>

응답 그룹을 마이그레이션한 후에는 공식 에이전트가 응답 그룹에 로그인 및 로그 아웃 하는 데 사용 하는 URL을 업데이트 하 고 Lync Server 제어판 또는 Lync Server Management Shell cmdlet을 사용 하 여 모든 에이전트 그룹, 큐 및 워크플로가 이동 되었는지 확인 해야 합니다. 함.

<div>


> [!WARNING]  
> 응답 그룹을 마이그레이션하면 Office Communications Server 2007 R2 응답 그룹이 제거 되지 않습니다. Office Communications Server 2007 R2 응답 그룹을 제거 하지 마세요. Office Communications Server 2007 R2 응답 그룹을 제거 하면 Lync Server 2013의 응답 그룹이 작동을 중지 합니다.



</div>

<div>


> [!IMPORTANT]  
> 풀을 해제할 때까지 이전 배포에서 데이터를 제거 하지 않는 것이 좋습니다. 또한 마이그레이션한 후 즉시 응답 그룹을 내보낼 것을 적극 권장 합니다. Office Communications Server 2007 R2 응답 그룹이 제거 되 면 백업에서 응답 그룹을 복원 하 여 Lync Server 2013 응답 그룹을 다시 실행할 수 있습니다.



</div>

**CsRgsConfiguration** cmdlet을 실행 하는 경우 롤백 목적으로 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 레거시 풀에 남아 있습니다. 그러나 레거시 풀로 롤백해야 하는 경우에는 요청 **이동 Applicationendpoint** cmdlet을 실행 하 여 연락처 개체를 레거시 풀로 다시 이동 해야 합니다.

<div>


> [!IMPORTANT]  
> 풀을 해제할 때까지 레거시 풀에서 응답 그룹 데이터를 삭제 하지 않는 것이 좋습니다.



</div>

응답 그룹 구성을 마이그레이션하기 위해 사용 하는 절차는 레거시 풀과 Lync Server 2013 풀 사이에 일대일 관계를 사용 하는 것으로 가정 합니다. 마이그레이션 및 배포 중에 풀을 통합 하거나 분할할 계획 이라면 어떤 레거시 풀이 어떤 Lync Server 2013 풀에 매핑되는지 계획 해야 합니다.

<div>

## <a name="to-migrate-response-group-configurations"></a>응답 그룹 구성을 마이그레이션하려면

1.  설치 미디어의 설치 폴더에서 OCSWMIBC msi.dll을 찾아 설치 합니다.

2.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 관리자 권한이 있는 계정을 사용 하 여 컴퓨터에 로그온 합니다.

3.  Lync Server 관리 셸을 엽니다.

4.  명령줄에 다음을 입력 합니다.
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    예를 들면 다음과 같습니다.
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Office Communications Server 2007 R2 환경에서 Microsoft Office Communicator 2007 R2에 대 한 응답 그룹 탭을 배포한 경우 Office Communicator 2007 R2 탭 .xml 파일에서 탭을 제거 합니다.
    
    <div>
    

    > [!NOTE]  
    > 공식 에이전트는 응답 그룹 탭을 사용 하 여 응답 그룹에 로그인 한 후 전화를 받을 수 있습니다. 응답 그룹 탭을 배포한 경우 Office Communicator 2007 R2 탭 .xml 파일을 배포 했을 때의 위치를 선택 합니다.

    
    </div>

6.  상담원에 게 응답 그룹에 로그인 하 고 로그 아웃 해야 하는 업데이트 된 URL을 제공 합니다.
    
    <div>
    

    > [!NOTE]  
    > URL은 일반적으로 https://webpoolFQDN/RgsClients/Tab.aspxwebpoolFQDN이 Lync Server 2013에 방금 마이그레이션한 풀과 연결 된 웹 풀의 FQDN (정규화 된 도메인 이름)입니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync의 <STRONG>도구</STRONG> 메뉴에서 URL을 사용할 수 있기 때문에 사용자가 lync 2013으로 업그레이드 한 후에는이 단계가 필요 하지 않습니다.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면

1.  Lync Server 제어판을 엽니다.

2.  왼쪽 탐색 창에서 **응답 그룹**을 클릭 합니다.

3.  **워크플로** 탭에서 Office Communications Server 2007 R2 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.

4.  **큐** 탭을 클릭 하 고 Office Communications Server 2007 R2 환경의 모든 큐가 목록에 포함 되어 있는지 확인 합니다.

5.  **그룹** 탭을 클릭 하 고 Office Communications Server 2007 R2 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Cmdlet을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면

1.  Lync Server 관리 셸을 엽니다.
    
    다음 cmdlet에 대 한 자세한 내용을 보려면 다음을 실행 합니다.
    
        Get-Help <cmdlet name> -Detailed

2.  명령줄에 다음을 입력 합니다.
    
        Get-CsRgsAgentGroup

3.  Office Communications Server 2007 R2 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.

4.  명령줄에 다음을 입력 합니다.
    
        Get-CsRgsQueue

5.  Office Communications Server 2007 R2 환경의 모든 큐가 목록에 포함 되어 있는지 확인 합니다.

6.  명령줄에 다음을 입력 합니다.
    
        Get-CsRgsWorkflow

7.  Office Communications Server 2007 R2 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

