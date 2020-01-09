---
title: 비즈니스용 Skype 서버에서 전화 접속 사용자에 게 환영 전자 메일 보내기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: '요약: 비즈니스용 Skype 서버에서 사용자가 전화 접속 회의를 시작 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: d9f0740128a8790052534e63c95a8305f65bb96d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992835"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 접속 사용자에 게 환영 전자 메일 보내기
 
**요약:** 비즈니스용 Skype 서버에서 사용자가 전화 접속 회의를 시작 하는 방법에 대해 알아봅니다.
  
전화 접속 회의를 구성 하 고 제대로 작동 하는지 테스트 한 후에는 사용자에 대 한 초기 개인 id 번호 (Pin)를 설정 하 고 사용자에 게 기능의 사용 가능성에 대해 알려 주어 야 합니다. 초기 PIN 및 전화 접속 회의 설정 웹 페이지에 대 한 링크와 같은 안내 지침을 포함할 수 있습니다. 
  
일반적으로 핀을 다시 설정 하는 데는 **CsClientPin** cmdlet을 사용 하지만 pin 정보를 사용 하 여 소개 시작 전자 메일을 보내려는 경우이 항목의 절차를 사용할 수 있습니다. 전자 메일을 보내지 않으려면 대신 **Set CsClientPin** 을 사용할 수 있습니다.
  
**CsPinSendCAWelcomeMail** 스크립트를 사용 하 여 PIN을 설정 하 고 한 명의 사용자에 게 환영 전자 메일을 보낼 수 있습니다. 기본적으로 스크립트는 이미 설정 된 경우 PIN을 재설정 하지 않지만 Force 매개 변수를 사용 하 여 PIN을 강제로 재설정할 수 있습니다. SMTP (Simple Mail Transfer Protocol)를 사용 하 여 전자 메일 메시지가 전송 됩니다.
  
핀을 설정 하 고 사용자 그룹에 전자 메일을 보내기 위해 **set-CsPinSendCAWelcomeMail** 스크립트를 반복적으로 실행 하는 스크립트를 만들 수 있습니다. 전자 메일 템플릿 (즉, CAWelcomeEmailTemplate 파일)을 수정 하 여 인트라넷 페이지에 대 한 링크를 추가 하거나 전자 메일 텍스트를 수정할 수 있습니다.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>초기 PIN 설정 및 환영 전자 메일 보내기

1. RTCUniversalServerAdmins 그룹의 구성원으로 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 명령 프롬프트에서 다음을 실행 합니다.
    
   ```PowerShell
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

**SmtpServer** 기본적으로 스크립트는이 매개 변수에 대해 **$PSEmailServer** 예약 된 환경 변수 값을 사용 합니다. **$PSEmailServer** 변수를 설정 하지 않은 경우에는이 매개 변수를 지정 해야 합니다.
    
**자격 증명** 기본적으로 스크립트는 현재 사용자의 자격 증명을 사용 합니다. 현재 사용자에 게 지정 된 보낸 사람 주소 대신 전자 메일을 보낼 수 있는 권한이 없는 경우이 매개 변수를 지정 해야 합니다. 일반적인 규칙으로, 전자 메일 주소를 보낸 사람 주소로 지정 하지 않으면이 매개 변수를 지정 합니다.
    
다음 예에서는 새 PIN을 만든 다음 매크로에서 Bob에 게 환영 전자 메일을 보냅니다. 기본 서식 파일의 전자 메일 텍스트를 사용 하 고 HTML 형식으로 전자 메일 메시지를 만듭니다. 기본 제목은 "전화 접속 회의 시작"입니다.
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

다음 예에서는 bob에 게 기존 PIN이 있는 경우에도 "383042650" 값이 포함 된 새 PIN을 강제 적용 하 고 매크로에서 Bob에 게 환영 전자 메일을 보냅니다. Credential 매개 변수를 지정 했기 때문에 명령을 실행 하는 사용자에 게 암호를 입력 하 라는 메시지가 표시 됩니다. SSL (Secure Sockets layer)을 사용 하 여 전자 메일을 보냅니다.
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
