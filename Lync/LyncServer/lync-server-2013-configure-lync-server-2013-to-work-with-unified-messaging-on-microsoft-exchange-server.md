---
title: 'Lync Server 2013: Microsoft Exchange Server의 통합 메시징과 함께 작동하도록 Lync Server 2013 구성'
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
ms.openlocfilehash: 985b2d286f65be2353c2ace0d59872f4d0fc47ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>Microsoft Exchange Server의 통합 메시징과 함께 작동하도록 Lync Server 2013 구성

</div>

<div id="mainSection">

<div id="mainBody">

_**마지막으로 수정한 주제:** 2013-04-03_

이 단계를 수행 하려면 Exchange UM 통합 유틸리티 (OcsUmUtil. exe)가 필요 합니다. 이 도구는 다음의 Lync Server 2013 서버에 있습니다. \\프로그램 파일\\공통 파일\\Microsoft Lync Server 2013\\지원 폴더

<div>

## <a name="running-the-exchange-um-integration-utility"></a>Exchange UM 통합 유틸리티 실행

Exchange UM 통합 유틸리티는 다음 특성을 가진 사용자 계정에서 실행 해야 합니다.

  - RTCUniversalServerAdmins 및 RtcUniversalUserAdmins 그룹의 구성원 자격 (Exchange Server 통합 메시징 설정 읽기 권한이 포함 되어 있음)

  - 지정 된 OU (조직 구성 단위) 컨테이너에서 연락처 개체를 만들기 위한 도메인 내의 사용자 권한

Exchange UM 통합 유틸리티를 실행 하는 경우 다음 작업이 수행 됩니다.

  - 엔터프라이즈 음성 사용자가 사용할 각 자동 전화 교환 및 가입자 액세스 번호에 대 한 연락처 개체를 만듭니다.

  - 각 Enterprise Voice dial 계획의 이름이 해당 UM (통합 메시징) 다이얼 플랜 전화 컨텍스트와 일치 하는지 확인 합니다. 이 일치는 UM 다이얼 플랜이 Exchange 2010 서비스 팩 1 보다 *이전* 버전의 exchange에서 실행 되는 경우에만 필요 합니다.

> [!IMPORTANT]
> Exchange UM 통합 유틸리티를 실행 하기 전에 다음을 수행 해야 합니다.
> <ul>
> <li><p>Exchange 제품 설명서에 설명 된 대로 하나 이상의 Exchange UM 다이얼 플랜을 만듭니다.</p>
> <p>Microsoft Exchange Server 2010의 경우에 &quot;&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>는 UM 다이얼 플랜 만들기를 참조 하세요.</p>
> <p>Microsoft Exchange Server 2007 SP1(서비스 팩 1)의 경우에 &quot;&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>는 통합 메시징 SIP URI 다이얼 플랜을 만드는 방법을 참조 하세요.</p></li>
> <li><p><a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013에서 다이얼 플랜 만들기</a>에 설명 된 대로 하나 이상의 해당 Lync Server 다이얼 플랜을 만듭니다.</p></li>
> <ul><li>Microsoft Exchange Server 2010 SP1 이전 버전의 Exchange를 사용 하는 경우 Lync Server 2013 다이얼 플랜 <STRONG>간단한 이름</STRONG> 필드에 해당 하는 exchange UM (통합 메시징) SIP 다이얼 플랜의 FQDN (정규화 된 도메인 이름)을 입력 해야 합니다. Microsoft Exchange Server 2010 SP1 또는 최신 서비스 팩을 사용 하는 경우에는이 다이얼 플랜 이름 일치가 필요 하지 않습니다.</li></ul>
> <li>자동 전화 교환을 만들고 구독자 액세스 번호와 자동 전화 교환 번호가 모두 E 164 형식으로 되어 있는지 확인 합니다.</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>Exchange UM 통합 유틸리티를 실행 하려면

1.  프런트 엔드 서버에서 명령 프롬프트를 열고 **cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\지원을**입력 한 다음 enter 키를 누릅니다.

2.  **Ocsumutil**을 입력 한 다음 enter 키를 누릅니다.

3.  **데이터 로드** 를 클릭 하 여 신뢰할 수 있는 모든 Exchange 포리스트를 찾습니다.

4.  **SIP 다이얼** 플랜 목록에서 연락처 개체를 만들 UM SIP 다이얼 플랜을 선택한 다음 **추가**를 클릭 합니다.

5.  **연락처** 상자에서 기본 조직 구성 단위를 그대로 사용 하거나 **찾아보기를** 클릭 하 여 **OU 선택기**를 시작 합니다. **Ou** 선택 상자에서 ou를 선택 하 고 **확인**을 클릭 하거나 **새 ou** 만들기를 클릭 하 여 도메인의 루트 또는 다른 ou 아래에 새 조직 구성 단위를 만들 수 있습니다 (예: "OU = RTC 특수 계정, dc = fourthcoffee, dc = com" **) .를**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 선택 하거나 만든 OU의 DN (고유 이름)이 이제 <STRONG>조직 구성 단위</STRONG> 상자에 표시 됩니다.

    
    </div>

6.  **이름** 상자에서 기본 다이얼 플랜 이름을 그대로 사용 하거나 만들려는 연락처 개체의 새 표시 이름을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 예를 들어 구독자 액세스 연락처 개체를 만드는 경우 단순히 구독자 액세스 이름을 이름만 사용할 수 있습니다.

    
    </div>

7.  **Sip 주소** 상자에서 기본 sip 주소를 적용 하거나 새 sip 주소를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 새로운 SIP 주소를 입력 하는 경우 <STRONG>sip:</STRONG> (즉, 콜론을 포함 하 여 "sip:")로 시작 해야 합니다.

    
    </div>

8.  **서버 또는 풀** 목록에서 연락처 개체를 사용할 수 있는 Standard Edition Server 또는 프런트 엔드 풀을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 선택 하는 풀은 Enterprise Voice 및 Exchange UM을 배포 하는 사용자가 동일한 한 풀입니다.

    
    </div>

9.  **전화 번호** 목록에서 **전화 번호 입력** 또는 **Exchange UM에서이 조종사 번호 사용** 을 선택 하 고 전화 번호를 입력 합니다.

10. **연락처 유형** 목록에서 만들려는 연락처 유형을 선택 하 고 **확인**을 클릭 합니다.

11. 만들려는 추가 연락처 개체에 대해 1 ~ 10 단계를 반복 합니다.
    
    <div>
    

    > [!NOTE]  
    > 각 자동 전화 교환에 대해 하나 이상의 대화 상대를 만들어야 합니다. 외부 액세스를 원할 경우 구독자 액세스 연락처가 필요 하며 직접 안쪽 다이얼 (a) 번호를 지정 합니다.

    
    </div>

</div>

연락처 개체가 만들어졌는지 확인 하려면 Active Directory 사용자 및 컴퓨터를 열고 개체가 만들어진 OU를 선택 합니다. 연락처 개체가 세부 정보 창에 나타납니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

