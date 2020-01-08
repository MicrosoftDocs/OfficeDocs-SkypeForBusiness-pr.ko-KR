---
title: 'Lync Server 2013: (선택 사항) 사용자에게 전화 접속 회의 시작 메시지 보내기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3defde18a01ed09ac529ba9b289749f28c4cdd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>(선택 사항) Lync Server 2013에서 사용자에게 전화 접속 회의 시작 메시지 보내기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-30_

전화 접속 회의를 구성 하 고 제대로 작동 하는지 테스트 한 후에는 사용자에 대 한 초기 개인 id 번호 (Pin)를 설정 하 고 사용자에 게 해당 기능의 사용 가능성에 대해 알려 주십시오 (해당 하는 설명 지침 포함). 초기 PIN 및 전화 접속 회의 설정 웹 페이지에 대 한 링크 이 단계는 선택 사항입니다. 일반적으로 핀을 다시 설정 하는 데는 **CsClientPin** cmdlet을 사용 하지만,이 항목의 절차는 정보를 사용 하 여 환영 전자 메일을 보낼 때 처음으로 사용할 수 있습니다. 전자 메일을 보내지 않으려면 대신 **Set CsClientPin** 을 사용할 수 있습니다.

**CsPinSendCAWelcomeMail** 스크립트를 사용 하 여 PIN을 설정 하 고 한 명의 사용자에 게 환영 전자 메일을 보낼 수 있습니다. 기본적으로 스크립트는 이미 설정 된 경우 PIN을 재설정 하지 않지만 **force** 매개 변수를 사용 하 여 pin을 강제로 재설정할 수 있습니다. SMTP (Simple Mail Transfer Protocol)를 사용 하 여 전자 메일 메시지가 전송 됩니다.

핀을 설정 하 고 사용자 그룹에 전자 메일을 보내기 위해 **set-CsPinSendCAWelcomeMail** 스크립트를 반복적으로 실행 하는 스크립트를 만들 수 있습니다. 전자 메일 템플릿 (즉, **CAWelcomeEmailTemplate** 파일)을 수정 하 여 인트라넷 페이지에 대 한 링크를 추가 하거나 전자 메일 텍스트를 수정할 수 있습니다.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>초기 PIN을 설정 하 고 환영 전자 메일을 보내려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령 프롬프트에서 다음을 실행 합니다.
    
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
    
    **SmtpServer**   이 스크립트는 기본적으로이 매개 변수에 **$PSEmailServer** reserved 환경 변수 값을 사용 합니다. **$PSEmailServer** 변수를 설정 하지 않은 경우에는이 매개 변수를 지정 해야 합니다.
    
    **자격 증명**   기본적으로 스크립트는 현재 사용자의 자격 증명을 사용 합니다. 현재 사용자에 게 지정 된 보낸 사람 주소 대신 전자 메일을 보낼 수 있는 권한이 없는 경우이 매개 변수를 지정 해야 합니다. 일반적인 규칙으로, 전자 메일 주소를 보낸 사람 주소로 지정 하지 않으면이 매개 변수를 지정 합니다.
    
    예를 들면 다음과 같습니다.
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    이 예제에서는 새 PIN을 만든 다음 매크로에서 Bob에 게 환영 전자 메일을 보냅니다. 기본 서식 파일의 전자 메일 텍스트를 사용 하 고 HTML 형식으로 전자 메일 메시지를 만듭니다. 기본 제목은 "전화 접속 회의 시작"입니다.
    
    다른 예:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    이 예제에서는 bob에 게 기존 PIN이 있는 경우에도 "383042650" 값이 포함 된 새 PIN을 강제 적용 하 고 매크로에서 Bob에 게 환영 전자 메일을 보냅니다. Credential 매개 변수를 지정 했기 때문에 명령을 실행 하는 사용자에 게 암호를 입력 하 라는 메시지가 표시 됩니다. SSL (Secure Sockets layer)을 사용 하 여 전자 메일을 보냅니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

