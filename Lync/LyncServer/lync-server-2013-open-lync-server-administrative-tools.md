---
title: 'Lync Server 2013: Lync Server 관리 도구 열기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b4f6bef254b54a6979d9a4b6976f5e31df60268
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Lync Server 2013 관리 도구 열기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-28_

이 항목의 절차를 사용 하 여 Lync Server 2013 토폴로지를 배포, 구성 또는 문제 해결할 관리 도구를 열 수 있습니다.

  - 배포 마법사

  - 토폴로지 작성기

  - Lync Server 제어판

  - Lync Server 관리 셸

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>배포 마법사

다음 절차에 따라 배포 마법사를 로컬로 시작 하 여 Lync Server 2013 구성 요소 파일을 추가 하거나 제거 합니다.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Lync Server 2013 배포 마법사를 시작 하려면

1.  Lync Server 배포 마법사가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013**, **Lync server 배포 마법사**를 차례로 클릭 합니다.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>토폴로지 작성기

다음 절차에 따라 토폴로지 작성기를 열어 Lync Server 2013 토폴로지에서 배포할 서버를 정의 합니다.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Lync Server 2013 토폴로지 작성기를 열어 토폴로지를 디자인 하려면

1.  토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.
    
    <div>
    

    > [!NOTE]  
    > 로컬 Users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 서버에 Lync Server 2013을 설치 하는 데 필요한 토폴로지를 읽거나 게시 하거나 사용 하도록 설정 하려면 Domain Admins 그룹의 구성원 인 계정 및 RTCUniv을 사용 해야 합니다. ersalServerAdmins 그룹과, 토폴로지 작성기가 필요한 Dacl (임의 액세스 제어 목록)을 구성할 수 있도록 보관 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기, 쓰기 및 수정)이 포함 되어 있습니다. 또는 이와 동등한 사용자 권한이 있는 계정을 사용 합니다.

    
    </div>

2.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Lync Server 2013 제어판

다음 절차 중 하나를 사용 하 여 Lync Server 2013 제어판을 열어 해당 환경의 서버, 사용자, 클라이언트 및 장치에 대 한 구성을 관리 합니다.

<div>


> [!NOTE]  
> CsAdministrator 역할에 할당 된 사용자 계정을 사용 하 여 Lync Server 2013 제어판의 작업을 수행할 수 있습니다. 다른 역할을 사용 하 여 Lync Server 2013 제어판에 로그온 하 여 수행 해야 하는 작업에 따라 특정 관리 작업을 수행할 수 있습니다. 예를 들어 CSArchivingAdministrator을 사용 하 여 Lync Server 2013 제어판에서 보관을 관리할 수 있습니다. 역할에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어 계획</A> 을 참조 하십시오. 특정 작업을 수행하기 위해 사용할 수 있는 역할에 대한 자세한 내용은 해당 작업에 대한 설명서를 참조하십시오.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>조직의 방화벽 내부에 있는 모든 컴퓨터에서 Lync Server 2013 제어판을 열려면

1.  CsAdministrator 역할 또는 수행할 작업에 적절 한 사용자 권한 및 사용 권한이 있는 다른 역할에 할당 된 사용자 계정에서 최소 화면 해상도 1024 x 768을 사용 하 여 내부 배포의 컴퓨터에 로그온 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 관리 단순 URL (uniform resource locator)을 구성한 경우 조직의 방화벽 내 모든 컴퓨터에서 실행 되는 인터넷 브라우저에서 Lync Server 2013 제어판에 액세스할 수 있습니다. 관리 단순 URL을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 계획 설명서에서 <A href="lync-server-2013-planning-for-simple-urls.md">Lync server 2013의 단순 Url 계획</A> 및 <A href="lync-server-2013-edit-or-configure-simple-urls.md">lync server 2013의 단순 url 편집 또는 구성</A> 를 참조 하십시오.

    
    </div>

2.  브라우저 창을 열고 조직에 구성된 관리 URL을 입력합니다.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Lync Server 2013를 실행 하는 컴퓨터에서 Lync Server 2013 제어판을 열려면

1.  CsAdministrator 역할 또는 수행할 작업에 적절 한 사용자 권한 및 사용 권한이 있는 다른 역할의 구성원 인 사용자 계정에서 Lync Server 2013을 설치 하는 컴퓨터에 로그온 하거나 최소한 Lync Server 2013 administrat ive 도구 설정을 구성 하려면 컴퓨터의 화면 해상도가 최소 1024 x 768 이어야 합니다.

2.  Lync Server 2013 시작 제어판: **시작**, **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **Microsoft lync Server 2013**를 가리키고 **Lync server 2013 제어판**을 클릭 합니다.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸

다음 절차에 따라 명령줄을 사용 하 여 사용자 환경의 서버, 사용자, 클라이언트 및 장치를 관리 하기 위해 Lync Server 2013 관리 셸을 엽니다.

<div>


> [!NOTE]  
> CsAdministrator 역할에 할당 된 사용자 계정을 사용 하 여 Lync Server 2013 관리 셸에서 모든 작업을 수행할 수 있습니다. 수행해야 하는 작업에 따라 다른 역할을 사용하여 로그온해서 특정 관리 작업을 수행할 수 있습니다. 예를 들어 CSArchivingAdministrator를 사용하여 보관 관리와 관련된 cmdlet을 실행할 수 있습니다. 역할에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어 계획</A> 을 참조 하십시오. 특정 cmdlet을 실행하기 위해 사용할 수 있는 역할에 대한 자세한 내용은 해당 cmdlet에 대한 설명서를 참조하십시오.<BR>또한 cmdlet에 따라 RTCUniversalServerAdmins, RTCUniversalUserAdmins 또는 RTCUniversalReadOnlyAdmins 그룹의 사용자 계정을 사용하여 특정 cmdlet을 실행할 수도 있습니다.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸을 열려면

  - Lync Server 2013 관리 셸이 아닌 Windows PowerShell 창을 여는 경우 기본적으로 Lync Server 2013 cmdlet을 실행할 수 없습니다. Windows PowerShell 내에서 Lync Server 2013 cmdlet을 실행 하려면 Windows PowerShell 명령 프롬프트에 다음을 입력 합니다.
    
    `Import-Module Lync`

  - **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

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

