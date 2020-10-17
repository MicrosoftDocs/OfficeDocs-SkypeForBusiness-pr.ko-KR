---
title: 'Lync Server 2013: (선택 사항) 사용자에 게 전화 접속 회의 시작'
description: 'Lync Server 2013: (선택 사항) 사용자에 게 전화 접속 회의를 시작 하는 방법을 환영 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d33c7184a8cf22699b4ebe8d8ea8b4ef1c133a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546904"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>반드시 Lync Server 2013에서 사용자에 게 전화 접속 회의 시작

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-30_

전화 접속 회의를 구성 하 고 테스트 하 여 정상적으로 작동 하는지 확인 한 후에는 사용자에 대 한 초기 개인 식별 번호 (Pin)를 설정 하 고 초기 PIN 및 전화 접속 회의 설정 웹 페이지에 대 한 링크와 같은 소개 지침을 포함 하 여 사용자에 게 기능의 가용성을 알려야 합니다. 이 단계는 선택 사항입니다. 일반적으로는 **CsClientPin** cmdlet을 사용 하 여 pin을 다시 설정 하지만, 정보를 포함 하 여 환영 전자 메일을 처음으로 보낼 때이 항목의 절차를 사용할 수 있습니다. 전자 메일을 보내지 않으려면 대신 **Set CsClientPin** 을 사용할 수 있습니다.

**Set-cspinsendcawelcomemail** 스크립트를 사용 하 여 PIN을 설정 하 고 단일 사용자에 게 환영 전자 메일을 보낼 수 있습니다. 기본적으로 스크립트는 이미 설정 된 경우 PIN을 다시 설정 하지 않지만 **force** 매개 변수를 사용 하 여 pin을 강제로 재설정할 수 있습니다. 전자 메일 메시지는 SMTP (Simple Mail Transfer Protocol)를 사용 하 여 전송 됩니다.

**Set-cspinsendcawelcomemail** 스크립트를 반복적으로 실행 하 여 pin을 설정 하 고 사용자 그룹에 전자 메일을 보내는 스크립트를 만들 수 있습니다. 전자 메일 서식 파일 ( **CAWelcomeEmailTemplate.html** 파일)을 수정 하 여 인트라넷 페이지에 대 한 링크를 더 추가 하거나 전자 메일 텍스트를 수정할 수 있습니다.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>초기 PIN을 설정 하 고 환영 전자 메일을 보내려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령 프롬프트에서 다음을 실행합니다.
    
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
    
    **SmtpServer**     기본적으로 스크립트는이 매개 변수에 **$PSEmailServer** 예약 된 환경 변수 값을 사용 합니다. **$PSEmailServer** 변수를 설정 하지 않은 경우이 매개 변수를 지정 해야 합니다.
    
    **자격 증명**     기본적으로 스크립트는 현재 사용자의 자격 증명을 사용 합니다. 현재 사용자에 게 지정 된 보낸 사람 주소 대신 전자 메일을 보낼 수 있는 권한이 없는 경우이 매개 변수를 지정 해야 합니다. 일반적으로 전자 메일 주소를 보낸 사람 주소로 지정 하지 않는 경우이 매개 변수를 지정 합니다.
    
    예제:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    이 예에서는 새 PIN을 만든 다음 Marco에서 Bob에 게 환영 전자 메일을 보냅니다. 기본 서식 파일의 전자 메일 텍스트를 사용 하 고 HTML 형식으로 전자 메일 메시지를 만듭니다. 기본 제목은 "전화 접속 회의에 오신 것을 환영 합니다."입니다.
    
    다른 예:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    이 예에서는 bob에 게 기존 PIN이 있더라도 bob에 게 값이 "383042650" 인 새 PIN을 강제로 적용 한 다음 Marco에서 Bob에 게 환영 전자 메일을 보냅니다. Credential 매개 변수를 지정 했기 때문에 명령을 실행 하는 사용자에 게 암호를 입력 하 라는 메시지가 표시 됩니다. 이 전자 메일은 SSL (Secure Sockets Layer)을 사용 하 여 전송 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

