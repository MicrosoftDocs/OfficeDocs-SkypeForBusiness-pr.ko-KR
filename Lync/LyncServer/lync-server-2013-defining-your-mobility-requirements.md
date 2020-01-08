---
title: 'Lync Server 2013: 모바일 기능 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604812d96f58a53ee008bfe42603243571138d1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Lync Server 2013에 대한 모바일 기능 요구 사항 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 mobility 기능에 대 한 계획 단계 중에 Lync 2010 모바일 및 Lync 2013 모바일 클라이언트를 사용 하는 경우 배포 단계를 결정 하는 의사 결정을 내릴 수 있습니다.

고려해 야 할 결정 사항은 다음과 같습니다.

  - **Lync 모바일 클라이언트에 대 한 자동 검색을 사용 하 고 싶으세요?**
    
    자동 검색을 지원 하려면 새 내부 및 외부 DNS (Domain Name System) 레코드를 만들고 프런트 엔드 서버, 디렉터 및 역방향 프록시의 인증서에 주체 대체 이름을 추가 하 고 기존 게시 규칙을 수정 해야 합니다. 리버스 프록시에서. 자세한 내용은 [Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)참조 하세요. 자동 검색을 사용 하면 모바일 장치 설정에 Url을 입력 하지 않고 사용자가 회사 네트워크 내부나 외부의 어디에서 나 자동으로 Lync Server 2013 웹 서비스를 찾을 수 있습니다.
    
    자동 검색 대신 수동 설정을 사용 하는 경우 모바일 사용자는 모바일 장치에 수동으로 다음 Url을 입력 해야 합니다.
    
      - 외부\<액세스를 위한\>Https://extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root
    
      - https://\<intpoolfqdn\>/AutoDiscover/autodiscoverservice/Root 내부 액세스
    
    자동 검색을 사용 하는 것이 좋습니다. 수동 설정은 주로 문제 해결을 위해 사용 됩니다.

  - **자동 검색을 지원 하기로 결정 한 경우, 각 SIP 도메인에 대 한 주체 대체 이름을 사용 하 여 역방향 프록시에서 인증서를 업데이트 하려고 하나요?**
    
    많은 SIP 도메인이 있는 경우 역방향 프록시에서 공용 인증서를 업데이트 하는 데 비용이 매우 많이 들 수 있습니다. 이러한 경우에는 포트 443에서 HTTPS를 사용 하는 대신 포트 80에서 HTTP를 사용 하 여 초기 자동 검색 서비스 요청에 대 한 자동 검색이 구현 되도록 선택할 수 있습니다. 그러나이 방법은 권장 되지 않습니다. 이 대안을 선택 하기로 결정 한 경우에는 리버스 프록시에서 인증서를 업데이트 하지 않아도 되지만, 포트 80에서 HTTP에 대 한 웹 게시 규칙을 만들어야 합니다. 자세한 내용은 [Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md)참조 하세요.

  - **회사 네트워크 내부 및 외부 모두에서 Lync 모바일 클라이언트를 지원 하거나 회사 네트워크 내 에서만 클라이언트를 지원 하 고 싶으신가요?**
    
    네트워크 내부 및 외부 모바일 클라이언트를 지원 하려는 경우 모바일 장치는 모든 위치에서 이동성 기능에 액세스할 수 있습니다. 기본 구성은 회사 네트워크 내부와 외부 모두에 대해 클라이언트를 지원 하는 것입니다.
    
    기본 구성을 통해 모바일 클라이언트 트래픽이 외부 사이트를 통과할 수 있지만, 모바일 클라이언트 소통량을 내부 회사 네트워크로 제한할 수 있습니다. 내부 네트워크에 대 한 트래픽을 제한 하면 사용자는 네트워크 내에 있는 경우에만 모바일 장치에서 Lync 모바일 응용 프로그램을 사용할 수 있습니다.
    
    Mcx mobility service 및 Lync 2010 Mobile을 사용 하 여 이동성을 지 원하는 배포의 경우, **Set-CsMcxConfiguration** cmdlet을 실행 합니다. 내부용 으로만 이동성을 설정 하려면 다음과 같은 명령을 사용 하면 됩니다.
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > 지 수에는 추가 구성이 필요 하지 않습니다. 일부는 해당 하는 내부 전용 구성이 아닙니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server&nbsp;2013 프런트 엔드 서버 또는 프런트 엔드 풀을 사용 중 <STRONG>이 고 lync</STRONG> Server 2010&nbsp;프런트 엔드 서버 또는 프런트 엔드 풀이 없는 경우 <STRONG>쿠키 기반 지 속성에 대 한 요구 사항이 없습니다</STRONG>. Lync Server 2010&nbsp;프런트 엔드 서버 또는 프런트 엔드 풀을 유지 해야 하는 경우에도 쿠키 기반 지 속성을 위해 lync server 2010에서 동일한 규칙이 적용 됩니다.

    
    </div>

  - **Apple iOS 장치 및 Windows phone에 대 한 푸시 알림을 지원 하 시겠습니까?**
    
    푸시 알림을 지원 하면 지원 되는 Apple iOS 장치 및 Windows phone에서 모바일 응용 프로그램이 비활성 상태일 때 발생 하는 이벤트에 대 한 알림을 받습니다. Edge 서버에서 Lync Online 데이터 센터에 있는 클라우드 기반 Lync Server 푸시 알림 서비스와 페더레이션 관계를 설정 하 고 cmdlet을 실행 하 여 푸시 알림을 사용 하도록 구성 해야 합니다.
    
    Wi-fi 네트워크를 통해 푸시 알림을 지원 하려는 경우 모바일 장치 공급자의 3G 또는 데이터 네트워크에서 푸시 알림을 지 원하는 것 외에도 엔터프라이즈 Wi-fi 네트워크에서 포트 5223 아웃 바운드를 열어야 합니다. Wi-fi 네트워크를 통해 푸시 알림을 지원 하면 실내 수신이 불량 한 Wi-fi 및 모바일 장치만 사용 하는 모바일 장치를 지원 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 포트 열기 TCP 5223는 Lync 2010 모바일 클라이언트를 실행 하는 Apple 장치를 지 원하는 경우에만 필요 합니다.

    
    </div>
    
    푸시 알림을 지원 하지 않는 경우 Apple 모바일 장치 및 Windows phone의 사용자는 모바일 응용 프로그램이 비활성 상태일 때 발생 하는 이벤트 (예: 인스턴트 메시지 초대 또는 부재 중 메시지)를 찾을 수 없습니다.
    
    <div>
    

    > [!NOTE]  
    > Apple 디바이스의 Lync 2013 모바일 클라이언트에는 푸시 알림이 필요 하지 않습니다. Windows Phone의 Lync 2013 모바일 클라이언트는 푸시 알림을 사용 합니다. 푸시 알림 및 푸시 알림 clearinghouse에 대 한 계획은 Lync 2013 모바일 클라이언트를 실행할 수 없는 Windows Phone 및 Apple 장치에서 Lync Mobile에 대해 동일 하 게 유지 됩니다.

    
    </div>

  - **모든 사용자에 게 모바일 기능에 대 한 액세스 권한을 부여 하거나 이러한 기능에 액세스할 수 있는 사용자를 지정 하 시겠습니까?**
    
    이 표에서는 Lync Server 2013에서 사용자가 사용할 수 있는 기능에 대해 설명 합니다. 기본적으로 작업을 통한 통화, VoIP (Voice over IP) 허용, 이동성 사용을 설정할 수 있습니다. 사용할 수 있는 옵션의 전체 집합은 다음과 같습니다.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>기능/매개 변수 이름/범위 (정책 매개 변수 이름이 같을 수 없음)</th>
    <th>설명</th>
    <th>새로</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>이동성 사용</p>
    <p>매개 변수 이름:<code>EnableMobility</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>관리 설정 Lync Mobile이 설치 되어 있는 지정 된 범위에서 사용자를 제어 하기 위해 정책이 False로 설정 되어 있으면 사용자가 클라이언트에 로그인 할 수 없습니다.</p>
    <p>기본 설정은 True입니다.</p></td>
    <td><p>Lync Server의 누적 업데이트 2010:11 월 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>외부 음성 사용</p>
    <p>매개 변수 이름:<code>EnableOutsideVoice</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>사용자가 휴대폰 번호 대신 회사 번호를 사용 하 여 전화를 걸고 받을 수 있는 기능인 작업을 통해 전화를 사용 하는 사용자의 기능을 제어 합니다. False로 설정 되 면 사용자는 해당 모바일 장치에서 회사 번호를 사용 하 여 전화를 걸거나 받을 수 없게 됩니다.</p>
    <p>기본 설정은 True입니다.</p></td>
    <td><p>Lync Server의 누적 업데이트 2010:11 월 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP 오디오 및 비디오 사용</p>
    <p>매개 변수 이름:<code>EnableIPAudioVideo</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>사용자가 VoIP를 사용 하 여 모바일 장치에서 음성 또는 영상 통화를 하거나 수신할 수 있는지 여부를 제어 합니다. False로 설정 되 면 사용자는 자신의 장치에서 VoIP 또는 영상 통화를 하거나 받을 수 없게 됩니다.</p>
    <p>기본 설정은 True입니다.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>IP 오디오에 WiFi 필요</p>
    <p>매개 변수 이름:<code>RequireWiFiForIPAudio</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>이 설정은 클라이언트가 셀룰러 데이터 네트워크 대신 WiFi에서 VoIP를 통해 전화를 걸고 받으려고 하는 데 필요한 지 여부를 정의 합니다. True로 설정 되 면 사용자는 WiFi 네트워크에 연결 된 경우에만 VoIP 통화를 설정 하 고 받을 수 있습니다.</p>
    <p>기본 설정은 False입니다.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP 비디오에 WiFi 필요</p>
    <p>매개 변수 이름:<code>RequireWiFiForIPVideo</code></p>
    <p>범위: 전역/사이트/사용자</p></td>
    <td><p>이 설정은 클라이언트가 셀룰러 데이터 네트워크 대신 Wi-fi에서 영상 통화를 설정 하 고 받도록 해야 하는지 여부를 정의 합니다. True로 설정 되 면 사용자는 Wi-fi 네트워크에 연결 된 경우에만 영상 통화를 하 고 받을 수 있습니다.</p>
    <p>기본 설정은 False입니다.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    구성할 수 있는 정책 설정에 대 한 설명과 정책을 관리 하는 방법에 대 한 자세한 내용은 [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) 및 [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)을 참조 하세요.

  - **Enterprise Voice를 사용 하도록 설정 하지 않은 사용자가 클릭 하 여 회의 참가에 참가할 수 있도록 하 고 싶으신가요?**
    
    사용자가 모바일 기능에 액세스 하 고 작업을 통해 전화를 걸려면 Enterprise Voice를 사용 하도록 설정 해야 합니다. 그러나 Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 적절 한 음성 정책이 지정 되어 있는 경우 모바일 장치에서 해당 링크를 클릭 하 여 회의에 참가할 수 있습니다. 이러한 사용자에 게 특정 음성 정책을 할당 하거나 해당 정책에 적용 되는 전역 정책 또는 사이트 수준 정책이 있는지 확인할 수 있습니다. 지정 하는 음성 정책에는 사용자가 전화를 걸어 회의에 참가할 수 있는 영역을 정의 하는 공개 통신망 (교환 전화망) 사용 레코드 및 경로가 있어야 합니다. 음성 정책, PSTN 사용 레코드, 경로를 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 음성 정책, pstn 사용 레코드 및 음성 경로 구성을](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > 클릭 하 여 참가 하려는 모바일 사용자는 모바일 장치에서 링크를 클릭 하면 Lync Server 2013에서 나가는 호출을 하 게 되므로 관련 PSTN 사용 레코드 및 음성 경로와 함께 음성 정책이 필요 합니다.

    
    </div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 모바일 기능에 대한 기술 요구 사항](lync-server-2013-technical-requirements-for-mobility.md)  


[Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

