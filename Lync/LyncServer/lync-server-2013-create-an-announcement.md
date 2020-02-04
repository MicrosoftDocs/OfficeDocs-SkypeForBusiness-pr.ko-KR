---
title: 'Lync Server 2013: 알림 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfae1817cb47c769885ca42a7ca3ff6f57f7b669
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a>Lync Server 2013에서 알림 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

새 알림을 만들려면 다음 단계를 수행 해야 합니다.

1.  오디오 메시지가 표시 되는 경우 좋아하는 오디오 녹음 응용 프로그램을 사용 하 여 오디오 파일을 녹음 합니다.

2.  오디오 프롬프트의 경우 **CsAnnouncementFile** cmdlet을 실행 하 여 오디오 파일의 콘텐츠를 파일 저장소로 가져옵니다.

3.  **새 csannouncement** cmdlet을 실행 하 여 알림을 만들고 이름을 만듭니다. 오디오 프롬프트, 텍스트 음성 변환 (TTS) 프롬프트 또는 메시지가 표시 되지 않는 알림을 만들려면이 단계를 수행 합니다.
    
    <div>
    

    > [!TIP]  
    > 메시지를 재생 하지 않고 특정 대상에 전화를 거는 등의 메시지가 표시 되지 않은 상태에서 알림을 만들어야 할 수 있습니다.

    
    </div>

4.  지정 하지 않은 번호 표의 번호 범위에 새 공지 사항을 할당 합니다.

이 항목에서는 알림을 가져오고 만드는 방법에 대해 설명 합니다. 할당 되지 않은 번호 표에 공지 사항을 할당 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 지정 하지 않은 번호 표 구성을](lync-server-2013-configure-the-unassigned-number-table.md)참조 하세요.

<div>

## <a name="to-create-a-new-announcement"></a>새 알림을 만들려면

1.  오디오 메시지가 표시 되는 경우 오디오 파일을 만듭니다.

2.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

3.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

4.  오디오 프롬프트에 대해 다음을 실행 합니다.
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  런
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    음성 메일로 통화를 전송 하는 경우 sip: username@domainname, 불투명 = 앱: 음성 메일 (예: sip: bob@contoso, 불투명 = app) 형식으로 SIPAddress를 입력 합니다. 전화 번호로 통화를 전송 하는 경우 sip: number@domainname, user = phone 형식으로 SIPAddress를 입력 합니다 (예: sip: + 14255550121@contoso 사용자 = 휴대폰).
    
    예를 들어 오디오 프롬프트를 지정 하려면 다음을 실행 합니다.
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    예를 들어 TTS 프롬프트를 지정 하려면 다음을 실행 합니다.
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    이러한 cmdlet에 대 한 자세한 내용 및 **TextToSpeechPrompt** 매개 변수에 사용할 언어 코드 목록을 보려면 [새 csannouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[가져오기-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[새 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Lync Server 2013에서 지정되지 않은 번호 테이블 구성](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

