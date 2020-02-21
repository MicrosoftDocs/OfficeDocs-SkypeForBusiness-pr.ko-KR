---
title: 명시적으로 지원 또는 제한 되지 않는 클라이언트에 대 한 기본 작업 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f2b88b43c41a5a8bf990a72f0fdfef1c5537e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Lync Server 2013에서 명시적으로 지원 또는 제한 되지 않는 클라이언트에 대 한 기본 작업 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

Lync Server 2013 환경에서 지원할 클라이언트 버전을 지정 하는 것 외에, 아직 버전 정책이 정의 되어 있지 않은 클라이언트에 대 한 기본 작업을 지정할 수도 있습니다. 이를 통해 Lync Server 환경에서 사용 되는 클라이언트 버전을 제한 하 여 여러 클라이언트 버전 지원과 관련 된 비용을 제어할 수 있습니다.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>명시적으로 지원 또는 제한되지 않는 클라이언트에 대한 기본 동작을 수정하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **클라이언트 버전 구성**을 클릭합니다.

4.  **클라이언트 버전 구성** 페이지의 목록에서 **전역** 구성을 두 번 클릭합니다.

5.  **클라이언트 버전 구성 편집** 대화 상자에서 **버전 제어 사용** 확인란이 선택되어 있는지 확인하고 **기본 동작** 아래에서 다음 중 하나를 선택합니다.
    
      - **허용**   클라이언트 버전이 **클라이언트 버전 정책** 목록의 필터와 일치 하지 않으면 클라이언트 로그온을 허용 합니다.
    
      - **차단**   클라이언트 버전이 **클라이언트 버전 정책** 목록의 필터와 일치 하지 않으면 클라이언트 로그온을 방지 합니다.
    
      - **Url로 차단**   클라이언트 버전이 **클라이언트 버전 정책** 목록의 필터와 일치 하지 않으면 클라이언트 로그온을 차단 하 고, 새 클라이언트를 다운로드할 수 있는 URL이 포함 된 오류 메시지를 포함 합니다.
    
      - **Url로 허용**   클라이언트 버전이 **클라이언트 버전 정책** 목록의 필터와 일치 하지 않으면 클라이언트 로그온을 허용 하 고, 새 클라이언트를 다운로드할 수 있는 URL이 포함 된 오류 메시지를 포함 합니다.

6.  **URL로 차단**을 선택한 경우 오류 메시지에 포함할 클라이언트 다운로드 URL을 **URL** 상자에 입력합니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-disable-client-version-control"></a>클라이언트 버전 제어를 사용하지 않도록 설정하려면

  - 버전 제어를 사용하지 않도록 설정하여 클라이언트 버전에 관계없이 모든 클라이언트의 로그온을 허용하려면 **버전 제어 사용** 확인란 선택을 취소하고 **커밋**을 클릭합니다.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 기본 작업 수정

사용자가 명시적으로 지원 되지 않거나 클라이언트 버전 정책을 통해 제한 되지 않은 클라이언트를 사용 하 여 로그온 하려고 할 때 수행 되는 기본 작업은 Windows PowerShell 명령줄 인터페이스와 **CsClientVersionPolicy** cmdlet을 사용 하 여 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>액세스를 차단 하는 기본 작업을 구성 하려면

  - 다음 명령은 Redmond 사이트 차단을 위한 기본 작업을 설정합니다. 이 명령은 클라이언트 버전 구성 규칙이 없는 모든 클라이언트의 등록을 차단합니다.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>액세스를 허용 하도록 기본 작업을 구성 하려면

  - 이 예에서 Redmond 사이트에 대한 기본 작업은 허용으로 설정됩니다. 이 명령은 클라이언트 버전 구성 규칙이 없는 모든 클라이언트의 등록을 허용합니다.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

자세한 내용은 [설정-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

