---
title: 'Lync Server 2013: Lync Server 2013 관리 팩 가져오기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd5f09d80aa86c9c0f692fbe0e744a445067e74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Lync Server 2013 관리 팩 가져오기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

System center Operations Manager에서 모니터링할 수 있는 항목 및 해당 항목을 모니터링 하는 방법 및 알림을 트리거하는 방법을 결정 하는 관리 팩을 설치 하 여 System Center Operations Manager의 기능을 확장할 수 있습니다. 한다고. Lync Server 2013에는 다음과 같은 기능을 제공 하는 2 개의 System Center Operations Manager 관리 팩이 포함 되어 있습니다.

  - 구성 요소 및 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp (사용자 관리 팩)는 이벤트 로그에 기록 되 고, 성능 카운터에서 등록 되거나, CDR (통화 정보 기록) 또는 경력 품질 (QoE)에 기록 된 Lync Server 문제를 추적 합니다. 데이터베이스. 중요 한 문제의 경우 System Center Operations Manager를 구성 하 여 전자 메일, 인스턴트 메시지 또는 SMS (Short Message Service) 메시징을 통해 관리자에 게 즉시 알릴 수 있습니다. SMS는 모바일 장치 간에 문자 메시지를 전송하기 위해 사용되는 기술입니다.
    
    <div>
    

    > [!NOTE]  
    > Operations Manager 알림을 구성 하는 방법에 대 한 자세한 내용은 TechNet 라이브러리의 구성 알림 <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>를 참조 하십시오.

    
    </div>

  - Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp (Active Monitoring Management Pack)는 시스템에 로그인 하거나 인스턴트 메시지를 교환 하거나 공개 된 휴대폰에 전화를 거는 것과 같은 주요 Lync Server 구성 요소를 테스트 합니다. 전화 네트워크 (PSTN) 이러한 테스트는 Lync Server 가상 트랜잭션 cmdlet을 사용 하 여 수행 됩니다. 예를 들어 **Test-CsIM** cmdlet을 사용해서 테스트 사용자의 쌍 간에 IM(인스턴트 메시징) 대화를 시뮬레이션할 수 있습니다. 시뮬레이션된 메시징 대화가 실패하면 알림이 생성됩니다.

관리 팩을 가져와야 합니다. 관리 팩을 가져오지 않으면 Operations Manager를 사용 하 여 Lync Server 이벤트를 모니터링 하거나 Lync Server 가상 트랜잭션을 실행할 수 없습니다.

구성 요소 및 사용자 관리 팩은 Lync Server 2013을 모니터링 하는 데만 사용 됩니다. Lync Server 2013와 Lync Server 2010이 모두 설치 되어 있는 공존 시나리오에서는 lync Server 2010 컴퓨터용 Lync Server 2010 관리 팩을 계속 사용 해야 합니다.

<div>


> [!NOTE]  
> Lync Server 2010 용 관리 팩에는 Lync Server 2010 모니터링 관리 팩과 Lync Server 2010 그룹 채팅 모니터링 관리 팩이 포함 되어 있습니다.



</div>

다음 도구 중 하나를 사용해서 관리 팩을 가져올 수 있습니다.

  - **System Center Operations manager**   이 방법을 사용 하는 경우 Operations manager를 사용 하 여 Lync Server에 대 한 모니터링을 추가 합니다.

  - **Operations manager shell**   operations manager 셸을 사용 하 여 직접 가져오거나 System Center Operations Manager 콘솔을 사용 하 여 관리 팩을 가져올 때 발생 하는 문제를 해결할 수 있습니다.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager를 사용 하 여 관리 팩 가져오기

1.  Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 및 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 파일을 다운로드합니다.

2.  System Center Operations Manager에서 **관리**를 클릭 합니다.

3.  **관리** 창에서 **관리 팩**을 마우스 오른쪽 단추로 클릭한 후 **관리 팩 가져오기**를 클릭합니다.

4.  **관리 팩 선택** 대화 상자에서 **추가**를 클릭한 후 **디스크에서 추가**를 클릭합니다.

5.  **온라인 카탈로그 연결** 대화 상자에서 작업 관리자가 온라인에서 Lync Server 관리 팩에 대 한 종속성이 있는지 확인 하지 않도록 하려면 **취소** 를 클릭 합니다. System Center Operations Manager 2012를 사용 하는 경우 **아니요**를 클릭 합니다.

6.  **가져올 관리 팩 선택** 대화 상자에서 **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** 및 **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** 파일을 찾아서 선택한 후 **열기**를 클릭합니다. 대화 상자에서 여러 파일을 선택하려면 첫 번째 파일을 클릭하고, Ctrl 키를 누른 상태에서 두 번째 파일을 클릭합니다.

7.  **관리 팩 선택** 대화 상자에서 **설치**를 클릭합니다. 오류 메시지가 표시되고 설치가 실패하면 일반적으로 관리 팩 파일이 Windows 사용자 계정 컨트롤에서 보호되는 폴더에 있기 때문일 수 있습니다. 이 경우 파일을 다른 폴더에 복사한 후 가져오기 및 설치 프로세스를 다시 시작합니다.

8.  **관리 팩 선택** 대화 상자에서 **닫기**를 클릭합니다. 가져오기 및 설치 프로세스는 완료하는 데 몇 분 정도 걸릴 수 있습니다.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager 셸을 사용 하 여 관리 팩 가져오기

일반적으로 Operations Manager를 사용 하 여 관리 팩을 가져오는 것이 더 쉽습니다. 그러나 오류가 발생 하 고 가져오기가 실패 하면 콘솔에서 적절 한 오류 보고서를 제공 하지 않을 수 있습니다. Operations Manager 셸에서는 비교를 통해 자세한 정보를 제공 합니다. Operations Manager를 사용 하는 경우 관리 팩을 가져오는 동안 문제가 발생 하면 Operations Manager 셸을 사용 하 여 팩을 가져옵니다. Operations Manager 셸은 가져오기가 실패 한 이유를 확인 하는 데 도움이 되는 추가 정보를 제공 합니다.

System Center Operations Manager 2007 R2를 사용 하는 경우 다음 절차를 수행 합니다.

1.  **시작**, **모든 프로그램**, **System Center Operations Manager 2007 R2**를 차례로 클릭 한 다음 **Operations manager Shell**을 클릭 합니다.

2.  Operations Manager 셸에서 명령 프롬프트에 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 파일 복사본의 실제 경로를 사용 하 여 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  첫 번째 관리 팩을 가져온 후 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 파일의 복사본에 대한 경로를 사용해서 프로세스를 반복합니다.
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Operations Manager 셸을 닫습니다.

System Center Operations Manager 2012를 사용 하는 경우에는이 절차를 대신 수행 합니다.

1.  **시작**, **모든 프로그램**, **Microsoft System Center 2012**, **operations manager**, **operations manager 셸을**차례로 클릭 합니다.

2.  Operations Manager 셸에서 명령 프롬프트에 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 파일 복사본의 실제 경로를 사용 하 여 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  첫 번째 관리 팩을 가져온 후 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 파일의 복사본에 대한 경로를 사용해서 프로세스를 반복합니다.
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

