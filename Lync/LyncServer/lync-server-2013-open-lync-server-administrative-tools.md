---
title: 'Lync Server 2013: Lync Server 관리 도구 열기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa84c132061cb599448b78cf7d4ffcc6bd7fa3d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Lync Server 2013 관리 도구 열기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-28_

이 항목의 절차를 사용 하 여 Lync Server 2013 토폴로지 배포, 구성 또는 문제 해결을 위한 관리 도구를 열 수 있습니다.

  - 배포 마법사

  - 토폴로지 작성기

  - Lync Server 제어판

  - Lync Server Management Shell

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>배포 마법사

다음 절차를 사용 하 여 배포 마법사를 로컬로 시작 하 여 Lync Server 2013 구성 요소 파일을 추가 하거나 제거 합니다.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Lync Server 2013 배포 마법사를 시작 하려면

1.  Lync Server 배포 마법사가 설치 되어 있는 컴퓨터에 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 로그온 합니다.

2.  **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 배포 마법사**를 클릭 합니다.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>토폴로지 작성기

다음 절차를 사용 하 여 토폴로지 작성기를 열고 Lync Server 2013 토폴로지에서 배포 하려는 서버를 정의 합니다.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Lync Server 2013 토폴로지 작성기를 열어 토폴로지를 디자인 하려면

1.  도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 서버에 Lync Server 2013을 설치 하는 데 필요한 토폴로지를 읽고, 게시 하거나, 사용 하려면 Domain Admins 그룹의 구성원 인 계정 및 RTCUniv을 사용 해야 합니다. ersalServerAdmins 그룹으로, 보관 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있으며, 이렇게 하면 토폴로지 작성기가 필요한 Dacl (임의 액세스 제어 목록)을 구성할 수 있습니다. 또는 해당 사용자 권한이 있는 계정

    
    </div>

2.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013 제어판

다음 절차 중 하나를 사용 하 여 Lync Server 2013 제어판을 열어 환경에서 서버, 사용자, 클라이언트 및 장치의 구성을 관리 합니다.

<div>


> [!NOTE]  
> CsAdministrator 역할에 할당 된 사용자 계정을 사용 하 여 Lync Server 2013 제어판에서 모든 작업을 수행할 수 있습니다. 다른 역할을 사용 하 여 Lync Server 2013 제어판에 로그온 하 여 수행 해야 하는 작업에 따라 특정 관리 작업을 수행할 수 있습니다. 예를 들어 CSArchivingAdministrator를 사용 하 여 Lync Server 2013 제어판에서 보관을 관리할 수 있습니다. 역할에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013의 역할 기반 액세스 제어 계획</A> 을 참조 하세요. 특정 작업을 수행 하는 데 사용할 수 있는 역할에 대 한 자세한 내용은 해당 작업에 대 한 설명서를 참조 하세요.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>조직의 방화벽에 포함 된 컴퓨터에서 Lync Server 2013 제어판을 열려면

1.  CsAdministrator 역할 또는 작업에 대 한 적절 한 사용자 권한 및 사용 권한이 있는 다른 역할에 할당 된 사용자 계정에서 최소 화면 해상도 1024 x 768을 사용 하 여 내부 배포의 컴퓨터에 로그온 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 관리 간단한 URL (simple resource locator)을 구성한 경우 조직의 방화벽에 포함 된 컴퓨터에서 실행 중인 인터넷 브라우저에서 Lync Server 2013 제어판에 액세스할 수 있습니다. 관리 간단한 URL을 구성 하는 방법에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-simple-urls.md">Lync server 2013에서 간단한 url에 대 한 계획</A> 을 참조 하 고 배포 설명서의 <A href="lync-server-2013-edit-or-configure-simple-urls.md">lync server 2013에서 간단한 url을 편집 또는 구성</A> 합니다.

    
    </div>

2.  브라우저 창을 열고 조직에 대해 구성 된 관리자 URL을 입력 합니다.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Lync Server 2013를 실행 하는 컴퓨터에서 Lync Server 2013 제어판을 열려면

1.  CsAdministrator 역할의 구성원 인 사용자 계정이 나 작업을 수행 하는 데 적절 한 사용자 권한 및 사용 권한이 있는 다른 역할의 경우 Lync Server 2013를 설치한 컴퓨터에 로그온 하거나 최소한 Lync Server 2013 administrat ive 도구. 설정을 구성 하려면 컴퓨터의 화면 해상도가 최소 1024 x 768 이상 이어야 합니다.

2.  Lync Server 2013 제어판: **시작**을 클릭 하 고 **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **Microsoft Lync Server 2013**를 차례로 가리킨 다음 **lync server 2013 제어판**을 클릭 합니다.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸

명령줄을 사용 하 여 사용자 환경에서 서버, 사용자, 클라이언트 및 장치를 관리 하려면 다음 절차를 사용 하 여 Lync Server 2013 관리 셸을 엽니다.

<div>


> [!NOTE]  
> CsAdministrator 역할에 할당 된 사용자 계정을 사용 하 여 Lync Server 2013 관리 셸에서 모든 작업을 수행할 수 있습니다. 수행 해야 하는 작업에 따라 다른 역할을 사용 하 여 특정 관리 작업을 수행 하도록 로그온 할 수 있습니다. 예를 들어 CSArchivingAdministrator를 사용 하 여 보관 관리와 관련 된 cmdlet을 실행할 수 있습니다. 역할에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013의 역할 기반 액세스 제어 계획</A> 을 참조 하세요. 특정 cmdlet을 실행 하는 데 사용할 수 있는 역할에 대 한 자세한 내용은 cmdlet에 대 한 설명서를 참조 하세요.<BR>Cmdlet에 따라 RTCUniversalServerAdmins, RTCUniversalUserAdmins 또는 RTCUniversalReadOnlyAdmins 그룹의 사용자 계정을 사용 하 여 특정 cmdlet을 실행할 수도 있습니다.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸을 열려면

  - Lync Server 2013 관리 셸이 아닌 Windows PowerShell 창을 열면 기본적으로 Lync Server 2013 cmdlet을 실행할 수 없습니다. Windows PowerShell 내에서 Lync Server 2013 cmdlet을 실행 하려면 Windows PowerShell 명령 프롬프트에서 다음을 입력 합니다.
    
    `Import-Module Lync`

  - Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 관리 도구 설치](lync-server-2013-install-lync-server-administrative-tools.md)  


[Lync Server 2013 관리 도구](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

