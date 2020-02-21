---
title: 'Lync Server 2013: 모바일 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2268313ed570ab560be2eca9827f0ab07ec9149
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Lync Server 2013에서 모바일 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013에서는 모바일 기능을 사용할 수 있는 사람, 직장, VoIP (voice over IP) 또는 비디오를 통해 전화를 거는 방법 및 VoIP 또는 비디오에 대해 WiFi가 필요한 지를 결정 하는 모바일 정책을 제공 합니다. 업무를 통한 통화 기능을 사용 하면 모바일 사용자가 휴대폰 번호 대신 회사 전화 번호를 사용 하 여 휴대폰에서 전화를 걸고 받을 수 있습니다. 이 기능은 전화 건 사람이 발신자의 휴대폰 번호를 확인 하 여 아웃 바운드 통화 요금을 피할 수 있도록 합니다. VoIP 및 동영상을 구성 하면 사용자가 VoIP 통화 및 비디오를 수신 하 고 제공할 수 있습니다. WiFi 사용 설정 사용자의 장치에서 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용 해야 하는 경우를 정의 합니다.

기본적으로는 mobility, Work를 통한 통화 및 VoIP 및 비디오 기능을 사용할 수 있습니다. VoIp 및 비디오용으로 WiFi를 요구 하는 설정을 사용 하지 않도록 설정 합니다. 관리자는 cmdlet을 실행하여 이러한 기능에 액세스할 수 있는 사용자를 결정할 수 있습니다. 옵션을 전역적으로 해제할 수도 있고 사이트나 사용자별로 해제할 수도 있습니다.

모바일 기능과 회사번호로 전화 기능을 사용하려면 사용자는 다음 필수 구성 요소를 충족해야 합니다.

  - Lync Server 2013에 대해 사용자를 사용 하도록 설정 해야 합니다.

  - 사용자가 Enterprise Voice를 사용할 수 있도록 설정되어야 합니다.

  - **EnableMobility** 옵션이 True로 설정된 모바일 정책이 사용자에게 지정되어 있어야 합니다.

회사번호로 전화 기능을 사용하려는 사용자는 다음의 두 선행 조건을 추가로 충족해야 합니다.

  - **동시 전화 신호 울림 사용** 옵션이 선택된 음성 정책이 사용자에게 지정되어 있어야 합니다.

  - **EnableOutsideVoice** 옵션이 True로 설정된 모바일 정책이 사용자에게 지정되어 있어야 합니다.

<div>


> [!NOTE]  
> Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 모바일 장치를 사용 하 여 Lync for Lync (Voice over IP) 통화를 수행 하거나, 해당 사용자에 게 음성 정책에 대 한 적절 한 옵션을 할당 하는 경우 모바일 장치에서 링크를 클릭 하 여 연결을 통해 회의에 참가할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013에 대 한 모바일 기능 요구 사항 정의</A>를 참조 하십시오.



</div>

Lync Server 2013에 대해 사용자를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Disable or enable user account For Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)을 참조 하십시오. Enterprise Voice를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 사용자에 게 Enterprise Voice 사용을 허용](lync-server-2013-enable-users-for-enterprise-voice.md)을 참조 하세요. 음성 정책 옵션을 설정 하는 방법에 대 한 자세한 내용은 [Modify a voice policy 및 CONFIGURE PSTN usage records In Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)을 참조 하십시오.

<div>

## <a name="to-modify-global-mobility-policy"></a>전역 모바일 정책을 수정하려면

1.  Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에 다음을 입력하여 모바일 기능 및 회사번호로 전화 기능에 대한 액세스를 전역적으로 해제합니다.
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > 모바일 기능 액세스는 해제하지 않고 회사번호로 전화 기능만 해제할 수는 있지만, 회사번호로 전화 기능은 해제하지 않고 모바일 기능만 해제할 수는 없습니다.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>사이트별로 모바일 정책을 수정하려면

1.  Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  사이트 수준 정책을 만들고 VoIP 및 비디오를 끈 다음 사이트 별로 ip 오디오 및 IP 비디오용으로 WiFi를 사용 하도록 설정 합니다. 명령줄에 다음을 입력합니다.
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>사용자별로 모바일 정책을 수정하려면

1.  Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에 다음을 입력하여 사용자 수준 모바일 정책을 만들고 모바일 기능 및 회사번호로 전화 기능을 사용자별로 해제합니다.
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    모바일 기능 액세스는 해제하지 않고 회사번호로 전화 기능만 해제할 수는 있지만, 회사번호로 전화 기능은 해제하지 않고 모바일 기능만 해제할 수는 없습니다.
    
    예를 들면 다음과 같습니다.
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Lync Server 2013에 대 한 모바일 기능 요구 사항 정의](lync-server-2013-defining-your-mobility-requirements.md)  


[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Get-csmobilitypolicy을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

