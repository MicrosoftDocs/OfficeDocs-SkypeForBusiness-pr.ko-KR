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
ms.openlocfilehash: db2e8bd84fa6a03bad845a87f7fb3c1532ae7ec2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188913"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="a4df4-103">비즈니스용 Skype 서버에서 전화 접속 사용자에 게 환영 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="a4df4-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="a4df4-104">**요약:** 비즈니스용 Skype 서버에서 사용자가 전화 접속 회의를 시작 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="a4df4-105">전화 접속 회의를 구성 하 고 제대로 작동 하는지 테스트 한 후에는 사용자에 대 한 초기 개인 id 번호 (Pin)를 설정 하 고 사용자에 게 기능의 사용 가능성에 대해 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="a4df4-106">초기 PIN 및 전화 접속 회의 설정 웹 페이지에 대 한 링크와 같은 안내 지침을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="a4df4-107">일반적으로 핀을 다시 설정 하는 데는 **CsClientPin** cmdlet을 사용 하지만 pin 정보를 사용 하 여 소개 시작 전자 메일을 보내려는 경우이 항목의 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="a4df4-108">전자 메일을 보내지 않으려면 대신 **Set CsClientPin** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="a4df4-109">**CsPinSendCAWelcomeMail** 스크립트를 사용 하 여 PIN을 설정 하 고 한 명의 사용자에 게 환영 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="a4df4-110">기본적으로 스크립트는 이미 설정 된 경우 PIN을 재설정 하지 않지만 Force 매개 변수를 사용 하 여 PIN을 강제로 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="a4df4-111">SMTP (Simple Mail Transfer Protocol)를 사용 하 여 전자 메일 메시지가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="a4df4-112">핀을 설정 하 고 사용자 그룹에 전자 메일을 보내기 위해 **set-CsPinSendCAWelcomeMail** 스크립트를 반복적으로 실행 하는 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="a4df4-113">전자 메일 템플릿 (즉, CAWelcomeEmailTemplate 파일)을 수정 하 여 인트라넷 페이지에 대 한 링크를 추가 하거나 전자 메일 텍스트를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="a4df4-114">초기 PIN 설정 및 환영 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="a4df4-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="a4df4-115">RTCUniversalServerAdmins 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="a4df4-116">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a4df4-117">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-117">Run the following at the command prompt:</span></span>
    
   ```
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

<span data-ttu-id="a4df4-118">**SmtpServer** 기본적으로 스크립트는이 매개 변수에 대해 **$PSEmailServer** 예약 된 환경 변수 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="a4df4-119">**$PSEmailServer** 변수를 설정 하지 않은 경우에는이 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="a4df4-120">**자격 증명** 기본적으로 스크립트는 현재 사용자의 자격 증명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="a4df4-121">현재 사용자에 게 지정 된 보낸 사람 주소 대신 전자 메일을 보낼 수 있는 권한이 없는 경우이 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="a4df4-122">일반적인 규칙으로, 전자 메일 주소를 보낸 사람 주소로 지정 하지 않으면이 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="a4df4-123">다음 예에서는 새 PIN을 만든 다음 매크로에서 Bob에 게 환영 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="a4df4-124">기본 서식 파일의 전자 메일 텍스트를 사용 하 고 HTML 형식으로 전자 메일 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="a4df4-125">기본 제목은 "전화 접속 회의 시작"입니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="a4df4-126">다음 예에서는 bob에 게 기존 PIN이 있는 경우에도 "383042650" 값이 포함 된 새 PIN을 강제 적용 하 고 매크로에서 Bob에 게 환영 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="a4df4-127">Credential 매개 변수를 지정 했기 때문에 명령을 실행 하는 사용자에 게 암호를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="a4df4-128">SSL (Secure Sockets layer)을 사용 하 여 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4df4-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
