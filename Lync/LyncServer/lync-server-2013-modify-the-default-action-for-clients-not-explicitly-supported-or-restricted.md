---
title: 명시적으로 지원 되거나 제한 되지 않은 클라이언트에 대 한 기본 작업 수정
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
ms.openlocfilehash: 0262bface172c965d12fc276bc08882cac8348ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Lync Server 2013에서 명시적으로 지원 되거나 제한 되지 않은 클라이언트에 대 한 기본 작업 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

Lync Server 2013 환경에서 지원 하려는 클라이언트 버전을 지정 하는 것 외에도 아직 버전 정책이 정의 되어 있지 않은 클라이언트에 대 한 기본 작업을 지정할 수 있습니다. 이를 통해 Lync Server 환경에서 사용 되는 클라이언트 버전을 제한 하 여 여러 클라이언트 버전 지원과 관련 된 비용을 제어할 수 있습니다.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>명시적으로 지원 되거나 제한 되지 않은 클라이언트에 대 한 기본 작업을 수정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **클라이언트 버전 구성을**클릭 합니다.

4.  **클라이언트 버전 구성** 페이지의 목록에서 **전역** 구성을 두 번 클릭 합니다.

5.  **클라이언트 버전 구성 편집** 대화 상자에서 **버전 제어 사용** 확인란이 선택 되어 있는지 확인 한 다음 **기본 동작**에서 다음 중 하나를 선택 합니다.
    
      - **허용**   -클라이언트 버전이 **클라이언트 버전 정책** 목록의 필터와 일치 하지 않는 경우 클라이언트에서 로그온 할 수 있습니다.
    
      - **Block**   은 클라이언트 버전이 **클라이언트 버전 정책** 목록의 필터와 일치 하지 않는 경우 클라이언트가 로그온 할 수 없도록 합니다.
    
      - **Url로 차단**   클라이언트 버전이 **클라이언트 버전 정책** 목록의 필터와 일치 하지 않는 경우 클라이언트가 로그온 할 수 없으며 최신 클라이언트를 다운로드 하는 URL이 포함 된 오류 메시지가 포함 됩니다.
    
      - **사용 url**   허용 클라이언트 버전이 **클라이언트 버전 정책** 목록의 필터와 일치 하지 않으면 클라이언트가 로그온 할 수 있도록 허용 하 고 최신 클라이언트를 다운로드할 수 있는 URL이 포함 된 오류 메시지를 포함 합니다.

6.  **Url을 사용 하 여 차단**을 선택한 경우 **url** 상자의 오류 메시지에 포함할 클라이언트 다운로드 URL을 입력 합니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-disable-client-version-control"></a>클라이언트 버전 제어를 사용 하지 않도록 설정 하려면

  - 모든 클라이언트가 클라이언트 버전에 관계 없이 로그온 할 수 있도록 버전 제어를 사용 하지 않도록 설정 하려면 **버전 제어 사용** 확인란의 선택을 취소 한 다음 **커밋을**클릭 합니다.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 기본 작업 수정

사용자가 명시적으로 지원 되지 않거나 클라이언트 버전 정책에 따라 제한 되지 않은 클라이언트를 사용 하 여 로그인을 시도할 때 수행할 기본 작업은 Windows PowerShell 명령줄 인터페이스 및 **Set CsClientVersionPolicy** cmdlet을 사용 하 여 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Access를 차단 하도록 기본 작업을 구성 하려면

  - 다음 명령은 Redmond 사이트 블록에 대 한 기본 작업을 설정 합니다. 이렇게 하면 클라이언트 버전 구성 규칙이 없는 모든 클라이언트에 대 한 등록이 차단 됩니다.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>액세스를 허용 하는 기본 작업을 구성 하려면

  - 이 예제에서는 Redmond 사이트의 기본 작업이 허용으로 설정 됩니다. 이렇게 하면 클라이언트 버전 구성 규칙이 없는 모든 클라이언트에 대 한 등록이 허용 됩니다.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

자세한 내용은 [설정 된 CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.

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

