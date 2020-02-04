---
title: 'Lync Server 2013: 환경 품질 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dbccfd145ad8143edab10f92a10901e626075e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>Lync Server 2013에서 환경 품질 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

환경 품질 (체감 품질)은 통화 및 세션과 관련 된 참가자, 장치 이름, 드라이버, IP 주소, 끝점 형식에 대 한 미디어 품질과 정보를 표시 하는 숫자 데이터를 기록 합니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 모니터링 계획 수립](lync-server-2013-planning-for-monitoring.md) 을 참조 하세요.

조직의 전체 조직 또는 각 사이트에 대해 체감 품질을 사용 하도록 설정 하려면 다음 절차를 사용 합니다.

<div>


> [!NOTE]  
> 체감 품질을 사용 하도록 설정 하려면 먼저 모니터링과 모니터링 백 엔드 데이터베이스를 구성 해야 합니다. 자세한 내용은 <A href="lync-server-2013-deploying-monitoring.md">Lync Server 2013에서 모니터링 배포</A>를 참조 하세요.



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 체감 품질을 사용 하도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.

4.  **경력 데이터** 페이지에서 테이블의 적절 한 컬렉션을 클릭 하 고 **작업**을 클릭 한 다음 **체감 품질 사용**을 클릭 합니다.

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 체감 품질 사용

Windows PowerShell 및 **Set-CsQoEConfiguration** cmdlet을 사용 하 여 체감 품질를 사용 하도록 설정할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>단일 위치에 대해 체감 품질을 사용 하도록 설정 하려면

  - 체감 품질을 사용 하도록 설정 하려면 EnableQoE 매개 변수를 True ($True)로 설정 합니다.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>단일 위치에 대해 체감 품질를 사용 하지 않도록 설정 하려면

  - 체감 품질를 사용 하지 않으려면 EnableQoE 매개 변수를 False ($False)로 설정 합니다. 이는 모니터링을 제거 하지 않습니다. 체감 품질 데이터의 컬렉션 및 저장소를 일시 중지 합니다.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>단일 명령을 사용 하 여 여러 위치에서 체감 품질을 사용 하도록 설정 하려면

  - 이 명령은 현재 조직에서 사용 중인 모든 체감 품질 구성 설정에 대해 체감 품질을 사용 하도록 설정 합니다.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

자세한 내용은 [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 모니터링 계획](lync-server-2013-planning-for-monitoring.md)  
[Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

