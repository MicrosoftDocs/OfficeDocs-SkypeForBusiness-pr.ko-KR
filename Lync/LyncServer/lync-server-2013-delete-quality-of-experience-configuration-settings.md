---
title: 'Lync Server 2013: 경험 수준 구성 설정 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c2a3d9b8907d888f7edbd65c550315dfabe3306
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 환경 품질 구성 설정 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

QoE(체감 품질) 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다. 이러한 메트릭은 통화 정보 기록과 같은 기타 데이터와 별도로 데이터베이스에 저장되므로 다른 데이터 기록에 관계없이 QoE를 설정 및 해제할 수 있습니다.

Microsoft Lync Server 2013을 설치 하면 QoE 구성 설정의 단일 전역 컬렉션이 만들어집니다. 관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다. 이러한 설정은 전역 범위 또는 사이트 범위에서 구성할 수 있습니다. 사이트 범위의 설정을 삭제할 경우 QoE는 전역 설정을 사용하여 해당 사이트에서 관리됩니다.

또한 전역 설정을 “삭제”할 수도 있습니다. 그러나 전역 설정을 사실상 삭제되지 않습니다. 대신에, 해당 모음에 있는 모든 속성이 기본값으로 다시 설정됩니다. 예를 들면 기본적으로 지우기는 QoE 구성 설정 모음에서 사용할 수 있습니다. 지우기를 사용할 수 없도록 전역 모음을 수정한다고 가정하겠습니다. 나중에 전역 설정을 삭제하면 모든 속성이 기본값으로 다시 설정됩니다. 따라서 이 경우에는 지우기를 다시 사용할 수 있게 됩니다.

Lync Server 제어판을 사용 하거나 [remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet을 사용 하 여 QoE 구성 설정을 제거할 수 있습니다.

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 QoE 구성 설정을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **체감 품질 데이터**를 클릭합니다.

4.  **체감 품질 데이터** 페이지에서 원하는 정책을 클릭하고 **편집**을 클릭한 다음 **삭제**를 클릭합니다.

5.  **확인**을 클릭합니다.

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 QoE 구성 설정 제거

QoE 구성 설정은 Windows PowerShell 및 **remove-csqoeconfiguration** cmdlet을 사용 하 여 삭제할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>지정된 QoE 구성 설정 모음을 제거하려면

  - 이 명령은 Redmond 사이트에 적용된 QoE 구성 설정을 제거합니다.
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용된 모든 QoE 구성 설정을 제거하려면

  - 이 명령은 사이트 범주에 적용된 모든 QoE 구성 설정을 제거합니다.
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 모니터링을 사용할 수 없는 경우 모든 QoE 구성 설정을 제거하려면

  - 이 명령은 QoE 모니터링을 사용할 수 없는 경우 모든 QoE 구성 설정을 제거합니다.
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

자세한 내용은 [Remove-remove-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

