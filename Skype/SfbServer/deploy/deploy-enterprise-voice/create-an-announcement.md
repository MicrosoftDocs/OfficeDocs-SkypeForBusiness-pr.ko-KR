---
title: 비즈니스용 Skype 서버에서 공지 사항 만들기 또는 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대 한 공지 사항을 만들거나 삭제 합니다. 이는 할당 되지 않은 번호로의 호출이 처리 되는 방식에 영향을 줍니다.
ms.openlocfilehash: b9f745a4b3b5a85548cc52cc1e883159a01ec1df
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233790"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 공지 사항 만들기 또는 삭제

비즈니스용 Skype Server Enterprise Voice에서 알림 신청에 대 한 공지 사항을 만들거나 삭제 합니다. 이는 할당 되지 않은 번호로의 호출이 처리 되는 방식에 영향을 줍니다.

알림을 구성 하는 경우에는 할당 되지 않은 번호로 전화를 처리 하는 방법을 실제로 구성 하는 것입니다. 오디오 파일이 나 텍스트 음성 변환 (TTS) 파일이 될 수 있는 프롬프트를 재생 하거나, 프롬프트를 재생 하지 않고 지정 된 대상으로 통화를 전송할 수 있습니다.

할당 되지 않은 번호 표를 정의 하기 전에 공지 사항을 만들어야 합니다. 오디오 프롬프트, TTS 프롬프트 또는 메시지 표시 안 함을 사용 하는 모든 공지 사항에 대해이 단계를 수행 해야 합니다.

이 항목에서는 알림을 가져오고 만드는 방법에 대해 설명 합니다. 지정 되지 않은 번호 테이블에 공지 사항을 할당 하는 방법에 대 한 자세한 내용은 지정 하지 [않은 번호 표 구성을](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)참조 하세요.

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>할당 되지 않은 번호에 대 한 새 공지 사항 만들기

새 알림을 만들려면 다음 단계를 수행 해야 합니다.

1. 오디오 메시지가 표시 되는 경우 좋아하는 오디오 녹음 응용 프로그램을 사용 하 여 오디오 파일을 녹음 합니다.

2. 오디오 프롬프트의 경우 **CsAnnouncementFile** cmdlet을 실행 하 여 오디오 파일의 콘텐츠를 파일 저장소로 가져옵니다.

3. **새 csannouncement** cmdlet을 실행 하 여 알림을 만들고 이름을 만듭니다. 오디오 프롬프트, 텍스트 음성 변환 (TTS) 프롬프트 또는 메시지가 표시 되지 않는 알림을 만들려면이 단계를 수행 합니다.

    > [!TIP]
    > 메시지를 재생 하지 않고 특정 대상에 전화를 거는 등의 메시지가 표시 되지 않은 상태에서 알림을 만들어야 할 수 있습니다.

4. 지정 하지 않은 번호 표의 번호 범위에 새 공지 사항을 할당 합니다.

### <a name="to-create-a-new-announcement"></a>새 알림을 만들려면

1. 오디오 메시지가 표시 되는 경우 오디오 파일을 만듭니다.

2. 비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

3. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

4. 오디오 프롬프트에 대해 다음을 실행 합니다.

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. 런

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    음성 메일로 통화를 전송 하는 경우 sip: username @ domainname, 불투명 = 앱: 보이스 메일 형식 (예: sip: bob@contoso.com, 불투명 = 앱-음성 메일) 형식의 SIPAddress를 입력 합니다. 전화 번호로 통화를 전송 하는 경우 sip: number @ domainname, user = phone 형식으로 SIPAddress를 입력 합니다 (예를 들어 sip: + 14255550121@contoso.com, user = phone).

    예를 들어 오디오 프롬프트를 지정 하려면 다음을 실행 합니다.

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    예를 들어 TTS 프롬프트를 지정 하려면 다음을 실행 합니다.

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   이러한 cmdlet에 대 한 자세한 내용 및 **TextToSpeechPrompt** 매개 변수에 사용할 언어 코드 목록을 보려면 [새 csannouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)를 참조 하세요.

## <a name="delete-an-announcement-for-unassigned-numbers"></a>할당 되지 않은 번호에 대 한 공지 사항 삭제

### <a name="to-delete-an-announcement"></a>공지 사항을 삭제 하려면

1. 비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

3. 조직의 모든 공지 사항을 나열 합니다. 명령줄에서 다음을 실행 합니다.

   ```
   Get-CsAnnouncement
   ```

4. 결과 목록에서 삭제 하려는 공지 사항을 찾아 GUID를 복사 합니다. 그런 다음 명령줄에서 다음을 실행 합니다.

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    예를 들면 다음과 같습니다.

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > 추가 옵션에 대 한 자세한 내용은 [Csannouncement 가져오기](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) 및 [-csannouncement 제거](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)를 참조 하세요.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 공지 사항 만들기 또는 삭제](create-an-announcement.md)

[가져오기-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[새 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[CsAnnouncement 제거](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[다운로드-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

