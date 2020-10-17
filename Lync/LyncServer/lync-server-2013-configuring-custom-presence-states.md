---
title: 'Lync Server 2013: 사용자 지정 현재 상태 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd551ede7d7be7e631c229e99613cfc8baa006eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526995"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Lync Server 2013에서 사용자 지정 현재 상태 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-10_

Lync 2013에서 사용자 지정 현재 상태를 정의 하려면 XML 사용자 지정 현재 상태 구성 파일을 만든 다음 Lync Server 관리 셸 cmdlet **New-csclientpolicy** 또는 Parameter CustomStateURL과 함께 **csclientpolicy** 를 사용 하 여 해당 위치를 지정 합니다.

구성 파일에는 다음과 같은 속성이 있습니다.

  - 사용자 지정 현재 상태는 사용 가능, 사용 중, 방해 금지 상태 표시기로 구성할 수 있습니다.

  - Availability 특성은 사용자 지정 상태의 상태 텍스트와 연결 된 현재 상태 표시기를 결정 합니다. 이 항목 뒷부분의 예제에서는 집에서 작업 상태 텍스트가 녹색 (사용 가능) 현재 표시기 오른쪽에 표시 됩니다.

  - 상태 텍스트의 최대 길이는 64 자입니다.

  - 사용자 지정 현재 상태를 최대 4 개까지 추가할 수 있습니다.

  - CustomStateURL 매개 변수는 구성 파일의 위치를 지정 합니다. Lync 2013에서 SIP 고급 보안 모드는 기본적으로 사용 하도록 설정 되어 있으므로 HTTPS를 사용 하도록 설정 된 웹 서버에 사용자 지정 현재 상태 구성 파일을 저장 해야 합니다. 그렇지 않으면 Lync 2013 클라이언트가 해당 클라이언트에 연결할 수 없게 됩니다. 예를 들어 유효한 주소는 `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` 입니다.

<div>


> [!NOTE]  
> 프로덕션 환경에서는 권장 되지 않지만 EnableSIPHighSecurityMode 레지스트리 설정을 사용 하 여 클라이언트에서 SIP 고급 보안 모드를 사용 하지 않도록 설정 하 여 HTTPS가 아닌 파일 공유에 있는 구성 파일을 테스트할 수 있습니다. 그런 다음 CustomStateURL 레지스트리 설정을 사용 하 여 구성 파일에 대해 HTTPS가 아닌 위치를 지정할 수 있습니다. Lync 2013는 Lync 2010 레지스트리 설정을 준수 하지만 레지스트리 하이브가 업데이트 되었습니다. 레지스트리 설정은 다음과 같이 만들 수 있습니다. 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>유형: DWORD</P>
> <P>값 데이터: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Type: String (REG_SZ)</P>
> <P>값 데이터 (예): file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml 또는 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

XML 구성 파일에 하나 이상의 LCID (로캘 ID) 스키마를 지정 하 여 사용자 지정 현재 상태를 지역화 합니다. 이 항목의 뒷부분에 나오는 예제에서는 영어-미국 (1033), 노르웨이어-복말 (1044), 프랑스어-프랑스 (1036) 및 터키어 (1055)로 지역화 하는 방법을 보여 줍니다. Lcid 목록은 Microsoft에서 할당 한 로캘 Id를 참조 하십시오 <https://go.microsoft.com/fwlink/p/?linkid=157331> .

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>Lync 2013에 사용자 지정 현재 상태를 추가 하려면

1.  다음 예제의 형식을 사용 하는 XML 구성 파일을 만듭니다.
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  HTTPS를 사용 하도록 설정 된 웹 서버에 XML 구성 파일을 저장 합니다. 이 예제에서 파일의 이름은 Presence.xml로 저장 됩니다 https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml .

3.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

4.  Lync Server 관리 셸에서 다음과 같은 명령을 사용 하 여 XML 구성 파일의 위치를 정의 합니다.
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  **부여-CSClientPolicy** cmdlet을 사용 하 여 사용자에 게이 새 정책을 할당 합니다.

자세한 내용은 Lync Server 관리 셸 설명서에서 [New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 및 [Grant-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 를 참조 하십시오.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>기본적으로 Lync Server 2013는 &nbsp; 3 시간 마다 클라이언트 정책과 설정을 업데이트 합니다.</P>
> <LI>
> <P>CustomStateURL과 같은 이전 릴리스의 그룹 정책 설정을 계속 사용 하려는 경우 Lync 2013은 새 정책 레지스트리 하이브에 있는 설정 (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync))을 인식 합니다. 그러나 서버 기반 클라이언트 정책이 우선적으로 적용 됩니다.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

