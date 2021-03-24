---
title: 비즈니스용 Skype 서버에서 공지 만들기 또는 삭제
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 비즈니스용 Skype 서버 2013에서 공지사항 응용 프로그램에 대한 공지 사항을 만들거나 Enterprise Voice. 이는 미지정 번호에 대한 호출이 처리된 방식에 영향을 미치게 됩니다.
ms.openlocfilehash: 571dce52366430c0e13f442de4917a2c51ed056f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093286"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 공지 만들기 또는 삭제

비즈니스용 Skype 서버 2013에서 공지사항 응용 프로그램에 대한 공지 사항을 만들거나 Enterprise Voice. 이는 미지정 번호에 대한 호출이 처리된 방식에 영향을 미치게 됩니다.

공지 사항을 구성할 때 실제로는 미지정 번호에 대한 통화를 처리할 방법을 구성합니다. 오디오 파일 또는 TTS(텍스트 음성) 파일일 수 있는 프롬프트를 재생하거나 프롬프트를 재생하지 않고 통화를 지정된 대상으로 전송할 수 있습니다.

미지정 번호 테이블을 정의하기 전에 공지 사항을 만들어야 합니다. 오디오 프롬프트, TTS 프롬프트 또는 프롬프트를 사용하지 않는 모든 공지에 대해 이 단계를 수행해야 합니다.

이 항목에서는 알림을 가져오고 만드는 방법에 대해 설명합니다. 할당되지 않은 번호 테이블에서 알림을 할당하는 방법에 대한 자세한 내용은 [Configure the Unassigned Number Table](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table)을 참조하십시오.

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>미지정 번호에 대한 새 공지 만들기

새 알림을 만들려면 다음 단계를 수행해야 합니다.

1. 오디오 음성 안내의 경우 자주 사용하는 오디오 녹음 응용 프로그램을 사용하여 오디오 파일을 녹음합니다.

2. 오디오 음성 안내의 경우 **Import-CsAnnouncementFile** cmdlet을 실행하여 오디오 파일의 내용을 파일 저장소로 가져옵니다.

3. **New-CsAnnouncement** cmdlet을 실행하여 알림을 만들고 알림의 이름을 지정합니다. 오디오 음성 안내나 TTS(텍스트 음성 변환) 음성 안내를 사용하거나 또는 음성 안내를 사용하지 않고 알림을 만들려면 이 단계를 수행합니다.

    > [!TIP]
    > 음성 안내를 사용하지 않고 알림을 만들어야 하는 경우도 있습니다(예를 들어 메시지를 재생하지 않고 특정 대상에게 통화를 전송할 경우).

4. 새 알림을 할당되지 않은 번호 테이블의 번호 범위에 할당합니다.

### <a name="to-create-a-new-announcement"></a>새 알림을 만들려면

1. 오디오 음성 안내의 경우 오디오 파일을 만듭니다.

2. 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 설치 권한 위임에 설명된 필요한 사용자 권한으로 **로그온합니다.**

3. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**

4. 오디오 음성 안내의 경우 다음을 실행합니다.

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. 을 실행합니다.

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    통화를 음성 메일로 전송하려면 SIPAddress를 sip:username@domainname;opaque=app:voicemail 형식으로 입력합니다(예: sip:bob@contoso.com;opaque=app:voicemail). 통화를 전화 번호로 전송할 경우에는 SIPAddress를 sip:number@domainname;user=phone 형식으로 입력합니다(예: sip:+ 14255550121@contoso.com;user=phone).

    예: 오디오 음성 안내 지정

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    예: TTS 음성 안내 지정

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   이러한 cmdlet에 대한 자세한 내용과 **TextToSpeechPrompt** 매개 변수에서 사용할 언어 코드 목록을 확인하면 [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)를 참조하세요.

## <a name="delete-an-announcement-for-unassigned-numbers"></a>미지정 번호에 대한 공지 삭제

### <a name="to-delete-an-announcement"></a>공지 사항을 삭제하려면

1. 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 설치 권한 위임에 설명된 필요한 사용자 권한으로 **로그온합니다.**

2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**

3. 조직의 모든 공지 사항을 나열합니다. 명령줄에서 다음을 실행합니다.

   ```powershell
   Get-CsAnnouncement
   ```

4. 결과 목록에서 삭제할 공지 사항을 찾아 GUID를 복사합니다. 그런 다음 명령줄에서 다음을 실행합니다.

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    예:

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > 추가 옵션에 대한 자세한 내용은 [Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) 및 [Remove-CsAnnouncement를 참조하세요.](/powershell/module/skype/remove-csannouncement?view=skype-ps)

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 공지 만들기 또는 삭제](create-an-announcement.md)

[Import-CsAnnouncementFile](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)