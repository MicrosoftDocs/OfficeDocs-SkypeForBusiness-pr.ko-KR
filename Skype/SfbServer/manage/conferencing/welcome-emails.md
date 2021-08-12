---
title: 사용자의 전화 접속 사용자에게 환영 전자 메일을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: '요약: 사용자의 전화 접속 회의를 시작하게 하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 1b585d4e0ff05bdb1faca0aa9c8b0863dd26f10f7d06bb1140211a2f1663e6b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313196"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>사용자의 전화 접속 사용자에게 환영 전자 메일을 비즈니스용 Skype 서버
 
**요약:** 사용자의 전화 접속 회의 시작을 환영하는 방법을 비즈니스용 Skype 서버.
  
전화 접속 회의를 구성하고 테스트하여 제대로 작동하고 있는지 확인한 후 사용자에 대해 초기 개인식별번호(PINS)를 설정하고 기능의 가용성을 사용자에게 알려야 합니다. 초기 PIN과 같은 소개 지침과 전화 접속 회의 웹 페이지에 대한 설정 있습니다. 
  
일반적으로 **Set-CsClientPin** cmdlet을 사용하여 PIN을 다시 설정하지만 PIN 정보가 있는 소개 환영 전자 메일을 보내고 싶은 경우 이 항목의 절차를 사용할 수 있습니다. 전자 메일을 보내지 않을 경우 **Set-CsClientPin을** 대신 사용할 수 있습니다.
  
**Set-CsPinSendCAWelcomeMail** 스크립트를 사용하여 PIN을 설정하고 단일 사용자에게 환영 전자 메일을 보낼 수 있습니다. 기본적으로 스크립트는 이미 설정된 경우 PIN을 다시 설정하지 않지만 Force 매개 변수를 사용하여 PIN을 강제로 다시 설정할 수 있습니다. 전자 메일 메시지는 SMTP(Simple Mail Transfer Protocol)를 사용하여 전송됩니다.
  
**Set-CsPinSendCAWelcomeMail** 스크립트를 실행하여 PINS를 설정하고 사용자 그룹에 전자 메일을 보내는 스크립트를 만들 수 있습니다. 전자 메일 템플릿(예: l 파일)을 수정하여 CAWelcomeEmailTemplate.htm링크를 추가하거나 전자 메일 텍스트를 수정할 수 있습니다.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>초기 PIN 설정 및 환영 전자 메일 보내기

1. RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 명령 프롬프트에서 다음을 실행합니다.
    
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

**SmtpServer** 기본적으로 스크립트는 이 매개 변수에 대해  예약된 환경 변수의 $PSEmailServer 사용합니다. $PSEmailServer **변수가** 설정되지 않은 경우 이 매개 변수를 지정해야 합니다.
    
**자격 증명** 기본적으로 스크립트는 현재 사용자의 자격 증명을 사용 합니다. 현재 사용자에게 지정된 보낸 사람 주소를 대신하여 전자 메일을 보낼 수 있는 권한이 없는 경우 이 매개 변수를 지정해야 합니다. 일반적으로 전자 메일 주소를 From 주소로 지정하지 않는 경우 이 매개 변수를 지정합니다.
    
다음 예에서는 새 PIN을 만든 다음 Marco에서 Bob에게 환영 전자 메일을 전송합니다. 기본 템플릿의 전자 메일 텍스트를 사용하여 HTML 형식으로 전자 메일 메시지를 만듭니다. 기본 제목은 "전화 접속 회의 시작"입니다.
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

다음 예제에서는 Bob에 기존 PIN이 있는 경우에도 Bob에 대해 "383042650" 값을 가지는 새 PIN을 강제로 설정한 다음 Marco에서 Bob에게 환영 전자 메일을 전송합니다. Credential 매개 변수가 지정되어 있기 때문에 명령을 실행하는 사용자에게 암호를 입력하라는 메시지가 표시됩니다. 전자 메일은 SSL(Secure Sockets Layer)을 사용하여 전송됩니다.
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
