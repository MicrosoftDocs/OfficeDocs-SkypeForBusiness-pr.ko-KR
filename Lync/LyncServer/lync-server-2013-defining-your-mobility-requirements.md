---
title: 'Lync Server 2013: 모바일 기능 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da630e422aaf7068a4252333d5221f552bce525
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 모바일 기능 요구 사항 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 모바일 기능에 대 한 계획 단계 중에 Lync 2010 모바일 및 Lync 2013 모바일 클라이언트를 사용 하는 경우에는 배포 단계를 결정 하는 결정을 내려야 합니다.

고려해 야 할 결정 사항은 다음과 같습니다.

  - **Lync 모바일 클라이언트에 대해 자동 검색을 사용할지 여부**
    
    자동 검색을 지원 하려면 새 내부 및 외부 DNS (Domain Name System) 레코드를 만들고, 프런트 엔드 서버, 디렉터 및 역방향 프록시의 인증서에 주체 대체 이름을 추가 하 고, 기존 게시 규칙을 수정 해야 합니다. 역방향 프록시 자세한 내용은 [Lync Server 2013에서 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)참조 하세요. 자동 검색을 사용 하면 사용자가 모바일 장치 설정에 Url을 입력 하지 않고도 회사 네트워크 내부 또는 외부의 어디에서 든 지 Lync Server 2013 웹 서비스를 자동으로 찾을 수 있습니다.
    
    자동 검색 대신 수동 설정을 사용 하는 경우 모바일 사용자가 모바일 장치에서 다음 Url을 수동으로 입력 해야 합니다.
    
      - 외부\<액세스용 Https://extpoolfqdn\>https://
    
      - 내부\<액세스용 Https://intpoolfqdn\>/AutoDiscover/autodiscoverservice/Root
    
    자동 검색은 사용하는 것이 좋습니다. 수동 설정은 주로 문제 해결 시에 사용됩니다.

  - **자동 검색을 지원하기로 결정하는 경우 각 SIP 도메인의 주체 대체 이름으로 역방향 프록시의 인증서를 업데이트할지 여부**
    
    SIP 도메인이 여러 개인 경우 역방향 프록시에서 공용 인증서를 업데이트하려면 비용이 매우 많이 들 수 있습니다. 이러한 경우에는 초기 자동 검색 서비스 요청이 포트 443에서 HTTPS를 사용 하는 대신 포트 80에서 HTTP를 사용 하도록 자동 복구를 구현 하도록 선택할 수 있습니다. 그러나 권장 되는 방법은 아닙니다. 이 대체 방법을 선택 하는 경우 역방향 프록시에서 인증서를 업데이트할 필요가 없지만 포트 80의 HTTP에 대 한 웹 게시 규칙을 만들어야 합니다. 자세한 내용은 [Lync Server 2013에서 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)참조 하세요.

  - **Lync 모바일 클라이언트를 지원할 위치(회사 네트워크 내부와 외부에서 모두 지원/회사 네트워크 내부에서만 지원)**
    
    모바일 클라이언트를 네트워크 내부와 외부에서 모두 지원하는 경우 모바일 장치가 어디서나 모바일 기능에 액세스할 수 있습니다. 기본 구성에서는 회사 네트워크 내부와 외부에서 모두 클라이언트가 지원됩니다.
    
    기본 구성을 사용 하면 모바일 클라이언트 트래픽이 외부 사이트를 통과 하 게 되지만 모바일 클라이언트 트래픽이 내부 회사 네트워크로 제한 될 수 있습니다. 내부 네트워크에 대 한 트래픽을 제한 하면 사용자가 네트워크 내부에 있을 때만 모바일 장치에서 Lync 모바일 응용 프로그램을 사용할 수 있습니다.
    
    Mcx mobility service 및 Lync 2010 Mobile을 사용 하 여 모바일 기능을 지 원하는 배포의 경우, **Set-CsMcxConfiguration** cmdlet을 실행 합니다. 내부 전용으로 모바일 기능을 설정 하려면 다음과 같은 명령을 사용 합니다.
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > 지 수에는 추가 구성이 필요 하지 않습니다. (C)는 동등한 내부 전용 구성을 사용 하지 않습니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server&nbsp;2013 프런트 엔드 서버 또는 프런트 엔드 풀을 사용 하는 경우 lync <STRONG></STRONG> Server 2010&nbsp;프런트 엔드 서버 또는 프런트 엔드 풀이 없으면 <STRONG>쿠키 기반 지 속성에 대 한 요구 사항은 없습니다</STRONG>. Lync Server 2010&nbsp;프런트 엔드 서버 또는 프런트 엔드 풀을 유지 해야 하는 경우에는 쿠키 기반 지 속성에 대해 동일한 규칙이 여전히 Lync server 2010에 적용 됩니다.

    
    </div>

  - **Apple iOS 장치 및 Windows Phone에 대해 푸시 알림을 지원할지 여부**
    
    푸시 알림을 지원하는 경우 지원되는 Apple iOS 장치 및 Windows Phone에서는 모바일 응용 프로그램이 비활성 상태일 때 발생하는 이벤트의 알림을 받게 됩니다. Edge 서버가 Lync Online 데이터 센터에 있는 클라우드 기반 Lync Server 푸시 알림 서비스와의 페더레이션 관계를 갖도록 구성 하 고, cmdlet을 실행 하 여 푸시 알림을 사용 하도록 설정 해야 합니다.
    
    Wi-fi 네트워크를 통해 푸시 알림을 지원 하려는 경우에는 모바일 장치 공급자의 3G 또는 데이터 네트워크를 통한 푸시 알림을 지 원하는 것 외에도 엔터프라이즈 Wi-fi 네트워크에서 포트 5223 아웃 바운드를 열어야 합니다. Wi-Fi만 사용하는 모바일 장치와 실내 수신 상태가 좋지 않은 모바일 장치에 한해 Wi-Fi 네트워크를 통해 푸시 알림을 지원할 수 있습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 열기 포트 TCP 5223는 Lync 2010 모바일 클라이언트를 실행 하는 Apple 장치를 지 원하는 경우에만 필요 합니다.

    
    </div>
    
    푸시 알림을 지원 하지 않으면 Apple 모바일 장치 및 Windows phone 사용자는 모바일 응용 프로그램이 비활성 상태일 때 발생 하는 이벤트 (예: 인스턴트 메시지 초대 또는 부재 중 메시지)를 찾을 수 없습니다.
    
    <div>
    

    > [!NOTE]  
    > Apple 장치에서의 Lync 2013 모바일 클라이언트에는 푸시 알림이 필요 하지 않습니다. Windows Phone의 Lync 2013 모바일 클라이언트는 푸시 알림을 사용 합니다. 푸시 알림 및 푸시 알림 클리어 링 계획은 Lync 2013 모바일 클라이언트를 실행할 수 없는 Windows Phone 및 Apple 장치의 Lync Mobile에 대해서도 동일 하 게 유지 됩니다.

    
    </div>

  - **모든 사용자에 게 모바일 기능에 대 한 액세스를 원하십니까? 아니면 이러한 기능에 대 한 액세스 권한이 있는 사용자를 지정할 수 있도록 하 시겠습니까?**
    
    이 표에서는 Lync Server 2013에서 사용자가 사용할 수 있는 기능에 대해 설명 합니다. 기본값은 직장에서 전화 걸기, VoIP (Voice over IP) 허용 및 모바일 기능을 사용 하도록 설정 하는 것입니다. 사용 가능한 옵션의 전체 집합은 다음과 같습니다.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Feature/Parameter Name/Scope (Policy 매개 변수 이름이 같을 수 없음)</th>
    <th>설명</th>
    <th>도입</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>모바일 기능 사용</p>
    <p>매개 변수 이름:<code>EnableMobility</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>관리 설정 Lync Mobile이 설치 된 지정 된 범위에서 사용자를 제어 하기 위해 정책이 False로 설정 되어 있으면 사용자가 클라이언트에 로그인 할 수 없습니다.</p>
    <p>기본 설정은 True입니다.</p></td>
    <td><p>Lync Server 2010 용 누적 업데이트: 11 월 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>외부 음성 사용</p>
    <p>매개 변수 이름:<code>EnableOutsideVoice</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>사용자가 휴대폰을 통해 전화를 사용 하는 기능을 제어 하는 기능이 지원 되는 기능인 회사 번호를 사용 하 여 전화를 걸고 받을 수 있습니다. False로 설정 하면 사용자가 모바일 장치에서 회사 번호를 사용 하 여 전화를 걸거나 받을 수 없게 됩니다.</p>
    <p>기본 설정은 True입니다.</p></td>
    <td><p>Lync Server 2010 용 누적 업데이트: 11 월 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP 오디오 및 비디오 사용</p>
    <p>매개 변수 이름:<code>EnableIPAudioVideo</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>사용자가 VoIP를 사용 하 여 모바일 장치에서 음성 또는 비디오 통화를 만들거나 수신할 수 있는지 여부를 제어 합니다. False로 설정 하면 사용자가 장치에서 VoIP 또는 비디오 통화를 만들거나 받을 수 없게 됩니다.</p>
    <p>기본 설정은 True입니다.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>IP 오디오에 WiFi 필요</p>
    <p>매개 변수 이름:<code>RequireWiFiForIPAudio</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>이 설정은 클라이언트가 셀룰러 데이터 네트워크가 아닌 WiFi에서 VoIP를 통해 전화를 걸고 받아야 하는지 여부를 정의 합니다. True로 설정 하면 사용자가 WiFi 네트워크에 연결 된 경우에만 VoIP 통화를 설정 하 고 받을 수 있습니다.</p>
    <p>기본 설정은 False입니다.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP 비디오에 WiFi 필요</p>
    <p>매개 변수 이름:<code>RequireWiFiForIPVideo</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>이 설정은 클라이언트가 셀룰러 데이터 네트워크가 아닌 Wi-fi에서 화상 통화를 설정 하 고 수신 해야 하는지 여부를 정의 합니다. True로 설정 된 경우 사용자는 Wi-fi 네트워크에 연결 된 경우에만 비디오 통화를 설정 하 고 수신할 수 있습니다.</p>
    <p>기본 설정은 False입니다.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    구성할 수 있는 정책 설정에 대 한 설명과 정책을 관리 하는 방법에 대 한 자세한 내용은 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) 및 [Remove-get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)를 참조 하십시오.

  - **Enterprise Voice를 사용할 수 있도록 설정되지 않은 사용자가 클릭하여 참가를 사용하여 회의에 참가하도록 할지 여부**
    
    모바일 기능 및 회사번호로 전화 기능에 액세스할 수 있는 사용자는 Enterprise Voice를 사용할 수 있도록 설정해야 합니다. 그러나 Enterprise Voice를 사용 하도록 설정 되지 않은 사용자는 해당 모바일 장치에 대 한 적절 한 음성 정책이 할당 되어 있는 경우 해당 링크를 클릭 하 여 회의에 참가할 수 있습니다. 이러한 사용자에 게 특정 음성 정책을 할당 하거나 해당 정책에 적용 되는 글로벌 정책 또는 사이트 수준 정책이 있는지 확인할 수 있습니다. 지정 하는 음성 정책에는 사용자가 회의에 참가 하기 위해 전화를 걸 수 있는 영역을 정의 하는 PSTN (공중 전화망) 사용 레코드 및 경로가 있어야 합니다. 음성 정책, PSTN 사용 레코드 및 경로를 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 음성 정책, pstn 사용 레코드 및 음성 경로 구성을](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > 모바일 장치에서 링크를 클릭 하면 Lync Server 2013에서 아웃 바운드 호출을 수행 하므로 클릭 하 여 참가 하려는 모바일 사용자에 게는 관련 PSTN 사용 레코드 및 음성 경로와 함께 음성 정책이 필요 합니다.

    
    </div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항](lync-server-2013-technical-requirements-for-mobility.md)  


[Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

