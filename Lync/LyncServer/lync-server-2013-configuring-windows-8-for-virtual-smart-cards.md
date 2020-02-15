---
title: 'Lync Server 2013: 가상 스마트 카드에 대해 Windows 8 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8fe9fb9bcca80e7e84f19bdc484dc693b1ee68
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Lync Server 2013를 사용 하 여 가상 스마트 카드를 사용 하도록 Windows 8 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-03_

2 단계 인증 및 스마트 카드 기술을 배포할 때 고려해 야 하는 한 가지 요인은 구현 비용입니다. Windows 8에서는 새로운 여러 보안 기능을 제공 하며, 가장 흥미로운 새로운 기능 중 하나는 가상 스마트 카드에 대 한 지원입니다.

규정 버전 1.2을 충족 하는 TPM (신뢰할 수 있는 플랫폼 모듈) 칩이 설치 된 컴퓨터의 경우 조직은 하드웨어에 추가 투자 없이 스마트 카드 로그온 이점을 얻을 수 있습니다. 자세한 내용은 Windows 8에서 [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365)가상 스마트 카드 사용을 참조 하십시오.

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>가상 스마트 카드에 대해 Windows 8을 구성 하려면

1.  Lync 사용 가능 사용자의 자격 증명을 사용 하 여 Windows 8 컴퓨터에 로그인 합니다.

2.  Windows 8 시작 화면에서 커서를 화면의 오른쪽 아래 모서리로 이동 합니다.

3.  **검색** 옵션을 선택한 다음 **명령 프롬프트**를 검색 합니다.

4.  **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.

5.  다음 명령을 실행 하 여 TPM (신뢰할 수 있는 플랫폼 모듈) 관리 콘솔을 엽니다.
    
        Tpm.msc

6.  TPM 관리 콘솔에서 TPM 사양 버전이 1.2 이상 인지 확인 합니다.
    
    <div>
    

    > [!NOTE]  
    > 호환 되는 TPM (트러스트 플랫폼 모듈)을 찾을 수 없다는 대화 상자가 표시 되 면 컴퓨터에 호환 되는 TPM 모듈이 있고 시스템 BIOS에서 사용 하도록 설정 되어 있는지 확인 합니다.

    
    </div>

7.  TPM 관리 콘솔 닫기

8.  명령 프롬프트에서 다음 명령을 사용 하 여 새 가상 스마트 카드를 만듭니다.
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > 가상 스마트 카드를 만들 때 사용자 지정 PIN 값을 제공 하려면 대신/tpin 프롬프트를 사용 합니다.

    
    </div>

9.  명령 프롬프트에서 다음 명령을 실행 하 여 컴퓨터 관리 콘솔을 엽니다.
    
        CompMgmt.msc

10. 컴퓨터 관리 콘솔에서 **장치 관리**를 선택 합니다.

11. **스마트 카드 판독기**를 확장 합니다.

12. 새 가상 스마트 카드 판독기가 만들어졌는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

