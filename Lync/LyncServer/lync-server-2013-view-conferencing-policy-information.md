---
title: 'Lync Server 2013: 회의 정책 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8dc9174356b1d5f8e5c6316ef761c51db1eb969
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a>Lync Server 2013에서 회의 정책 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

Lync Server 2013 제어판에서는 회의 정책을 사용 하 여 배포에서 회의가 구현 되는 방법을 제어 합니다. 여기에는 다음과 같은 회의 정책이 포함 됩니다.

  - Lync Server 2013을 배포할 때 기본적으로 생성 되는 전역 정책입니다.

  - 특정 사이트 또는 사용자에 대해 회의가 구현 되는 방법을 지정 하는 데 사용할 수 있는 선택적 사이트 수준 및 사용자 수준 정책입니다.

<div>

## <a name="to-view-conferencing-policy-settings"></a>회의 정책 설정을 보려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **회의 정책을**클릭 합니다.

4.  **회의 정책** 페이지에서 보려는 회의 정책을 두 번 클릭 합니다.

5.  **파일 편집 필터**에서 **세부 정보 표시** ...를 선택 합니다. 확인란을 선택 합니다.
    
    **회의 정책 편집- \<정책\> ** 열림 선택한 정책에 대 한 설정을 표시 합니다. 설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 회의 정책 만들기 또는 수정을](lync-server-2013-create-or-modify-a-conferencing-policy.md)참조 하세요.

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 회의 정책 보기

Windows PowerShell 및 CsConferencingPolicy cmdlet을 사용 하 여 회의 정책을 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-conferencing-policies"></a>회의 정책을 보려면

  - 모든 회의 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsConferencingPolicy
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) 을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

