---
title: 'Lync Server 2013: Microsoft Exchange Server의 통합 메시징과 함께 작동 하도록 Lync Server 2013 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65908f1b142c72f584c48493023803e5dfd56208
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Microsoft Exchange Server의 통합 메시징과 함께 작동 하도록 Lync Server 2013 구성

</div>

<div id="mainSection">

<div id="mainBody">

_**마지막으로 수정 된 항목:** 2013-04-03_

이 단계에서는 Exchange UM 통합 유틸리티(OcsUmUtil.exe)가 필요합니다. 이 도구는의에 있는 Lync Server 2013 서버에 있습니다. \\프로그램 파일\\공용 파일\\Microsoft Lync Server 2013\\Support 폴더입니다.

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Exchange UM 통합 유틸리티 실행

Exchange UM 통합 유틸리티는 다음과 같은 사용자 계정에서 실행해야 합니다.

  - RTCUniversalServerAdmins 및 RtcUniversalUserAdmins 그룹의 구성원(Exchange Server 통합 메시징 설정을 읽을 수 있는 권한 포함)

  - 도메인 내에서 지정 된 OU (조직 구성 단위) 컨테이너에 연락처 개체를 만들 수 있는 사용자 권한

Exchange UM 통합 유틸리티를 실행하면 다음 작업이 수행됩니다.

  - Enterprise Voice 사용자가 사용할 각 자동 전화 교환 및 구독자 액세스 번호에 대한 연락처 개체를 만듭니다.

  - 각 Enterprise Voice 다이얼 플랜의 이름이 해당 UM (통합 메시징) 다이얼 플랜 전화 컨텍스트와 일치 하는지 확인 합니다. 이 일치는 UM 다이얼 플랜이 Exchange 2010 SP1 (서비스 팩 1) *이전의* exchange 버전에서 실행 되는 경우에만 필요 합니다.

> [!IMPORTANT]
> Exchange UM 통합 유틸리티를 실행 하기 전에 다음을 수행 해야 합니다.
> <ul>
> <li><p>Exchange 제품 설명서에 설명 된 대로 하나 이상의 Exchange UM 다이얼 플랜을 만듭니다.</p>
> <p>Microsoft Exchange Server 2010의 경우에 &quot;&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>는 UM 다이얼 플랜 만들기를 참조 하세요.</p>
> <p>Microsoft Exchange Server 2007 SP1 (서비스 팩 1)의 경우 통합 &quot;메시징 SIP URI 다이얼 플랜&quot; 을 만드는 방법을 참조 하세요 <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</p></li>
> <li><p><a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013의 다이얼 플랜 만들기</a>에 설명 된 대로 해당 하는 lync server 다이얼 플랜을 하나 이상 만듭니다.</p></li>
> <ul><li>Microsoft Exchange Server 2010 s p 1 보다 이전 버전의 Exchange를 사용 하는 경우 Lync Server 2013 다이얼 플랜 <STRONG>단순한 이름</STRONG> 필드에 해당 하는 exchange UM (통합 메시징) SIP 다이얼 플랜의 FQDN (정규화 된 도메인 이름)을 입력 해야 합니다. Microsoft Exchange Server 2010 SP1 또는 최신 서비스 팩을 사용 하는 경우에는이 다이얼 플랜 이름 일치가 필요 하지 않습니다.</li></ul>
> <li>자동 전화 교환을 만들고 구독자 액세스 번호와 자동 전화 교환 번호가 모두 E.164 형식인지 확인합니다.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Exchange UM 통합 유틸리티를 실행하려면

1.  프런트 엔드 서버에서 명령 프롬프트를 열고 **cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**를 입력 한 다음 enter 키를 누릅니다.

2.  **OcsUmUtil.exe**를 입력하고 Enter 키를 누릅니다.

3.  **데이터 로드**를 클릭하여 모든 신뢰할 수 있는 Exchange 포리스트를 찾습니다.

4.  **SIP 다이얼 플랜** 목록에서 연락처 개체를 만들 UM SIP 다이얼 플랜을 선택하고 **추가**를 클릭합니다.

5.  **연락처** 상자에서 기본 조직 구성 단위를 사용하거나 **찾아보기**를 클릭하여 **OU 선택기**를 시작합니다. **OU 선택기** 상자에서 OU를 선택하고 **확인**을 클릭하거나 **새 OU 만들기**를 클릭하여 루트 또는 도메인의 다른 OU 아래에 새 조직 구성 단위(예: "OU=RTC Special Accounts,DC=fourthcoffee,DC=com")를 만들고 **확인**을 클릭할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 이제 선택하거나 만든 OU의 DN(고유 이름)이 <STRONG>조직 구성 단위</STRONG> 상자에 표시됩니다.

    
    </div>

6.  **이름** 상자에서 기본 다이얼 플랜 이름을 적용하거나 만들고 있는 연락처 개체에 대해 새 표시 이름을 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > 예를 들어 구독자 액세스 연락처 개체를 만들고 있는 경우에는 구독자 액세스라고 명명하면 됩니다.

    
    </div>

7.  **SIP 주소** 상자에서 기본 SIP 주소를 그대로 적용하거나 새 SIP 주소를 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > 새 SIP 주소를 입력할 경우 이 주소는 <STRONG>SIP:</STRONG>(즉 콜론을 포함하여 "SIP:")로 시작되어야 합니다.

    
    </div>

8.  **서버 또는 풀** 목록에서 연락처 개체를 사용 하도록 설정할 Standard Edition Server 또는 프런트 엔드 풀을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > Enterprise Voice 및 Exchange UM 사용자가 배포된 풀을 선택하는 것이 좋습니다.

    
    </div>

9.  **전화 번호** 목록에서 **전화 번호 입력** 또는 **Exchange UM에서 이 파일럿 번호 사용**을 선택한 다음 전화 번호를 입력합니다.

10. **연락처 유형** 목록에서 만들 연락처 유형을 선택하고 **확인**을 클릭합니다.

11. 추가로 만들 연락처 개체에 대해 1-10단계를 반복합니다.
    
    <div>
    

    > [!NOTE]  
    > 각 자동 전화 교환에 대해 적어도 하나의 연락처 개체를 만들어야 하며, 외부 액세스를 원하는 경우에는 구독자 액세스 연락처도 필요하고 DID(Direct Inward Dial) 번호도 지정해야 합니다.

    
    </div>

</div>

연락처 개체가 만들어졌는지 확인하려면 Active Directory 사용자 및 컴퓨터를 열고 개체를 만든 OU를 선택하십시오. 연락처 개체가 세부 정보 창에 나타나야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

