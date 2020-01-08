---
title: 'Lync Server 2013: 모바일 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Lync Server 2013에서 모바일 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013는 모바일 기능을 사용할 수 있는 사용자, 작업 시간, VoIP (voice over IP), 비디오, VoIP 또는 비디오에 WiFi가 필요한 지 여부를 결정 하는 이동성 정책을 제공 합니다. 휴대 전화를 통한 통화 기능을 사용 하면 모바일 사용자가 휴대폰 번호 대신 회사 전화 번호를 사용 하 여 휴대폰에서 전화를 걸고 받을 수 있습니다. 이 기능은 상대방이 발신자의 휴대 전화 번호를 보지 못하게 하 고 사용자가 아웃 바운드 통화 요금을 피할 수 있도록 합니다. VoIP 및 비디오를 구성 하면 사용자가 VoIP 통화와 동영상을 주고 받을 수 있습니다. WiFi 사용량에 대 한 설정 사용자의 장치가 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용 해야 하는 경우에 정의 합니다.

기본적으로, 이동성, 업무용 통화, VoIP 및 비디오 기능을 사용할 수 있습니다. VoIp 및 비디오용으로 WiFi를 필요로 하는 설정을 사용할 수 없습니다. 관리자는 cmdlet을 실행 하 여 이러한 기능에 대 한 액세스 권한이 있는 사용자를 결정할 수 있습니다. 전역, 사이트 또는 사용자별로 옵션을 해제할 수 있습니다.

이동성 기능을 사용 하 고 작업을 통해 통화할 수 있으려면 사용자가 다음 필수 조건을 충족 해야 합니다.

  - 사용자는 Lync Server 2013을 사용할 수 있어야 합니다.

  - 사용자는 엔터프라이즈 음성을 사용할 수 있어야 합니다.

  - **EnableMobility** 옵션이 True로 설정 된 이동성 정책은 사용자에 게 할당 해야 합니다.

사용자가 작업을 통해 통화를 사용할 수 있으려면 다음 두 가지 추가 필수 조건을 충족 해야 합니다.

  - 사용자에 게는 **전화의 동시 신호음 사용** 옵션이 선택 되어 있는 음성 정책이 할당 되어야 합니다.

  - **EnableOutsideVoice** 옵션이 True로 설정 된 이동성 정책은 사용자에 게 할당 해야 합니다.

<div>


> [!NOTE]  
> Enterprise Voice를 사용 하도록 설정 되지 않은 사용자는 모바일 장치를 사용 하 여 Lync에서 lync (Voice over IP) 통화를 만들거나, 해당 사용자에 게 음성 정책에 대 한 적절 한 옵션을 할당 하는 경우 모바일 장치에서 클릭 하 여 참가 링크를 사용 하 여 회의에 참가할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013의 모바일 요구 사항 정의</A>를 참조 하세요.



</div>

Lync Server 2013 사용자를 사용 하는 방법에 대 한 자세한 내용은 [Lync server 2013에 대 한 사용자 계정 비활성화 또는 다시 사용](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)을 참조 하세요. Enterprise Voice 사용자를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 엔터프라이즈 음성 사용자 사용](lync-server-2013-enable-users-for-enterprise-voice.md)을 참조 하세요. 음성 정책 옵션 설정에 대 한 자세한 내용은 [Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성을](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)참조 하세요.

<div>

## <a name="to-modify-global-mobility-policy"></a>전역 이동성 정책 수정

1.  Lync Server Management Shell 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  전역으로 업무에 대 한 액세스를 해제 하 고 전화를 통해 통화를 사용 합니다. 명령줄에 다음을 입력 합니다.
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Mobility에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 끌 수 있습니다. 그러나 작업을 통해 통화를 끄지 않고 이동성을 해제할 수는 없습니다.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>사이트별 모바일 정책 수정

1.  Lync Server Management Shell 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  사이트 수준 정책을 만들고 VoIP 및 비디오를 해제 하 고 사이트 별로 ip 오디오 및 IP 비디오용으로 WiFi를 사용 하도록 설정 합니다. 명령줄에 다음을 입력 합니다.
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>사용자의 모바일 정책 수정

1.  Lync Server Management Shell 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  사용자 수준 이동성 정책을 만들고, 이동성을 사용 하지 않도록 설정 하 고, 사용자의 작업을 통해 전화를 겁니다. 명령줄에 다음을 입력 합니다.
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Mobility에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 끌 수 있습니다. 그러나 작업을 통해 통화를 끄지 않고 이동성을 해제할 수는 없습니다.
    
    예를 들면 다음과 같습니다.
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 활성화](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Lync Server 2013에 대한 모바일 기능 요구 사항 정의](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[부여-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

