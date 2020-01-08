---
title: 장치 업데이트 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d5b53ff6e876a2c5226b6728e0ebde95d55e7ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 장치 업데이트 구성 설정 컬렉션 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

Windows PowerShell 및 **CsDeviceUpdateConfiguration** cmdlet을 사용 하 고 **CsDeviceUpdateConfiguration** cmdlet을 사용 하 여 수정 하 여 장치 업데이트 구성 설정을 만들 수 있습니다 (사이트 범위에만 해당). 이러한 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>기본 값을 사용 하는 장치 업데이트 구성 설정을 만들려면

  - 이 명령은 Redmond 사이트에 대 한 새 장치 업데이트 구성 설정 집합을 만듭니다.
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    선행 명령에 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에 모든 속성에 대 한 기본값이 사용 됩니다.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>장치 업데이트 구성 설정을 만들 때 단일 속성 값을 변경 하려면

  - 다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다. 예를 들어 기본적으로 21 일 마다 오래 된 로그 파일을 삭제 하는 장치 업데이트 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>장치 업데이트 구성 설정을 만들 때 여러 속성 값을 변경 하려면

  - 여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다. 예를 들어이 명령은 로그 정리 간격을 21 일로, 로그 플러시 간격을 30 분으로 설정 합니다.
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

기존 장치 구성 설정을 수정 하는 방법에 대 한 자세한 내용은 [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요. 구성 설정 컬렉션을 만드는 방법에 대 한 자세한 내용은 [새 CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

