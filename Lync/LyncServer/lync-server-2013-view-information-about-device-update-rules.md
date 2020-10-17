---
title: 'Lync Server 2013: 장치 업데이트 규칙에 대 한 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fef5d58116da6b8cbc07ce2b16f3dd4f6b28ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506385"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Lync Server 2013의 장치 업데이트 규칙에 대 한 정보 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

업데이트를 적용할 장치의 유형, 모델 및 브랜드를 포함 하 여 이미 가져온 장치 업데이트 규칙에 대 한 세부 정보를 확인 합니다. 업데이트의 버전 및 유형 업데이트에 대 한 로캘 및 풀을 사용할 때 유용 합니다. 가져온 모든 장치 업데이트 규칙, 즉 승인 보류 중 (승인 됨), 회수 (복원 됨) 및 사용 하지 않기로 결정 한 (다시 설정)에 대 한 정보를 확인할 수 있습니다. Lync Server 제어판 또는 Windows PowerShell에서이 정보에 액세스할 수도 있습니다.

<div>


> [!NOTE]  
> 규칙 가져오기, 승인, 다시 설정, 복원 및 제거 방법에 대 한 자세한 내용은 <A href="lync-server-2013-device-update-rules.md">Lync Server 2013의 장치 업데이트 규칙</A>에 나열 된 항목을 참조 하십시오.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 장치 업데이트 규칙을 보려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **장치 업데이트** 탐색 단추를 클릭 합니다. 가져온 규칙은 **장치 업데이트** 페이지에 나열 됩니다.

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 규칙 보기

또한 Windows PowerShell 및 **get-csdeviceupdaterule** cmdlet을 사용 하 여 모든 장치 업데이트 규칙에 대 한 자세한 정보를 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 하세요.



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>모든 장치 업데이트 규칙을 보려면

  - 다음 명령은 조직에서 사용 하도록 구성 된 모든 장치 업데이트 규칙에 대 한 정보를 반환 합니다.
    
        Get-CsDeviceUpdateRule
    
    이 명령은 각 장치 업데이트 규칙에 대해 다음과 같은 정보를 반환 합니다.
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>특정 웹 서버에서 모든 장치 업데이트 규칙을 보려면

  - 특정 컴퓨터에서 장치 업데이트 규칙을 보려면 Filter 매개 변수 다음에 서버 Id와 와일드 카드 문자 ()를 사용 합니다 \* . 예제:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

자세한 내용은 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

