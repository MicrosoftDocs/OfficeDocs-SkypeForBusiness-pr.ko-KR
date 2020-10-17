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
ms.openlocfilehash: 5b704dc3db81c78e187a08ec9ab420f1676f049d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501735"
---
# <a name="create-an-announcement-in-lync-server-2013"></a>Lync Server 2013에서 알림 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

새 알림을 만들려면 다음 단계를 수행해야 합니다.

1.  오디오 음성 안내의 경우 자주 사용하는 오디오 녹음 응용 프로그램을 사용하여 오디오 파일을 녹음합니다.

2.  오디오 음성 안내의 경우 **Import-CsAnnouncementFile** cmdlet을 실행하여 오디오 파일의 내용을 파일 저장소로 가져옵니다.

3.  **New-CsAnnouncement** cmdlet을 실행하여 알림을 만들고 알림의 이름을 지정합니다. 오디오 음성 안내나 TTS(텍스트 음성 변환) 음성 안내를 사용하거나 또는 음성 안내를 사용하지 않고 알림을 만들려면 이 단계를 수행합니다.
    
    <div>
    

    > [!TIP]  
    > 음성 안내를 사용하지 않고 알림을 만들어야 하는 경우도 있습니다(예를 들어 메시지를 재생하지 않고 특정 대상에게 통화를 전송할 경우).

    
    </div>

4.  새 알림을 할당되지 않은 번호 테이블의 번호 범위에 할당합니다.

이 항목에서는 알림을 가져오고 만드는 방법에 대해 설명합니다. 지정 되지 않은 번호 테이블에 공지를 할당 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 지정 되지 않은 번호 테이블 구성을](lync-server-2013-configure-the-unassigned-number-table.md)참조 하십시오.

<div>

## <a name="to-create-a-new-announcement"></a>새 알림을 만들려면

1.  오디오 음성 안내의 경우 오디오 파일을 만듭니다.

2.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

3.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

4.  오디오 음성 안내의 경우 다음을 실행합니다.
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  을 실행합니다.
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    통화를 음성 메일로 전송하려면 SIPAddress를 sip:username@domainname;opaque=app:voicemail 형식으로 입력합니다(예: sip:bob@contoso.com;opaque=app:voicemail). 통화를 전화 번호로 전송할 경우에는 SIPAddress를 sip:number@domainname;user=phone 형식으로 입력합니다(예: sip:+ 14255550121@contoso.com;user=phone).
    
    예: 오디오 음성 안내 지정
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    예: TTS 음성 안내 지정
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    이러한 cmdlet에 대 한 자세한 내용을 보고, **TextToSpeechPrompt** 매개 변수에 사용할 언어 코드의 목록을 보려면 [New csannouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)를 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[경우 import-csannouncementfile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[새 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Lync Server 2013에서 지정 되지 않은 번호 테이블 구성](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

